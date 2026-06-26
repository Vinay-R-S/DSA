# STUDY.md - Feature Deep Dive: ARN Fetch, GSTIN Fetch, Email Templates

> Purpose: Explain these three features to a mentor - full step-by-step flow from user action to server response and back.

---

## PART 1: FETCH FROM ARN

### What it does
When a Sales RM enters an ARN (AMFI Registration Number) on a lead's detail form and clicks "Fetch from ARN", the system auto-fills fields like name, mobile, email, city, state, pincode, address, AUM, and website - pulling data from three sources in order of priority.

---

### Step-by-Step Flow

#### Step 1 - User enters ARN in the form
File: `client/src/components/sales/wizard/StepLeadDetails.tsx`

The lead onboarding wizard has Step 2 (Lead Details). This component renders a text input for the ARN field and a "Fetch from ARN" button. When the RM clicks the button, it calls `onAutoPopulate()` (passed in as a prop from `LeadWizard.tsx`).

---

#### Step 2 - LeadWizard triggers the lookup
File: `client/src/pages/sales/LeadWizard.tsx` (lines 261–299)

`autoPopulate()` function:
1. Reads `lead.arn` from state.
2. Calls the `lookupArn` mutation (TanStack Query `useMutation`).
3. Passes `{ arn: lead.arn, excludeLeadId: lead.id }` - the `excludeLeadId` is used so the server doesn't return this lead's own existing data as a "database match".

---

#### Step 3 - Client-side ARN normalization
File: `client/src/utils/arn.ts`

Before sending, the ARN is normalized:
- Input can be `"ARN-123456"` or `"123456"` or `"ARN 123456"`.
- The normalizer strips the `"ARN-"` prefix using regex `/^(?:ARN[-\s]?)?(\d{6})$/i`.
- Always stores/sends as a bare 6-digit string like `"042564"`.

---

#### Step 4 - HTTP call to the server
File: `client/src/services/leads.service.ts` (lines 161–175)

`leadsService.lookupArn(arn, excludeLeadId)` calls:
```
GET /api/v1/leads/arn-lookup/:arn?excludeLeadId=<id>
```
This goes through the Axios instance (`client/src/lib/apiClient.ts`) which automatically attaches the JWT token from Redux store.

---

#### Step 5 - Server validates the request
File: `server/src/validators/leads.validators.ts` (lines 60–67)

The route has a `validate(lookupArnSchema)` preHandler. The Zod schema:
- Validates `params.arn` - must be 6 digits (after normalization).
- The `.transform()` in `arnSchema` runs `normalizeArn()` again server-side (double safety).
- Also validates optional `query.excludeLeadId` as a number.

File: `server/src/utils/arn.ts` - server-side mirror of the normalizer.

---

#### Step 6 - Server route dispatches to controller
File: `server/src/routes/leads.routes.ts` (line 24)

```
GET /leads/arn-lookup/:arn  →  leadsController.lookupLeadArn
```

Note: This route is registered **before** `/:id` so that `arn-lookup` does not get matched as a lead ID.

---

#### Step 7 - Controller calls the service
File: `server/src/controllers/leads.controller.ts` (lines 92–100)

Thin handler - extracts `arn` from `req.params`, `excludeLeadId` from `req.query`, calls `lookupArn(arn, excludeLeadId)`, and returns the result via `sendSuccess()`.

---

#### Step 8 - ARN Lookup Service (3-tier priority)
File: `server/src/services/arnLookup.service.ts`

This is the core logic. It tries three sources in order and returns on the first hit:

**Tier 1 - Internal CRM Database**
- Searches `Lead` table for any other lead with the same ARN (excluding `excludeLeadId`).
- If found, returns `{ source: 'database', existsInDb: true, ...fields }`.
- This avoids hitting external APIs if we already have the data.

