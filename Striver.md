## Arrays

### 1. Longest Subarray with sum k (+ve and -ve numbers) (Easy)
> [Link](https://www.geeksforgeeks.org/problems/longest-sub-array-with-sum-k0809/1) - GFG
```
1. Make a Hashmap
3. Iterate over the loop
4. Check if the running sum is equal to k if so then update the maxLen = i+1
2. Store the running sum if not present in the Hashmap (Sum, Index)
3. Check if there is (sum - k) in the Hashmap if so then check the max of (maxLen) and (i - idx of (sum - k))
```

```java
HashMap<Integer, Integer> map = new HashMap<>();
int n = arr.length, sum = 0, max = 0;
for(int i=0; i<n; i++)
{
    sum += arr[i];
    if(sum == k) { max = i+1; }
    if(!map.containsKey(sum)) { map.put(sum, i); }
    if(map.containsKey(sum - k)) { max = Math.max(max, i - map.get(sum - k)); }
}
```

### 2. Longest Subarray with sum k (+ve numbers only) (Easy)
> [Link](https://www.geeksforgeeks.org/problems/subarray-with-given-sum-1587115621/1) - GFG
```
1. Iterate the array till your pointer 2 reaches the end
2. Keep running sum and then check 
3. If running sum > target then remove the values at pointer 1 and move front till sum > target
4. If sum == target then return the 1 based index (p1 + 1, p2)
```

```java
int n = arr.length, p1 = 0, p2 = 0, sum = 0;
ArrayList<Integer> ans = new ArrayList<>();
ans.add(-1);
while(p2 < n)
{
    sum += arr[p2];
    p2++;
    while(sum > target) 
    {
        sum -= arr[p1];
        p1++;
    }
    if(sum == target)
    {
        ans.remove(0);
        ans.add(p1+1);
        ans.add(p2);
        break;
    }
}
return ans;
```

### 3. Sort 0,1 & 2 (Medium)
> [Link](https://leetcode.com/problems/sort-colors/) - Leetcode 75
```
1. Take 3 pointers: left = 0, mid = 0 & right = n - 1
2. Increase the left and mid pointer if nums[mid] == 0
3. Increase the mid pointer if nums[mid] == 1
4. Decrease the right pointer if nums[mid] == 2
```

```java
int n = nums.length, left = 0, mid = 0, right = n-1, temp = 0;
while(mid <= right)
{
    if(nums[mid] == 0)
    {
        temp = nums[mid];
        nums[mid] = nums[left];
        nums[left] = temp;
        left++;
        mid++;
    }
    else if(nums[mid] == 1) mid++;
    else 
    {
        temp = nums[mid];
        nums[mid] = nums[right];
        nums[right] = temp;
        right--;
    }
}
```

### 4. Majority element (Easy)
> [Link](https://leetcode.com/problems/majority-element/) - Leetcode 169
```
1. Solve in optimized manner without using extra space
2. Since we have the one majority of element which appears n/2 times
3. So keep track of current number and its count if you encounter other number then reduce the count by 1
4. If count is zero then set the number from the loop as current number
```

```java
int cnt = 0, currNum = nums[0];
for(int i : nums)
{
    if(currNum == i) cnt++;
    else cnt--;

    if(cnt == 0) 
    {
        currNum = i;
        cnt++;
    }
}
return currNum;
```

### 5. Maximum subarry sum using Kadanes Algorithm (+ve and -ve numbers) (Medium)
> [Link](https://leetcode.com/problems/maximum-subarray/) - Leetcode 53
```
1. For each iteration of the loop check the max (currSum) of current number & current number and current sum
2. And then maintain a global max to check which is Max betwreen Global max and current sum
```

```java
int n = nums.length, currMax = nums[0], max = nums[0];
for(int i=1; i<n; i++)
{
    currMax = Math.max(nums[i], currMax + nums[i]);
    if(currMax > max) max = currMax;
}
return max;
```

### 6. Print Maximum subarry sum using Kadanes Algorithm (+ve and -ve numbers) (Medium)
> [Link](https://leetcode.com/problems/maximum-subarray/) - Leetcode 53
```
1. Same as the above Kadanes Algorithm but storing the max subarray array elements also
2. Use the ArrayList to store the running sub-array and max sub-array
```

```java
int n = nums.length, currMax = nums[0], max = nums[0];
ArrayList<Integer> subArr = new ArrayList<>();
ArrayList<Integer> ans = subArr;
subArr.add(nums[0]);
for(int i=1; i<n; i++)
{
    if(nums[i] > (nums[i] + currMax))
    {
        subArr = new ArrayList<>();
        subArr.add(nums[i]);
        currMax = nums[i];
    }
    else 
    {
        subArr.add(nums[i]);
        currMax = nums[i] + currMax;
    }

    if(currMax > max) 
    {
        ans = subArr;
        max = currMax;
    }
}
for(int i : ans) System.out.print(i + " ");
System.out.println();
return max;
```

### 7. Best time to buy and sell stocks (Easy)
> [Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) - Leetcode 121
```
1. Find the minStock number in the running loop
2. And find the max of the (currStock - minStock) & maxProfit
```

```java
int Stock = Integer.MAX_VALUE, maxProfit = 0, currProfit = 0;
for(int currStock : prices)
{
    Stock = Math.min(Stock, currStock);
    currProfit = currStock - Stock;
    maxProfit = Math.max(maxProfit, currProfit);
}
return maxProfit;
```

### 8. Next Permutation (Medium)
> [Link](https://leetcode.com/problems/next-permutation/) - Leetcode 31
```
1. Find the index of the element which is smaller then the next element from the right side
2. If no index is -1 then return the reversed array
3. If element present then find the element which is just greater then number at index from the right side
4. Swap the elements and then reverse the array on on the right side of index + 1
```

```java
int n = nums.length, temp = 0;
int p1 = 0, p2 = 0, idx = -1, swapIdx = 0;
for(int i=n-2; i>-1; i--) 
{
    if(nums[i] < nums[i+1]) 
    { 
        idx = i; 
        break; 
    }
}
if(idx == -1) reverse(nums, 0, n-1);
else
{
    for(int i=n-1; i>idx; i--)
    {
        if(nums[i] > nums[idx]) 
        {
            swapIdx = i;
            break;
        }
    }
    temp = nums[idx];
    nums[idx] = nums[swapIdx];
    nums[swapIdx] = temp;
    reverse(nums, idx+1, n-1);
}
```

### 9. Leaders in an Array (Medium)
> [Link](https://takeuforward.org/plus/dsa/problems/leaders-in-an-array)
```
1. Initialize the max to last element and add it to List
2. Keep a track of Running max while traversing from the right to left of the array
3. If current element is greater then the max then add to the List and update the max
```

```java
int n = nums.length, prevMax = nums[n-1];
List<Integer> ans = new ArrayList<>();
ans.add(nums[n-1]);
for(int i=n-2; i>=0; i--)    
{
    if(nums[i] > prevMax) 
    {
        ans.add(nums[i]);
        prevMax = Math.max(prevMax, nums[i]);
    }
}
n = ans.size();
for(int i=0; i<n/2; i++)
{
    int temp = ans.get(i);
    ans.set(i, ans.get(n-i-1));
    ans.set(n-i-1, temp);
}
return ans;
```

### 10. Longest Consecutive Sequence (Medium)
> [Link](https://leetcode.com/problems/longest-consecutive-sequence/) - Leetcode 128

```
1. Add all the elements to a HashSet
2. Traverse one by one element in the array and check if (num + 1) exists in the set using a while loop
3. Keep track of max length and return it
```

```java
HashSet<Integer> set = new HashSet<>();
for(int n : nums) set.add(n);
int max = 0;
for(int n : set)
{
    if(!set.contains(n - 1))
    {
        int curr = n;
        int len = 1;
        while(set.contains(curr + 1))
        {
            curr++;
            len++;
        }
        max = Math.max(max, len);
    }
}
return max;
```

### 11. Set Matrix Zeroes (Medium)
> [Link](https://leetcode.com/problems/set-matrix-zeroes/) - Leetcode 73

```
1. Check if the 0th Row and 0th Column has 0 in it and store it as a Boolean
2. Interate from 1st Row and 1st Column is any element is zero then mark that elements 0th Row and 0th Column as 0
3. Check the 0th Row and 0th Column and mark the elements zero in 2nd iteration
4. Check the Boolean values and make the elements to zero if 0th Row or 0th Column was true
```

```java
int rows = matrix.length;
int cols = matrix[0].length;
boolean firstRowZero = false;
boolean firstColZero = false;
for(int j=0; j<cols; j++) if(matrix[0][j] == 0) firstRowZero = true;
for(int i=0; i<rows; i++) if(matrix[i][0] == 0) firstColZero = true;
for(int i=1; i<rows; i++) 
{
    for(int j=1; j<cols; j++) 
    {
        if(matrix[i][j] == 0) 
        {
            matrix[i][0] = 0;
            matrix[0][j] = 0;
        }
    }
}
for(int i=1; i<rows; i++) 
{
    for(int j=1; j<cols; j++) 
    {
        if(matrix[i][0] == 0 || matrix[0][j] == 0) matrix[i][j] = 0;
    }
}
if(firstRowZero) for(int j=0; j<cols; j++) matrix[0][j] = 0;
if(firstColZero) for(int i=0; i<rows; i++) matrix[i][0] = 0;
```

### 12. Rotate Matrix by 90 Degree (Medium)
> [Link](https://leetcode.com/problems/rotate-image/) - Leetcode 48

```
1. Transpose the Matrix
2. Reverse each Row of the Matrix
```

```java
int n = matrix.length;
int temp = 0, left = 0, right = 0;
for(int i=0; i<n; i++)
{
    for(int j=i; j<n; j++)
    {
        temp = matrix[i][j];
        matrix[i][j] = matrix[j][i];
        matrix[j][i] = temp;
    }   
}
for(int i=0; i<n; i++)
{
    left = 0;
    right = n-1;
    while(left <= right)
    {
        temp = matrix[i][left];
        matrix[i][left] = matrix[i][right];
        matrix[i][right] = temp;
        left++;
        right--;
    }
}
```

### 13. Spiral Matrix (Medium)
> [Link](https://leetcode.com/problems/spiral-matrix/) - Leetcode 54

```
1. Initialize the end pointers i.e., minR, maxR, minC, maxC
2. Traverse the Matrix in Pattern and keep count of number of elements
3. Traversal pattern is
   Left to Right (Top Row)
   Top to Bottom (Right Column)
   Right to Left (Bottom Row)
   Bottom to Top (Left Column)
4. Keep the track of elements passed count and then once its > matrix size break the loop
```

```java
List<Integer> ans = new ArrayList<>();
int m = matrix.length;
int n = matrix[0].length;
int minR = 0;
int maxR = m-1;
int minC = 0;
int maxC = n-1;
int count = 0;
int total = m*n;
while(count < total)
{
    for(int i=minC; i<=maxC; i++)
    {
        if(count >= total) return ans;
        ans.add(matrix[minR][i]);
        count++;
    }
    minR++;
    if(count > total) break;

    for(int i=minR; i<=maxR; i++)
    {
        if(count >= total) return ans;
        ans.add(matrix[i][maxC]);
        count++;
    }
    maxC--;
    if(count > total) break;

    for(int i=maxC; i>=minC; i--)
    {
        if(count >= total) return ans;
        ans.add(matrix[maxR][i]);
        count++;
    }
    maxR--;
    if(count > total) break;

    for(int i=maxR; i>=minR; i--)
    {
        if(count >= total) return ans;
        ans.add(matrix[i][minC]);
        count++;
    }
    minC++;
    if(count >= total) break;
}
return ans;
```

### 14. Subarray Sum Equals K (Medium)
> [Link](https://leetcode.com/problems/subarray-sum-equals-k/) - Leetcode 560

```
1. Create a HashMap and Keep a track of running Sum
2. Check if the Running Sum = k, If so increase the count
3. Check if (Running Sum - k) key exists in the Map then increase the count by the value of that key
4. Add the Running Sum to the Map if it doesn't exist if not increase the count by 1
```

```java
Map<Integer, Integer> prefixSums = new HashMap<>();
int cnt = 0, currSum = 0, n = nums.length;
for(int i=0; i<n; i++) 
{
    currSum += nums[i];
    if(currSum == k) cnt++;
    if(prefixSums.containsKey(currSum - k)) cnt += prefixSums.get(currSum - k);
    prefixSums.put(currSum, prefixSums.getOrDefault(currSum, 0) + 1);
}
return cnt;
```

### 15. Pascal's Triangle (Easy)
> [Link](https://leetcode.com/problems/pascals-triangle/) - Leetcode 118

```
1. Make a subList with 1 as element
2. Make a subList with 1 1 as elements
3. Now use these subList to generate further
```

```java
List<List<Integer>> ans = new ArrayList<>();
List<Integer> sub_ans = new ArrayList<>();
sub_ans.add(1);
ans.add(sub_ans);
if(numRows == 1) return ans;
List<Integer> sub_ans2 = new ArrayList<>();
sub_ans2.add(1); sub_ans2.add(1);
ans.add(sub_ans2);
if(numRows == 2) return ans;
int r = numRows;
while(r > 2)
{
    List<Integer> sub_ans3 = new ArrayList<>();
    sub_ans3.add(1);
    int idx = 1;
    int s = ans.size()-1;
    while(idx < ans.get(s).size())
    {
        sub_ans3.add(ans.get(s).get(idx) + ans.get(s).get(idx-1));
        idx++;
    }
    sub_ans3.add(1);
    ans.add(sub_ans3);
    r--;
}
return ans;
```

### 16. Majority Element II (Medium)
> [Link](https://leetcode.com/problems/majority-element-ii/) - Leetcode 229

```
1. Initialize cnt1 = 0, cnt2 = 0, num1 = num2 = Integer.MIN_VALUE
2. Refer the conditional statements in the code block
```

```java
int n = nums.length, min = (int)Math.floor(n/3);
int cnt1 = 0, cnt2 = 0, num1 = Integer.MIN_VALUE, num2 = Integer.MIN_VALUE;
List<Integer> ans = new ArrayList<>();
for(int i=0; i<n; i++)
{
    if(cnt1 == 0 && nums[i] != num2)
    {
        cnt1 = 1;
        num1 = nums[i];
    }
    else if(cnt2 == 0 && nums[i] != num1)
    {
        cnt2 = 1;
        num2 = nums[i];
    }
    else if(nums[i] == num1) cnt1++;
    else if(nums[i] == num2) cnt2++;
    else
    {
        cnt1--;
        cnt2--;
    }
}
cnt1 = 0;
cnt2 = 0;
for(int i : nums)
{
    if(num1 == i) cnt1++;
    else if(num2 == i) cnt2++;
}
if(num1 != Integer.MIN_VALUE && cnt1 > min) ans.add(num1);
if(num2 != Integer.MIN_VALUE && cnt2 > min) ans.add(num2);
return ans;
```

### 17. 3Sum (Medium)
> [Link](https://leetcode.com/problems/3sum/) - Leetcode 15

```
1. Sort the array
2. Iterate through the array
3. Pick an element and pick left and right pointers (After that element)
4. Use Binary search to find the 3rd number so that the sum = 0 if so add this 3 numbers to the List
5. Skip the 
```

```java
int n = nums.length;
Arrays.sort(nums);
List<List<Integer>> ans = new ArrayList<>();
for(int i=0; i<n-2; i++) 
{
    if(i > 0 && nums[i] == nums[i-1]) continue;
    int left = i+1;
    int right = n-1;
    while(left < right) 
    {
        int sum = nums[i] + nums[left] + nums[right];
        if(sum == 0) 
        {
            ans.add(Arrays.asList(nums[i], nums[left], nums[right]));
            left++;
            right--;
            while(left < right && nums[left] == nums[left-1]) left++;
            while(left < right && nums[right] == nums[right+1]) right--;
        } 
        else if(sum < 0) left++;
        else right--;
    }
}
return ans;
```

### 18. 4Sum (Medium)
> [Link](https://leetcode.com/problems/4sum/) - Leetcode 18

```
1. Sort the array
2. Loop using variable i (Skip the duplicates)
3. Loop using variable j = i+1 (Skip the duplicates)
4. Use while loop using two pointers k and l
5. Add all numbers and if target then add the numbers to list and skip the duplicates
6. If sum < target then move k right
7. Else move l to left
```

```java
Arrays.sort(nums);
List<List<Integer>> ans = new ArrayList<>();
int n = nums.length, k = 0, l = 0;
for(int i=0; i<n; i++)
{
    if(i > 0 && nums[i] == nums[i-1]) continue;
    for(int j=i+1; j<n; j++)
    {
        if(j != (i+1) && nums[j] == nums[j-1]) continue;
        k = j+1;
        l = n-1;
        while(k < l)
        {
            long sum = (long)nums[i] + nums[j] + nums[k] + nums[l];
            if(sum == target)
            {
                List<Integer> subAns = new ArrayList<>();
                subAns.add(nums[i]);
                subAns.add(nums[j]);
                subAns.add(nums[k]);
                subAns.add(nums[l]);
                ans.add(subAns);
                k++;
                l--;
                while(k < l && nums[k] == nums[k-1]) k++;
                while(k < l && nums[l] == nums[l+1]) l--;
            }
            else if(sum < target) k++;
            else l--;
        }
    }
}
return ans;
```

### 19. Longest Subarray with sum 0 (Medium)
> [Link](https://takeuforward.org/plus/dsa/problems/largest-subarray-with-sum-0)

```
1. Make a Hashmap
3. Iterate over the loop
4. Check if the running sum is equal to 0 if so then update the maxLen = i+1
2. Store the running sum if not present in the Hashmap (Sum, Index)
3. Check if there is (sum - 0) in the Hashmap if so then check the max of (maxLen) and (i - idx of (sum - 0))
```

```java
HashMap<Integer, Integer> map = new HashMap<>();
int n = arr.length, sum = 0, max = 0, k = 0;
for(int i=0; i<n; i++)
{
    sum += arr[i];
    if(sum == k) { max = i+1; }
    if(!map.containsKey(sum)) { map.put(sum, i); }
    if(map.containsKey(sum - k)) { max = Math.max(max, i - map.get(sum - k)); }
}
return max;
```

### 20. Count subarrays with given xor k (Hard)
> [Link](https://takeuforward.org/plus/dsa/problems/count-subarrays-with-given-xor-k)

```
1. Make a Hashmap and add (0, 1)
2. Iterate a loop over the array and then keep a track of running xor
3. If x = (xor ^ k) exists then add it to count
4. If xor exist in the HashMap then increase the count of not add it
```

```java
int n = nums.length, xor = 0, cnt = 0, x = 0;
HashMap<Integer, Integer> map = new HashMap<>();
map.put(0,1);
for(int i=0; i<n; i++)
{
    xor = xor ^ nums[i];
    x = xor ^ k;
    if(map.containsKey(x)) cnt += map.get(x);
    if(map.containsKey(xor)) map.put(xor, map.get(xor) + 1);
    else map.put(xor, 1);
}
return cnt;
```

### 21. Merge Intervals (Medium)
> [Link](https://leetcode.com/problems/merge-intervals/) - Leetcode 56

```
1. Sort the Interval array based on the 1st element
2. Then merge the arrays if arr[i][1] >= arr[i+1][0] if not
3. Create a new array of size two and add it to the List
```

```java
int n = intervals.length;
if(n == 1) return intervals;
Arrays.sort(intervals, (a, b) -> a[0] - b[0]);
List<int[]> result = new ArrayList<>();
int start = intervals[0][0];
int end = intervals[0][1];
for(int i=1; i<n; i++)
{
    if(intervals[i][0] <= end) end = Math.max(end, intervals[i][1]);
    else 
    {
        result.add(new int[]{start, end});
        start = intervals[i][0];
        end = intervals[i][1];
    }
}
result.add(new int[]{start, end});
return result.toArray(new int[result.size()][]);
```

### 22. Merge Sorted Array (Easy)
> [Link](https://leetcode.com/problems/merge-sorted-array/) - Leetcode 88

```
1. Make 3 pointers for nums1, nums2 and full length of k = nums1 + nums2
2. Iterate from the end of nums1 and nums2
3. If number at nums1 is greater then place that at pointer k and reduce the k and i pointer
4. If not then place that at pointer k and reduce the k and j pointer
5. Place the rest of the leftover elements from nums2 in nums1 and reduce the k and j pointer
```

```java
int i = m-1;
int j = n-1;
int k = m+n-1;
while(i >= 0 && j >= 0)
{
    if(nums1[i] > nums2[j]) nums1[k--] = nums1[i--];
    else nums1[k--] = nums2[j--];
}
while(j >= 0) nums1[k--] = nums2[j--];
```

### 23. Find the missing and repeating number (Hard)
> [Link](https://takeuforward.org/plus/dsa/problems/find-the-repeating-and-missing-number)

```
1. Find the sum of n natural numbers from 1 to n and find the sum of the elements in the array
2. Find the sum of square of n natural numbers from 1 to n and find the sum of sqaure of elements in the array
3. Equation 1: x - y = sumOfArrayElements - sumOfNaturalNumbers
4. Equation 2: x^2 - y^2 = sumOfSquareofArrayElements - sumOfSquareofNaturalNumbers
5. Math equation 
   (x - y) = a -> eq1
   (x - y) * (x + y) = b -> eq2
   To get (x + y) = eq2/eq1
   We have two equation now
   (x + y) = a
   (x - y) = b

   add both 2x = a + b
   so x = (a + b)/2
   y = x - b
```

```java
long n = nums.length, sum = 0, sqrSum = 0;
long realSum = (n * (n+1))/2;
long realSqrSum = (n * (n+1) * (2*n+1))/6;
for(int i=0; i<n; i++) 
{
    sum += nums[i];
    sqrSum += (long)nums[i] * (long)nums[i];
}
// x is repeating number
// y is missing number
// (x - y) = sumOfNautralNumbers - Real-sumOfNautralNumbers
// (x^2 - y^2) = sumOfSquareOfNaturalNumbers - Real-sumOfSquareOfNaturalNumbers
long eq1 = sum - realSum; // (x - y)
long eq2 = sqrSum - realSqrSum; // (x - y) * (x + y)
eq2 = eq2/eq1;
long x = (eq1 + eq2)/2;
long y = x - eq1;
int ans[] = {(int)x, (int)y};
return ans;
```

### 24. Count Invesrion (Hard)
> [Link](https://takeuforward.org/plus/dsa/problems/count-inversions)

```
1. Using Merge Sort logic
2. Use recursion to split the array in half using mergeSort() function
3. Then Before Applying merge() function check for numbers[i] > nums[j] and increae the count and then merge
```

```java
public long cnt = 0;
public void merge(int nums[], int p, int q, int r)
{
    int j = q + 1;
    for(int i = p; i <= q; i++)
    {
        while(j <= r && nums[i] > nums[j]) j++;
        cnt += (j - (q + 1));
    }
    int nL = q - p + 1;
    int nR = r - q;
    int L[] = new int[nL];
    int R[] = new int[nR];
    for(int i = 0; i < nL; i++) L[i] = nums[p + i];
    for(int i = 0; i < nR; i++) R[i] = nums[q + i + 1];
    int i = 0, k = p;
    j = 0;
    while(i < nL && j < nR)
    {
        if(L[i] <= R[j]) nums[k++] = L[i++];
        else nums[k++] = R[j++];
    }
    while(i < nL) nums[k++] = L[i++];
    while(j < nR) nums[k++] = R[j++];
}
public void mergeSort(int nums[], int p, int r)
{
    if(p >= r) return;
    int q = p + (r - p)/2;
    mergeSort(nums, p, q);
    mergeSort(nums, q+1, r);
    merge(nums, p, q, r);
}
public long numberOfInversions(int[] nums) 
{
    int n = nums.length;
    mergeSort(nums, 0, n-1);
    return cnt;
}
```

### 25. Reverse Pairs (Hard)
> [Link](https://leetcode.com/problems/reverse-pairs/) - Leetcode 493

```
1. Using Merge Sort logic
2. Use recursion to split the array in half using mergeSort() function
3. Then Before Applying merge() function check for numbers[i] > 2L * nums[j] and increae the count and then merge
```

```java
public int cnt = 0;
public void merge(int nums[], int p, int q, int r)
{
    int j = q + 1;
    for(int i = p; i <= q; i++)
    {
        while(j <= r && (long)nums[i] > 2L * nums[j]) j++;
        cnt += (j - (q + 1));
    }
    int nL = q - p + 1;
    int nR = r - q;
    int L[] = new int[nL];
    int R[] = new int[nR];
    for(int i = 0; i < nL; i++) L[i] = nums[p + i];
    for(int i = 0; i < nR; i++) R[i] = nums[q + i + 1];
    int i = 0, k = p;
    j = 0;
    while(i < nL && j < nR)
    {
        if(L[i] <= R[j]) nums[k++] = L[i++];
        else nums[k++] = R[j++];
    }
    while(i < nL) nums[k++] = L[i++];
    while(j < nR) nums[k++] = R[j++];
}
public void mergeSort(int nums[], int p, int r)
{
    if(p >= r) return;
    int q = p + (r - p)/2;
    mergeSort(nums, p, q);
    mergeSort(nums, q+1, r);
    merge(nums, p, q, r);
}
public long numberOfInversions(int[] nums) 
{
    int n = nums.length;
    mergeSort(nums, 0, n-1);
    return cnt;
}
```

### 26. Maximum Product Subarray (Medium)
> [Link](https://leetcode.com/problems/maximum-product-subarray/) - Leetcode 152

```
1. Modified Kadanes algorithm
2. Find both running max and min using Kadanes algoritm
3. If u encounter a -ve number then swap the min and max
4. Keep checking for finalMax in each iteration
```

```java
int max = nums[0];
int min = nums[0];
int ans = nums[0];
for(int i=1; i<nums.length; i++)
{
    if(nums[i] < 0)
    {
        int temp = max;
        max = min;
        min = temp;
    }
    max = Math.max(nums[i], max * nums[i]);
    min = Math.min(nums[i], min * nums[i]);
    ans = Math.max(ans, max);
}
return ans;
```

## Binary Search

### 1. Binary Search (Easy)
> [Link](https://leetcode.com/problems/binary-search/) - Leetcode 704

```
1. Keep left and right pointers, and mid pointer as 0
2. Loop while left <= right, Find mid = left + (right - left)/2
3. Check if number at mid is equal to target then return the mid
4. If number at mid is greater then target shift the right pointer to mid - 1
5. If number at mid is smaller then target shift the left pointer to mid + 1
6. Else return -1
```

```java
int n = nums.length;
int left = 0, right = n-1, mid = 0;
while(left <= right)
{
    mid = left + (right - left)/2;
    if(nums[mid] == target) return mid;
    else if(nums[mid] > target) right = mid-1;
    else left = mid+1;
}
return -1;
```

### 2. Lower Bound (Easy)
> [Link](https://takeuforward.org/plus/dsa/problems/lower-bound)

```
1. Make left = 0, right = n-1 and mid pointer with another variable as ans to store the index of lower bound
2. Loop while left <= right, Find mid = left + (right - left)/2
3. Check if number at mid >= target then update the ans to mid and right to mid - 1
4. Else if number at mid is < target then update left to mid + 1
5. Return ans
```

```java
int n = nums.length;
int left = 0, right = n-1, mid = 0, ans = 0;
while(left <= right)
{
    mid = left + (right - left)/2;
    if(nums[mid] >= x) 
    {
        ans = mid;
        right = mid - 1;
    }
    else left = mid + 1;
}
return ans;
```

### 3. Upper Bound (Easy)
> [Link](https://takeuforward.org/plus/dsa/problems/upper-bound)

```
1. Make left = 0, right = n-1 and mid pointer with another variable as ans to store the index of lower bound
2. Loop while left <= right, Find mid = left + (right - left)/2
3. Check if number at mid > target then update the ans to mid and right to mid - 1
4. Else if number at mid is < target then update left to mid + 1
5. Return ans
```

```java
int n = nums.length;
int left = 0, right = n-1, mid = 0, ans = 0;
while(left <= right)
{
    mid = left + (right - left)/2;
    if(nums[mid] > x) 
    {
        ans = mid;
        right = mid - 1;
    }
    else left = mid + 1;
}
return ans;
```

### 4. Search Insert Position (Easy)
> [Link](https://leetcode.com/problems/search-insert-position/) - Leetcode 35

```
1. Make left = 0, right = n-1 and mid pointer with another variable as ans with value as n
2. Loop while left <= right, Find mid = left + (right - left)/2
3. Check if number at mid >= target then update the ans to mid and right to mid - 1
4. Else if number at mid is < target then update left to mid + 1
5. Return ans
```

```java
int n = nums.length, left = 0, right = n-1, mid = 0, ans = n;
while(left <= right)
{
    mid = left + (right - left)/2;
    if(nums[mid] >= target) 
    {
        ans = mid;
        right = mid - 1;
    }
    else left = mid + 1;
}
return ans;
```

### 6. Find First and Last Position of Element in Sorted array (Medium)
> [Link](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/) - Leetcode 34

```
1. Make three pointers left, right and mid and an array to store the index of First and Last occurance of target
2. Use Binary search to find the First occurance by moving left of the target
3. Use Binary search to find the Last occurance by moving right of the target
4. Return the index's
```

```java
int n = nums.length, left = 0, right = n-1, mid = 0;
int res[] = {-1, -1};
while(left <= right)
{
    mid = left + (right - left)/2;
    if(nums[mid] == target)
    {
        res[0] = mid;
        right = mid - 1;
    }
    else if(nums[mid] > target) right = mid - 1;
    else left = mid + 1;
}  
left = 0;
right = n-1;
while(left <= right)
{
    mid = left + (right - left)/2;
    if(nums[mid] == target)
    {
        res[1] = mid;
        left = mid + 1;
    }
    else if(nums[mid] > target) right = mid - 1;
    else left = mid + 1;
}
return res;
```

### 8. Search in Rotated sorted array (Medium)
> [Link](https://leetcode.com/problems/search-in-rotated-sorted-array) - Leetcode 33

```
1. Make low, high and mid pointers
2. Apply Binary search logic
3. Find the value for mid pointer and check for target if found return the index
4. If the number at low <= number at mid
   Check if the number at low <= target and target < number at mid then shift the high pointer
   Else shift the low pointer
5. Else 
   Check the number at mid < target and target <= number at high then shift the low pointer
   Else shift the high pointer
```

```java
int n = nums.length, low = 0, high = n-1, mid = 0;
while(low <= high) 
{
    mid = low + (high - low) / 2;
    if(nums[mid] == target) return mid;
    if(nums[low] <= nums[mid]) 
    {
        if(nums[low] <= target && target < nums[mid]) high = mid - 1;
        else low = mid + 1;
    } 
    else 
    {
        if(nums[mid] < target && target <= nums[high]) low = mid + 1;
        else high = mid - 1;
    }
}
return -1;
```