**Tier 2 - AdvisorKhoj MFAPI (Primary External)**
File: `server/src/services/external/advisorkhojArn.client.ts`
- Calls: `GET {MFAPI_ADVKJ_BASE_URL}/getAmfiArnDetails?arn_no={arn}&key={MFAPI_ADVKJ_API_KEY}`
- Timeout: 8 seconds.
- Returns `null` if API key is not configured (so dev environments don't break).
- Field mapping from the API response:
  | API field | Our field |
  |---|---|
  | `tele_off` or `tele_res` | `primaryNumber` |
  | `email` | `primaryEmail` |
  | `aum` | `arnAum` (0 is a valid value - not treated as missing) |
  | `city` | `city` |
  | `state` | `state` |
  | `pin` | `pincode` |
  | `address` | `arnAddress` |
  | `website` | `websiteUrl` |
  | `remarks` | `remarks` |

**Tier 3 - AMFI Public API (Fallback)**
File: `server/src/services/external/amfiArn.client.ts`
- Calls: `GET https://www.amfiindia.com/api/distributor-agent?strOpt=ALL&search={arn}&page=1&pageSize=10`
- Timeout: 15 seconds (AMFI is slower).
- Returns `null` if no record found.
- This API has less data - no `arnAum`, `websiteUrl`, `remarks`, or `state`.
- If both Tier 2 and Tier 3 fail, throws `AppError 404` ("ARN not found").

---

#### Step 9 - Response arrives on the client
File: `client/src/pages/sales/LeadWizard.tsx` (lines 268–299)

The `onSuccess` callback in `autoPopulate()` does smart merging:

**Conflict Resolution (mobile and email)**
- If the API returns a `primaryEmail` different from the lead's existing `lead.email`, the API value becomes `form.primaryEmail` and the lead's existing email is moved to `form.secondaryEmail`.
- Same logic for mobile → `primaryNumber` / `secondaryNumber`.
- This prevents silently overwriting data the RM already entered.

**Form Merge**
- All other fields (city, state, pincode, arnAum, websiteUrl, address, etc.) are merged into `nextForm` only if the API returned a non-empty value.
- Exception: `arnAum` uses `!== undefined` guard (so a returned value of `0` still overwrites, because 0 AUM is valid data).

**Persist**
- `persistDraft(nextForm)` is called immediately (bypasses the 600ms debounce) via `PATCH /leads/:id/wizard-draft`.

**Toast message** tells the RM which source was used:
- `'database'` → "Details matched from CRM database"
- `'advisorkhoj'` → "Details auto-populated from ARN"
- `'amfi'` → "Details auto-populated from AMFI (fallback)"

---

### ARN Flow Summary Diagram
```
RM enters ARN → clicks "Fetch from ARN"
  → autoPopulate() [LeadWizard.tsx]
    → useLookupArn mutation
      → leadsService.lookupArn() [leads.service.ts]
        → GET /leads/arn-lookup/:arn [leads.routes.ts]
          → validate(lookupArnSchema) [leads.validators.ts]
            → lookupLeadArn controller [leads.controller.ts]
              → lookupArn service [arnLookup.service.ts]
                ├── Tier 1: Lead.findOne (CRM DB) → hit? return 'database'
                ├── Tier 2: fetchAdvisorkhojArnDetails() [advisorkhojArn.client.ts]
                │     GET MFAPI → map fields → return 'advisorkhoj'
                └── Tier 3: fetchAmfiArnDetails() [amfiArn.client.ts]
                      GET AMFI → map fields → return 'amfi'
                      else → AppError 404
  ← ArnLookupResult
→ conflict resolution (email/mobile)
→ merge into form state
→ persistDraft() → PATCH /leads/:id/wizard-draft
→ toast with source label
```

---

## PART 2: FETCH FROM GSTIN

### What it does
When the RM enters a GSTIN (15-digit GST Identification Number) and clicks "Fetch from GST", the system auto-fills: legal name, display name, pincode, city, state, and business address - from the company's AdvisorKhoj MFAPI.

---

### Step-by-Step Flow

#### Step 1 - User enters GSTIN and clicks "Fetch from GST"
File: `client/src/components/sales/wizard/StepLeadDetails.tsx`

The GSTIN field and "Fetch from GST" button are rendered alongside the ARN section. Clicking calls `onAutoPopulateGst()` (prop from `LeadWizard.tsx`).

---

#### Step 2 - LeadWizard triggers the lookup
File: `client/src/pages/sales/LeadWizard.tsx` (lines 332–355)

`autoPopulateGst()` function:
1. Guards: if `!form.gstin`, shows a toast error - "Enter a GSTIN first".
2. Calls the `lookupGst` mutation with the raw GSTIN string.

---

#### Step 3 - HTTP call to the server
File: `client/src/services/leads.service.ts` (lines 177–189)

`leadsService.lookupGst(gstin)` calls:
```
GET /api/v1/leads/gst-lookup/:gstin
```

---

#### Step 4 - Server validates
File: `server/src/validators/leads.validators.ts` (lines 69–73)

`lookupGstSchema` validates `params.gstin` against the GSTIN regex:
```
/^\d{2}[A-Z]{5}\d{4}[A-Z][A-Z\d][Z][A-Z\d]$/
```
15 characters: 2 state-code digits + 5-letter PAN + 4 digits + 3 check chars. Rejects garbage input before hitting the API.

---

#### Step 5 - Route and Controller
File: `server/src/routes/leads.routes.ts` (line 25)
```
GET /leads/gst-lookup/:gstin  →  leadsController.lookupLeadGst
```

File: `server/src/controllers/leads.controller.ts` (lines 102–109)

Thin controller - extracts `gstin`, calls `lookupGst(gstin)`, returns result.

---

#### Step 6 - GST Lookup Service
File: `server/src/services/gstLookup.service.ts`

Unlike ARN, GSTIN has only ONE source - the AdvisorKhoj MFAPI. No fallback. If the API is not configured or returns no data, throws `AppError 404`.

---

#### Step 7 - External GST API Client
File: `server/src/services/external/gstLookup.client.ts`

- Calls: `GET {MFAPI_ADVKJ_BASE_URL}/getCompanyDetailsByGST?gst_no={gstin}&key={MFAPI_ADVKJ_API_KEY}`
- Timeout: 8 seconds.
- Returns `null` if API key is missing.

**Address Assembly** (`buildAddress()` function, lines 31–46):
The GST API returns address in fragments (`bno`, `bnm`, `flno`, `st`, `locality`, `loc`). These are joined into one string, blank parts skipped, then `- {pncd} ({stcd})` is appended. For example:
```
"Plot 12, TechPark, Whitefield - 560066 (KARNATAKA)"
```

**Field Mapping:**
| API field | Our form field |
|---|---|
| `lgnm` | `legalName` |
| `tradeNam` | `displayName` |
| `pncd` | `pincode` |
| `loc` | `city` |
| `stcd` | `state` |
| assembled | `address` |

---

#### Step 8 - Form update on the client
File: `client/src/pages/sales/LeadWizard.tsx` (lines 342–354)

On success, merges `legalName`, `displayName`, `pincode`, `city`, `state`, `address` into the current form state. Then:
- `persistDraft(nextForm)` - immediate save.
- Toast: "Details auto-populated from GSTIN".

**Important distinction:**
- ARN's `address` → maps to `form.arnAddress` (distributor's own address from ARN registration).
- GSTIN's `address` → maps to `form.address` (company's GST-registered business address).
These are separate form fields.

---

### GSTIN Flow Summary Diagram
```
RM enters GSTIN → clicks "Fetch from GST"
  → autoPopulateGst() [LeadWizard.tsx]
    → guard: if no GSTIN, show toast and stop
      → useLookupGst mutation
        → leadsService.lookupGst() [leads.service.ts]
          → GET /leads/gst-lookup/:gstin [leads.routes.ts]
            → validate(lookupGstSchema) [leads.validators.ts]
              → lookupLeadGst controller [leads.controller.ts]
                → lookupGst service [gstLookup.service.ts]
                  → fetchGstDetails() [gstLookup.client.ts]
                    GET MFAPI → build address → map fields
                    null? → AppError 404
  ← GstLookupResult
→ merge into form state (legalName, displayName, pincode, city, state, address)
→ persistDraft()
→ toast "Details auto-populated from GSTIN"
```

---

## PART 3: EMAIL TEMPLATES

This is the most complex feature. It has two sides:
- **Admin side**: Create and manage templates with a visual block editor.
- **Sales RM side**: Compose and send emails to leads using those templates.

---

## PART 3A: ADMIN SIDE - Creating/Editing Templates

### What is a Template?
A template is a reusable email structure stored in the database with:
- A **name** and unique **slug** (URL-safe identifier like `quotation-draft`).
- A **subject** line (can contain `{{variable}}` placeholders).
- A **body** made of structured **blocks** (heading, paragraph, table, bank details, etc.).
- Optional default `To/CC/BCC` addresses.
- A **category** (sales, billing, renewal, service, internal).

File: `server/src/models/EmailTemplate.ts`

---

### Step 1 - Admin navigates to Templates page
File: `client/src/pages/AdminEmailTemplatesPage.tsx`

The admin sees a table of all email templates with:
- Name and slug.
- Category badge (color-coded).
- Active/inactive status.
- Edit and Delete (soft-delete) buttons.
- A "New Template" button → navigates to the editor.

---

### Step 2 - Admin opens the Template Editor
File: `client/src/pages/AdminEmailTemplateEditorPage.tsx`

This is a three-panel page:
1. **Left panel** - Variables panel: lists all 33 available `{{variable}}` tokens grouped by category.
2. **Middle panel** - Block editor: the email body, built from blocks.
3. **Right panel** - Live preview: renders the template with sample values.

The admin also fills in: Name, Slug (auto-derived from name), Category, Subject, default To/CC/BCC.

---

### Step 3 - Understanding Variables
File: `server/src/constants/emailVariables.ts`

There are 33 variables, for example:

| Variable | What it becomes |
|---|---|
| `{{client_name}}` | Lead's full name |
| `{{arn}}` | Lead's ARN number |
| `{{company_name}}` | Lead's company/legal name |
| `{{reference_number}}` | Auto-generated ref like `AK/QT/2026-27/T001` |
| `{{products_table}}` | Full HTML table of selected products |
| `{{subtotal}}` | Sum of product prices |
| `{{total_amount}}` | After discount + GST |
| `{{bank_account_name}}` | Company bank account name |
| `{{bank_upi_id}}` | UPI ID for payment |
| `{{sender_name}}` | The Sales RM's name |

Each variable also has a `sample` value used for **live preview** in the editor (e.g., `{{client_name}}` shows "Rajesh Kumar" in the preview).

The admin can click any variable in the left panel → it gets inserted at the cursor position in whichever field (subject or a block's text) was last focused.

File for insertion logic: `AdminEmailTemplateEditorPage.tsx` (lines 604–621) - uses `element.selectionStart`/`selectionEnd` to insert at exact cursor position.

---

### Step 4 - Building with Blocks
File: `client/src/lib/emailBlocks.ts`

The email body is built from an ordered array of **blocks**. Available block types:

| Block Type | What it renders |
|---|---|
| `heading` | `<h2>` with customizable text and color |
| `paragraph` | `<p>` with text (can contain `{{variables}}`) |
| `list` | `<ul>` or `<ol>` with bullet items |
| `table` | Custom HTML table with rows/columns |
| `bankDetails` | Fixed layout with bank name, account, IFSC, UPI, Razorpay link - all `{{bank_*}}` variables |
| `productsTable` | Emits the `{{products_table}}` placeholder (replaced at send time with the actual table) |
| `billingTotals` | Emits `{{subtotal}}`, `{{discount_label}}`, `{{gst_amount}}`, `{{total_amount}}` placeholders |
| `raw` | Raw HTML - escape hatch for custom markup |

The admin can add blocks, reorder them by drag-and-drop or Up/Down buttons, and edit each block's fields.

---

### Step 5 - How blocks are saved to the database
File: `client/src/lib/emailBlocks.ts` - `renderBlocksToHtml(blocks)` function

When saving, the blocks array goes through two operations:
1. Each block is rendered to its HTML string.
2. The **entire blocks array is JSON-encoded, base64-encoded, and prepended as an HTML comment** at the start of `bodyHtml`:
   ```html
   <!--EB_BLOCKS:eyJ0eXBlIjoiaGVhZGluZyIsInRleHQiOi...-->
   <h2>Hello {{client_name}}</h2>
   <p>Your ARN is {{arn}}...</p>
   ```

This "marker" trick means:
- The database stores valid renderable HTML (so it can be emailed directly if needed).
- The editor can re-open the template and **restore the exact block structure** by decoding the marker - no need to parse HTML back into blocks.

To recover blocks: `parseBlocksFromHtml(bodyHtml)` strips and decodes the comment.

Server-side port: `server/src/services/email/blocks.ts` (kept manually in sync with the client version).

---

### Step 6 - Live Preview in the editor
File: `AdminEmailTemplateEditorPage.tsx` (lines 576–597)

The right panel shows a live preview in an `<iframe>`. The preview logic:
1. Takes the current `bodyHtml`.
2. Calls `substitute(bodyHtml, sampleValues)` **client-side** - replaces every `{{variable}}` with its `sample` value from `emailVariables.ts`.
3. Wraps in a basic branded HTML document and sets `iframe.srcDoc`.
4. A `ResizeObserver` watches the iframe content and auto-adjusts its height.

This is purely client-side - no API call. It updates in real time as the admin edits.

---

### Step 7 - Saving the template
File: `AdminEmailTemplateEditorPage.tsx` (lines 679–712)

On "Save":
1. `renderBlocksToHtml(blocks)` → produces `bodyHtml` (with the embedded block marker).
2. `htmlToPlainText(bodyHtml)` → auto-generates a plain-text fallback (for email clients that don't render HTML).
3. Calls `createTemplate.mutate(values)` or `updateTemplate.mutate(values)`.

Chain:
```
AdminEmailTemplateEditorPage
  → useCreateEmailTemplate / useUpdateEmailTemplate [useEmailTemplates.ts]
    → emailTemplateService.create/update [emailTemplate.service.ts]
      → POST /email-templates  or  PUT /email-templates/:id [emailTemplate.routes.ts]
        → admin-only auth check [emailTemplate.routes.ts]
          → createTemplate / updateTemplate service [emailTemplate.service.ts]
            → EmailTemplate.create / .update in MySQL
```

---

### Step 8 - Managing templates
File: `AdminEmailTemplatesPage.tsx`

- **Edit** → opens editor pre-filled with existing template data.
- **Delete** → confirmation dialog → `emailTemplateService.remove(id)` → `DELETE /email-templates/:id` → sets `isActive: false` (soft delete, data is never removed from the database).
- **Variable registry endpoint**: `GET /email-templates/variables` returns the full `EMAIL_VARIABLES` array - used by the editor's variable panel.

---

## PART 3B: SALES RM SIDE - Composing and Sending Emails

### When does the RM send emails?
The wizard has 4 steps. Steps 3 and 4 each involve sending an email:
- **Step 3 (Lead Confirmation / Quotation)**: RM sends a quotation email to the lead. Template slug: e.g. `quotation-draft`.
- **Step 4 (Billing Notice)**: RM sends a billing notice to the internal billing team. Template slug: `billing-notice-internal`.

---

### Step 1 - RM opens Step 3 or Step 4 of the wizard

Files:
- `client/src/components/sales/wizard/StepLeadConfirmation.tsx`
- `client/src/components/sales/wizard/StepBillingNotice.tsx`

Both components use the `useEmailComposer` hook, passing the template slug and lead ID.

---

### Step 2 - Template preview is fetched from the server
File: `client/src/hooks/useEmail.ts` (lines 11–30) - `useEmailPreview` query

```
GET /api/v1/email/preview?templateSlug=quotation-draft&leadId=42
```

This is a `useQuery` (TanStack Query) - runs automatically when the step mounts.

---

### Step 3 - Server renders the preview
File: `server/src/services/email/emailRenderer.service.ts`

`renderEmailPreview(template, lead, sender, sentAt)`:

1. **Fetches company settings** (bank details, company name, support email, etc.) from `CompanySettings` table.
2. **Gets product line items** - reads `lead.LeadProduct` rows (post-onboarding) or `lead.wizardState` (if not yet onboarded). Calculates AUM-slab pricing.
3. **Computes billing** - discount, GST, total.
4. **Builds variable context** - a flat `{ client_name: "Rajesh Kumar", arn: "042564", subtotal: "₹12,000", ... }` object with all 33 variables resolved with real data.
5. **Special handling for `{{reference_number}}`**: In preview mode (`'placeholder'` mode), this variable is **NOT put into the context**. So it stays as the literal text `{{reference_number}}` in the preview - because the reference number is only minted when the email is actually sent (to avoid wasting sequence numbers on previews).
6. **Parses blocks** from `bodyHtml` using `parseBlocksFromHtml()` - decodes the embedded block marker.
7. **Renders each block** individually, calling `substitute(blockHtml, context)` on each.
8. Returns a `RenderedBlock[]` array plus the flat `subject/html/text` with variables substituted.

---

### Step 4 - Preview arrives on the client
File: `client/src/hooks/useEmail.ts` (lines 82–94)

When preview data arrives, `useEmailComposer` seeds state:
- `subject` ← `emailPreview.data.subject` (variables already resolved).
- `items` ← each rendered block becomes a **locked item**: `{ kind: 'locked', id, type, html }`.
  - "Locked" means the RM cannot edit these blocks - they come from the admin's template.
- `layoutBefore` / `layoutAfter` ← branded email header/footer chrome (logo, company name, footer links).

---

### Step 5 - RM sees the email composer
File: `client/src/components/sales/wizard/EmailBlockComposer.tsx`

The composer shows:
- The branded header (from `layoutBefore`).
- All locked blocks rendered as HTML (read-only, `pointer-events-none`).
- An "Add Block" section where the RM can insert their own paragraphs/lists/tables between the locked blocks.
- The branded footer (from `layoutAfter`).

**RM's own blocks** are `{ kind: 'rm', block: EmailBlock }` - editable inline via `RmBlockFields`. The RM can add `paragraph`, `list`, or `table` blocks (not headings, bank details, etc. - those are admin-only template blocks).

Locked and RM blocks can be drag-reordered together.

---

### Step 6 - RM clicks "Send"
File: `client/src/hooks/useEmail.ts` - `send()` function (lines 140–168)

1. Assembles final `bodyHtml`:
   ```
   {layoutBefore}
   {locked blocks' pre-rendered .html}
   {RM's own blocks rendered via renderBlockToHtml()}
   {layoutAfter}
   ```
2. Derives `bodyText` via `htmlToPlainText(bodyHtml)`.
3. Calls `sendEmailMutation.mutate({ templateSlug, leadId, to, cc, bcc, subject, bodyHtml, bodyText })`.

File: `client/src/services/email.service.ts` → `POST /api/v1/email/send`

---

### Step 7 - Server processes the send
File: `server/src/services/email/email.service.ts` - `sendEmail()` function

This is the most important server function. In order:

1. **Fetch template** by slug, check `isActive`.
2. **Job-role check** - `assertCanSendCategory()`: Sales RM job roles are checked against which template categories they're allowed to use. Admins bypass.
3. **Fetch lead** with ownership check - non-admin can only send for their own leads.
4. **Mint reference number** - `generateReferenceNumber(typeCode, sender.salesPersonCode)`:
   - `typeCode` is looked up from `TEMPLATE_REFERENCE_TYPE` map: e.g. `quotation-draft` → `'QT'`, `tax-invoice-draft` → `'INV'`.
   - Uses `EmailReferenceSequence` table, keyed by `(type_code, financial_year, sales_person_code)`.
   - Generates a number like `AK/QT/2026-27/T001`.
   - This happens **only at actual send** - never during preview.
5. **Final substitution** - one more `substitute()` pass on the sender's (possibly edited) `subject/bodyHtml/bodyText` to resolve `{{reference_number}}` (which was left as a literal in the preview HTML).
6. **Create EmailLog row** with `status: 'pending'` - audit trail exists even if the next steps fail.
7. **Build PDF attachments** - based on which template is being sent:
   - `quotation-draft` → generates a quotation PDF and attaches it.
   - `billing-notice-internal` → generates both a client info PDF and a quotation PDF.
   File: `server/src/services/email/email.service.ts` - `ATTACHMENT_BUILDERS` map (lines 119–127).
8. **Send via email provider**:
   File: `server/src/services/email/emailProviderFactory.ts`
   - `EMAIL_PROVIDER=postal` → calls Postal's HTTP API (`postal.provider.ts`).
   - `EMAIL_PROVIDER=mandrill` → stub, throws 501 (not yet implemented).
9. **Update EmailLog** with `status: 'sent'`, `postalMessageId`, `sentAt`. On failure: `status: 'failed'`.

---

### Variable Substitution Mechanics (How `{{variable}}` → Real Value)

File: `server/src/services/email/emailRenderer.service.ts` - `substitute()` (line 266)

```typescript
input.replace(/\{\{(\w+)\}\}/g, (token, key) => context[key] ?? token)
```

Single regex pass. If `context['client_name']` = `"Rajesh Kumar"`, then `{{client_name}}` becomes `"Rajesh Kumar"`. If a key is missing from context, the token is left unchanged (e.g., `{{reference_number}}` stays literal during preview).

The `context` object is built by `buildVariableContext()` (line 296) with every variable resolved from:
- The `Lead` record and its form JSON.
- The `LeadProduct` rows (or wizard draft).
- The `User` (sender) record.
- The `CompanySettings` record.
- The `EmailLog` history (for `{{prior_date_1}}`, `{{prior_date_2}}`).

---

### Complete Email Template Flow Summary

```
ADMIN SIDE (one-time setup):
Admin → AdminEmailTemplatesPage → "New Template"
  → AdminEmailTemplateEditorPage
    → fills Name, Subject (with {{variables}}), Category
    → adds Blocks (heading, paragraph, bankDetails, productsTable, etc.)
    → clicks variable tokens to insert {{variable}} placeholders
    → live preview shows sample values substituted
    → Save → renderBlocksToHtml() embeds block JSON as base64 comment in bodyHtml
      → POST /email-templates [emailTemplate.routes.ts]
        → createTemplate service [emailTemplate.service.ts]
          → EmailTemplate.create() in MySQL

SALES RM SIDE (per-lead usage):
RM opens Lead → wizard Step 3 (StepLeadConfirmation)
  → useEmailComposer('quotation-draft', leadId) [useEmail.ts]
    → GET /email/preview?templateSlug=quotation-draft&leadId=42
      → renderEmailPreview() [emailRenderer.service.ts]
        → buildVariableContext() → resolves all {{variables}} with lead's real data
        → parseBlocksFromHtml() → decodes block structure
        → renders each block with substitute()
        → {{reference_number}} stays literal (not minted yet)
      ← RenderedBlock[] + subject + html + text
    → locked items seed the composer UI
    → layoutBefore/layoutAfter → branded header/footer
  RM sees read-only template blocks, can add own paragraph/list blocks
  RM edits subject/to/cc, clicks "Send"
    → send() assembles bodyHtml (locked + RM blocks + layout)
      → POST /email/send [email.routes.ts]
        → sendEmail() service [email.service.ts]
          → assertCanSendCategory() (job-role check)
          → verifyOwnership()
          → generateReferenceNumber() → mints AK/QT/2026-27/T001
          → substitute() final pass → {{reference_number}} is now replaced
          → EmailLog.create(status: 'pending')
          → build PDF attachments (quotationPdf, clientInfoPdf)
          → emailProviderFactory → postal.provider.ts
            → POST to Postal API → email sent
          → EmailLog.update(status: 'sent', sentAt)
```

---

## Quick File Reference

| Feature | File |
|---|---|
| ARN normalizer (server) | `server/src/utils/arn.ts` |
| ARN normalizer (client) | `client/src/utils/arn.ts` |
| ARN + GST Zod validators | `server/src/validators/leads.validators.ts` |
| Leads routes (ARN + GST endpoints) | `server/src/routes/leads.routes.ts` |
| ARN + GST controller handlers | `server/src/controllers/leads.controller.ts` |
| ARN lookup service (3-tier) | `server/src/services/arnLookup.service.ts` |
| GST lookup service | `server/src/services/gstLookup.service.ts` |
| AdvisorKhoj ARN API client | `server/src/services/external/advisorkhojArn.client.ts` |
| AMFI ARN fallback API client | `server/src/services/external/amfiArn.client.ts` |
| GSTIN API client | `server/src/services/external/gstLookup.client.ts` |
| ARN result type | `server/src/types/arnLookup.ts` |
| Client leads service | `client/src/services/leads.service.ts` |
| Client lookup hooks | `client/src/hooks/useLeads.ts` |
| LeadDetailsForm type | `client/src/features/sales-rm/leadForm.ts` |
| ARN/GST fetch buttons + form | `client/src/components/sales/wizard/StepLeadDetails.tsx` |
| autoPopulate + autoPopulateGst | `client/src/pages/sales/LeadWizard.tsx` |
| EmailTemplate model | `server/src/models/EmailTemplate.ts` |
| Email variables registry (33 vars) | `server/src/constants/emailVariables.ts` |
| Email template routes | `server/src/routes/emailTemplate.routes.ts` |
| Email template controller | `server/src/controllers/emailTemplate.controller.ts` |
| Email template service (CRUD) | `server/src/services/emailTemplate.service.ts` |
| Variable substitution + context | `server/src/services/email/emailRenderer.service.ts` |
| Block HTML renderers (client) | `client/src/lib/emailBlocks.ts` |
| Block HTML renderers (server port) | `server/src/services/email/blocks.ts` |
| Email send/preview orchestration | `server/src/services/email/email.service.ts` |
| Email controller | `server/src/controllers/email.controller.ts` |
| Email routes | `server/src/routes/email.routes.ts` |
| Email send/preview validators | `server/src/validators/email.validators.ts` |
| Branded base layout wrapper | `server/src/services/email/baseLayout.service.ts` |
| Admin template list page | `client/src/pages/AdminEmailTemplatesPage.tsx` |
| Admin template editor page | `client/src/pages/AdminEmailTemplateEditorPage.tsx` |
| Client email template service | `client/src/services/emailTemplate.service.ts` |
| Client email template hooks | `client/src/hooks/useEmailTemplates.ts` |
| Client email send/preview service | `client/src/services/email.service.ts` |
| Sales RM composer hook | `client/src/hooks/useEmail.ts` |
| Sales RM email block UI | `client/src/components/sales/wizard/EmailBlockComposer.tsx` |
| Step 3 - Lead Confirmation email | `client/src/components/sales/wizard/StepLeadConfirmation.tsx` |
| Step 4 - Billing Notice email | `client/src/components/sales/wizard/StepBillingNotice.tsx` |
