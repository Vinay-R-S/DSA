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
4. Swap the elements and then reverse the array on the right side of index + 1
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
4. Use Binary search kinda logic to find the 3rd number so that the sum = 0 if so add this 3 numbers to the List
5. Skip the duplicates in the Binary search for left and right pointers
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

### 7. Count Occurrences of an Element in a Sorted Array (Medium)
> [Link](https://takeuforward.org/plus/dsa/problems/count-occurrences-of-an-element-in-a-sorted-array)

```
1. Make three pointers left, right and mid and an array to store the index of First and Last occurance of target
2. Use Binary search to find the First occurance by moving left of the target
3. Use Binary search to find the Last occurance by moving right of the target
4. Return the index's and check if the returned values are not -1 else return -1
5. Return high - low + 1
```

```java
// lowIdx function
int n = nums.length, low = 0, mid = 0, high = n-1, x = -1;
while(low <= high)
{
    mid = low + (high - low);
    if(nums[mid] == target)
    {
        x = mid;
        high = mid - 1;
    }
    else if(nums[mid] > target) high = mid - 1;
    else low = mid + 1;
}
return x;

// highIdx function
int n = nums.length, low = 0, mid = 0, high = n-1, x = -1;
while(low <= high)
{
    mid = low + (high - low);
    if(nums[mid] == target)
    {
        x = mid;
        low = mid + 1;
    }
    else if(nums[mid] > target) high = mid - 1;
    else low = mid + 1;
}
return x;

// Main function
int low = lowIdx(nums, target);
int high = highIdx(nums, target);
if(low == -1 && high == -1) return -1;
return high - low + 1;
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
    mid = low + (high - low)/2;
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

### 9. Search in Rotated sorted array II (Medium)
> [Link](https://leetcode.com/problems/search-in-rotated-sorted-array-ii/) - Leetcode 81

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
6. If the number at low == number at mid == number at high then shift the low and high pointers
```

```java
int n = nums.length, low = 0, high = n-1, mid = 0;
while(low <= high) 
{
    mid = low + (high - low)/2;
    if(nums[mid] == target) return true;
    if(nums[low] == nums[mid] && nums[mid] == nums[high]) 
    {
        low++;
        high--;
    }
    else if(nums[low] <= nums[mid]) 
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
return false;
```

### 10. Minimum in the Rotated Sorted Array (Medium)
> [Link](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) - Leetcode 153

```
1. Make three pointers, low = 0, high = n-1, and mid = 0
2. Find mid and check for
3. Number at low <= Number at mid then find the minimum number between ans and low and update the low
4. Number at low > Number at mid then find the minimum number between ans and high and update the high
```

```java
int n = nums.length, low = 0, high = n-1, mid = 0, ans = Integer.MAX_VALUE;
while(low <= high)    
{
    mid = low + (high - low)/2;
    if(nums[low] <= nums[mid])
    {
        ans = Math.min(ans, nums[low]);
        low = mid + 1;
    }
    else 
    {
        ans = Math.min(ans, nums[mid]);
        high = mid - 1;
    }
}
return ans;
```

### 11. Find out how many times the array is rotated (Easy)
> [Link](https://takeuforward.org/plus/dsa/problems/find-out-how-many-times-the-array-is-rotated)

```
1. Make three pointers low, mid, high
2. Loop while left <= right, find mid
3. Check if low = high return low
4. Check if mid > 0 [AND] number at mid < number at mid-1 return mid
5. Check if mid < n-1 [AND] number at mid > number at mid+1 return mid+1
6. Check if number at mid >= number at low then shift the low
7. Else shift the high
```

```java
int n = nums.size(), low = 0, high = n - 1;
while(low <= high)
{
    if(nums.get(low) <= nums.get(high)) return low;

    int mid = low + (high - low)/2;
    if(mid > 0 && nums.get(mid) < nums.get(mid-1)) return mid;
    if(mid < n-1 && nums.get(mid) > nums.get(mid+1)) return mid + 1;
    if(nums.get(mid) >= nums.get(low)) low = mid+1; 
    else high = mid-1;
}
return 0;
```

### 12. Single Element in a Sorted array (Medium)
> [Link](https://leetcode.com/problems/single-element-in-a-sorted-array/) - Leetcode 540

```
1. Check the extremes for duplicates
2. Take three pointers, low, high and mid
3. Use while loop (left <= right) and calculate mid
4. Check if number at (mid - 1) != mid != (mid + 1) then return the number
5. Else check if mid is odd and (mid-1) == (mid) [OR] mid is even and (mid) == (mid+1) then shift low
6. Else shift high
```

```java
int n = nums.length;

if(n == 1) return nums[0];
if(nums[0] != nums[1]) return nums[0];
if(nums[n-1] != nums[n-2]) return nums[n-1];

int low = 1, high = n-2, mid = 0;

while(low <= high)
{
    mid = low + (high - low)/2;

    if(nums[mid-1] != nums[mid] && nums[mid+1] != nums[mid]) return nums[mid];                
    else if(mid%2 == 1 && nums[mid-1] == nums[mid] || mid%2 == 0 && nums[mid] == nums[mid+1]) low = mid+1; 
    else high = mid-1;
}
return -1;
```

### 13. Find peak element (Medium)
> [Link](https://leetcode.com/problems/find-peak-element/) - Leetcode 162

```
1. Make the three pointers low, high and mid
2. If size is 1 then return 0, if not
3. Use loop while low <= high and find mid
4. If (mid = 0 [OR] number at mid > number at mid-1) [AND] (mid = high [OR] number at mid >= number at mid+1) return mid
5. Else mid > 0 [AND] number at mid-1 > number at mid then move high
6. Else move low
```

```java
int n = nums.length, low = 0, high = n-1, mid = 0;
if(n == 1) return 0;
while(low <= high)
{
    mid = low + (high - low)/2;
    if((mid == 0 || nums[mid] >= nums[mid - 1]) && (mid == high || nums[mid] >= nums[mid + 1])) return mid;
    else if(mid > 0 && nums[mid - 1] > nums[mid]) high = mid-1;
    else low = mid+1;
}
return -1;
```

### 14. Find Square of a number (Medium)
> [Link](https://leetcode.com/problems/sqrtx) - Leetcode 69

```
1. Take low = 0, mid = 0, high = x and do binary search
2. Move right -> mid if the mid * mid is greater then x
3. Move left -> mid if the mid * mid is lesser then x
4. If mid * mid == x then return ans or return ans
5. Take care of overflow so use long
```

```java
long left = 0, right = x, mid = 0, ans = 0;
while(left <= right)
{
    mid = left + (right - left)/2;
    if(mid * mid == x) return (int)mid;
    else if(mid * mid > x) right = mid - 1;
    else
    {
        ans = mid;
        left = mid + 1;
    }
}
return (int)ans;
```

### 15. Find Nth root of a number (Medium)
> [Link](https://takeuforward.org/plus/dsa/problems/find-nth-root-of-a-number)

```
1. Keep low = 1, high = M, mid = 0, p = 1
2. Find the mid and check if mid ^ N is equal to M then return
3. If greater then move the right -> mid
4. If lesser then move the left -> mid
5. Else return -1
```

```java
long low = 1, high = M, mid = 0, p = 1;
if(M == 1) return 1;
while(low <= high)
{
    mid = low + (high - low)/2;
    p = 1;
    for(int i=1; i<=N; i++)
    {
        p *= mid;
        if(p > M) break;
    }
    if(p == M) return (int) mid;
    else if(p > M) high = mid - 1;
    else low = mid + 1;
}
return -1;
```

### 16. Koko eating bananas (Medium)
> [Link](https://leetcode.com/problems/koko-eating-bananas/) - Leetcode 875

```
1. Make three pointers, low, k, high
2. Find the max and initialize high to max
3. Loop while low <= high, find the k (max bananas which can be finished in an hour)
4. Count the total hours to finish the pile and break if count > h (hours given)
5. If count <= h then store the value of k and shift the high
6. Else shift the low
```

```java
int low = 1, high = 0, ans = 0, k = 0, cnt = 0;
for(int pile : piles) high = Math.max(high, pile);
ans = high;
while(low <= high)
{
    k = low + (high - low)/2;
    cnt = 0;
    for(int pile : piles)
    {
        cnt += (pile + k - 1)/k;
        if(cnt > h) break;
    }
    if(cnt <= h)
    {
        ans = k;
        high = k - 1;
    }
    else low = k + 1;
}
return ans;
```

### 17. Minimum Number of Days to Make m Bouquets (Medium)
> [Link](https://leetcode.com/problems/minimum-number-of-days-to-make-m-bouquets/) - Leetcode 1482

```
1. Make three pointers, low, mid, high
2. Find the max and initialize high to max
3. Loop while low <= high, find the mid
4. Check if the number of bouquets can be made in mid days
5. If yes then store the value of mid and shift the high
6. Else shift the low
```

```java
public static boolean checkPossibility(int[] bloomDay, int day, int m, int k) 
{
    int count = 0, bouquets = 0; 
    for(int bloom : bloomDay) 
    {
        if(bloom <= day) 
        {
            count++; 
            if(count == k) 
            {
                bouquets++; 
                count = 0; 
            }
        } 
        else count = 0; 
    }
    return bouquets >= m; 
}

public int minDays(int[] bloomDay, int m, int k) 
{
    long required = (long) m * k;
    if(required > bloomDay.length) return -1; 
    int minDay = Integer.MAX_VALUE, maxDay = Integer.MIN_VALUE;
    for(int bloom : bloomDay) 
    {
        minDay = Math.min(minDay, bloom);
        maxDay = Math.max(maxDay, bloom);
    }
    int low = minDay, high = maxDay, result = -1;
    while(low <= high) 
    {
        int mid = (low + high)/2;
        if(checkPossibility(bloomDay, mid, m, k)) 
        {
            result = mid; 
            high = mid - 1;
        } 
        else low = mid + 1; 
    }
    return result;
}
```

### 18. Find the smallest divisor (Medium)
> [Link](https://leetcode.com/problems/find-the-smallest-divisor-given-a-threshold/) - Leetcode 1283

```
1. Take low = 0, mid = 0, high = max value in the array
2. Apply binary search and find the mid
3. Find the sum of the all the number divison using the mid as the divisor
4. Keep track of sum and threshold, left -> mid if the sum is greater then threshold
5. Shift right -> mid if the sum <= threshold
6. Return the low value
```

```java
int n = nums.length, low = 1, mid = 0, high = 0, sum = 0;
for(int i : nums) high = Math.max(high, i);
while(low <= high)
{
    sum = 0;
    mid = low + (high - low)/2;
    for(int i : nums) 
    {
        if(sum > threshold) break;
        sum += Math.ceil((i + mid - 1)/mid);
    }
    if(sum <= threshold) high = mid - 1;
    else low = mid + 1;
}
return low;
```

### 19. Capacity to ship packages within D days (Medium)
> [Link](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/) - Leetcode 1011

```
1. Take low = max_weight, mid = 0, high = summation_weightsm, ans = 0
2. Use binary search and find mid, use the helper function to get the number of days to ship the loads
3. If cnt > days in the helper then break and return cnt and shift the low -> mid since we need to ship in less days so increase the capacity
4. If cnt <= days in the helper then return cnt and shift the high -> mid since there is scope to finish the process fast
5. Return the ans
```

```java
public int helper(int wt[], int n, int days, int cap)
{
    int sum = 0, cnt = 1;
    for(int i=0; i<n; i++)
    {
        sum += wt[i];
        if(sum > cap)
        {
            cnt++;
            sum = wt[i];
        }
        if(cnt > days) break;
    }
    return cnt;
}
public int shipWithinDays(int[] weights, int days)
{
    int n = weights.length, low = 0, mid = 0, high = 0, ans = 0, cnt = 0;
    for(int i : weights) 
    {
        low = Math.max(low, i);
        high += i;
    }
    while(low <= high)
    {
        cnt = 0;
        mid = low + (high - low)/2;
        cnt = helper(weights, n, days, mid);
        if(cnt > days) low = mid + 1;
        else 
        {
            ans = mid;
            high = mid - 1;
        }
    }
    return ans;
}
```

### 20. Kth missing Positive number (Medium)
> [Link](https://leetcode.com/problems/kth-missing-positive-number/) - Leetcode 1539

```
1. Make three pointers, low, mid, high
2. Use binary search and find mid and missing (missing is number at idx - idx since the array will be sorted we will get to kn how many missing numbers are there)
3. If missing < k then shift the low -> mid since we need to find the kth missing number
4. If missing <= k then shift the high -> mid since there is scope to find the kth missing number
5. Return the ans
```

```java
int n = arr.length, low = 0, mid = 0, high = n-1, missing = 0;
while(low <= high)
{
    mid = low + (high - low)/2;
    missing = arr[mid] - (mid + 1);
    if(missing < k) low = mid + 1;
    else high = mid - 1;
}
return low + k;
```

### 21. Aggressive cows (Hard)
> [Link](https://takeuforward.org/plus/dsa/problems/aggressive-cows)

```
1. Make three pointers, low, mid, high
2. Use binary search and find mid
3. Use the placeCow function to find if the cows can be placed in the given distance
4. If can place in mid then shift the high -> mid since there is scope to place in less distance
5. If cannot place in mid then shift the low -> mid since we need to place in more distance
6. Return the ans
```

```java
public boolean placeCow(int nums[], int k, int dist)
{
    int n = nums.length, last = nums[0], cnt = 1;
    for(int i=0; i<n; i++)
    {
        if(nums[i] - last >= dist)
        {
            cnt++;
            last = nums[i];
        }
        if(cnt >= k) return true;
    }
    return false;
}
public int aggressiveCows(int[] nums, int k) 
{
    Arrays.sort(nums);
    int n = nums.length, low = 1, mid = 0, high = nums[n-1] - nums[0];
    boolean flag = false;
    while(low <= high)
    {
        mid = low + (high - low);
        flag = placeCow(nums, k, mid);
        if(flag) low = mid + 1;
        else high = mid - 1;
    }
    return high;
}
```

### 22. Book Allocation Problem (Hard)
> [Link](https://takeuforward.org/plus/dsa/problems/book-allocation-problem)

```
1. Make three pointers, low, mid, high
2. Use binary search and find mid
3. Use the allocateBook function to check if the number of pages can be allocated
4. If can allocate in mid then shift the high -> mid since there is scope to allocate in less pages
5. If cannot allocate in mid then shift the low -> mid since we need to allocate in more pages
6. Return the ans
```

```java
public boolean allocateBook(int nums[], int k, int pages)
{
    int n = nums.length, cnt = 1, sum = 0;
    for(int i=0; i<n; i++)    
    {
        if(sum + nums[i] > pages)
        {
            cnt++;
            sum = 0;
        }
        sum += nums[i];
        if(cnt > k) return false;
    }
    return true;
}
public int findPages(int[] nums, int m) 
{
    int n = nums.length, low = 1, mid = 0, high = 0, sum = 0;
    boolean flag = true;
    if(n < m) return -1;
    for(int i : nums)
    {
        low = Math.max(low, i);
        sum += i;
    }
    high = sum;
    while(low <= high)
    {
        mid = low + (high - low)/2;
        flag = allocateBook(nums, m, mid);
        if(flag) high = mid - 1;
        else low = mid + 1;
    }
    return low;
}
```

### 23. Split Array largest sum (hard)
> [Link](https://leetcode.com/problems/split-array-largest-sum/) - Leetcode 410

```
1. Make three pointers, low, mid, high
2. Use binary search and find mid
3. Use the checkSplit function to check if the sum can be allocated
4. If can allocate in mid then shift the high -> mid since there is scope to allocate in less pages
5. If cannot allocate in mid then shift the low -> mid since we need to allocate in more pages
6. Return the ans
```

```java
public boolean checkSplit(int nums[], int k, int largeSum)
{
    int n = nums.length, cnt = 1, sum = 0;
    for(int i=0; i<n; i++)
    {
        if(sum + nums[i] > largeSum)
        {
            cnt++;
            sum = 0;
        }
        sum += nums[i];
        if(cnt > k) return false;
    }
    return true;
}

public int splitArray(int[] nums, int k) 
{
    int n = nums.length, low = nums[0], mid = 0, high = 0;
    boolean flag = true;
    for(int i : nums) 
    {
        low = Math.max(low, i);
        high += i;
    }
    while(low <= high)
    {
        mid = low + (high - low)/2;
        flag = checkSplit(nums, k, mid);
        if(flag) high = mid - 1; 
        else low = mid + 1;
    }
    return low;
}
```

### 24. Painters Partition Problem (Medium)
> [Link](https://www.interviewbit.com/problems/painters-partition-problem/)

```
1. Make three pointers, low, mid, high
2. Use binary search and find mid
3. Use the helper function to check if the time can be allocated
4. If can allocate in mid then shift the high -> mid since there is scope to allocate in less time
5. If cannot allocate in mid then shift the low -> mid since we need to allocate in more time
6. Return the ans
```

```java
public boolean helper(int board[], long A, long B, long mid)
{
    long n = board.length, sum = 0, cnt = 1;
    for(int i=0; i<n; i++)
    {
        if(sum + board[i] * B > mid)
        {
            cnt++;
            sum = 0;
        }
        sum += (long)board[i] * B;
        if(cnt > A) return false;
    }
    return true;
}
public int paint(int A, int B, int[] C) 
{
    int n = C.length;
    long low = 0, mid = 0, high = 0, mod = 10000003;
    for(int i : C) 
    {
        low = Math.max(low, (long)i * B);
        high += (long)i * B;
    }
    while(low <= high)
    {
        mid = low + (high - low)/2;
        if(helper(C, A, B, mid)) high = mid - 1;
        else low = mid + 1;
    }
    return (int)(low % mod);
}
```

### 25. Minimize Max distance between Gas station (Hard)
> [Link](https://takeuforward.org/plus/dsa/problems/minimise-max-distance-to-gas-stations)

```
Pending
```

```java
Pending
```

### 26. Median of Two Sorted Arrays (Medium)
> [Link](https://leetcode.com/problems/median-of-two-sorted-arrays/) - Leetcode 4

```
1. Main logic to find the Median is to split the both array's into two parts such that this left1 <= right2 && left2 <= right1
2. So use binary search using low, mid and high pointers to find the cut index
3. cut1 from array1 using normal mid
4. cut2 from array2 using (total elements + 1)/2 - cut1
5. find the l1 and l2 value and r1 and r2
6. Compare them for median and return the value based on the even or odd length
7. Shift to right if the l1 > r2 or else shift to left
```

```java
public double medianLogic(int nums1[], int nums2[])
{
    int n1 = nums1.length, n2 = nums2.length;
    int low = 0, high = n1, cut1 = 0, cut2 = 0, l1 = 0, l2 = 0, r1 = 0, r2 = 0;
    boolean flag = (n1 + n2)%2 == 0 ? true : false;
    while(low <= high)
    {
        cut1 = low + (high - low)/2;
        cut2 = (n1 + n2 + 1)/2 - cut1;
        l1 = cut1 == 0 ? Integer.MIN_VALUE : nums1[cut1-1];
        l2 = cut2 == 0 ? Integer.MIN_VALUE : nums2[cut2-1];
        r1 = cut1 == n1 ? Integer.MAX_VALUE : nums1[cut1];
        r2 = cut2 == n2 ? Integer.MAX_VALUE : nums2[cut2];
        if(l1 <= r2 && l2 <= r1)
        {
            if(flag) return ((double)Math.max(l1, l2) + (double)Math.min(r1, r2))/2.0;
            else return (double)Math.max(l1, l2);
        }
        else if(l1 > r2) high = cut1 - 1;
        else low = cut1 + 1;
    }
    return 0.0;
}
public double findMedianSortedArrays(int[] nums1, int[] nums2) 
{
    if(nums1.length <= nums2.length) return medianLogic(nums1, nums2);
    else return medianLogic(nums2, nums1);
}
```

### 27. Kth element of 2 sorted arrays (Medium)
> [Link](https://takeuforward.org/plus/dsa/problems/kth-element-of-2-sorted-arrays)

```
1. 
```

```java
public int helper(int a[], int b[], int k)
{
    int n1 = a.length, n2 = b.length;
    int l1 = 0, l2 = 0, r1 = 0, r2 = 0, cut1 = 0, cut2 = 0, low = Math.max(0, k - n2), high = Math.min(k, n1);
    while(low <= high)
    {
        cut1 = low + (high - low)/2;
        cut2 = k - cut1;
        l1 = cut1 == 0 ? Integer.MIN_VALUE : a[cut1-1];
        l2 = cut2 == 0 ? Integer.MIN_VALUE : b[cut2-1];
        r1 = cut1 == n1 ? Integer.MAX_VALUE : a[cut1];
        r2 = cut2 == n2 ? Integer.MAX_VALUE : b[cut2];
        if(l1 <= r2 && l2 <= r1) return Math.max(l1, l2);
        else if(l1 > r2) high = cut1 - 1;
        else low = cut1 + 1;
    }

    return -1;
}
public int kthElement(int[] a, int[] b, int k) 
{
    int n1 = a.length, n2 = b.length;
    if(n1 <= n2) return helper(a, b, k);
    return helper(b, a, k);
}
```

### 28. Find row with maximum 1's
> [Link](https://takeuforward.org/plus/dsa/problems/find-row-with-maximum-1's)

```
1. Find the idx where we find the 1st occurance of 1 in the give row array and return the total length (size of array) - idx (if idx is -1) return -1 using binary search
2. So find this for all rows and keep track max value and row index and return the idx at the end if not then -1
```

```java
public int firstOccurance(int arr[])
{
    int n = arr.length, low = 0, mid = 0, high = n-1, ans = -1;
    while(low <= high)
    {
        mid = low + (high - low)/2;
        if(arr[mid] == 1)
        {
            ans = mid;
            high = mid - 1;
        }
        else if(arr[mid] < 1) low = mid + 1;
        else high = mid - 1;
    }
    if(ans == -1) return -1;
    return n - ans;
}
public int rowWithMax1s(int[][] mat) 
{
    int n = mat.length, max = 0, cnt1 = 0, idx = -1;
    for(int i=0; i<n; i++) 
    {
        cnt1 = firstOccurance(mat[i]);
        if(max < cnt1)
        {
            max = cnt1;
            idx = i;
        }
    }
    return idx;
}
```


### 29. Search in a 2D matrix
> [Link](https://leetcode.com/problems/search-a-2d-matrix/) - Leetcode 74

```
1. Simple binary search using math to simulate a flattened array
2. Low, mid and high find the mid and then to get the row idex and column index use (mid/m) and (mid%m) respectively
```

```java
int n = matrix.length, m = matrix[0].length, st = 0, end = (m*n) - 1, mid = 0, midElement = 0;
while(st <= end)
{
    mid = st + (end - st)/2;
    midElement = matrix[mid/m][mid%m];
    if(midElement == target) return true;
    else if(midElement > target) end = mid - 1;
    else st = mid + 1;
}
return false;
```

### 30. Search in a 2D matrix - II (Hard)
> [Link](https://leetcode.com/problems/search-a-2d-matrix-ii/) - Leetcode 240

```
1. Since the 2D matrix has each rows and cols sorted we can start from the top right corner and traverse accordingly
2. If the target element is greater then the current element shift down if smaller then shift left
```

```java
int n = matrix.length, m = matrix[0].length, i = 0, j = m - 1;
while(i < n && j >= 0)
{
    if(matrix[i][j] == target) return true;
    else if(target < matrix[i][j]) j--;
    else i++;
}
return false;
```


### 31. Find Peak Element - II (Medium)
> [Link](https://leetcode.com/problems/find-a-peak-element-ii/) - Leetcode 1901

```
1. This is brute force approach, there is an optimized binary search approach 
2. Where we find the mid column and find max in that column and check the neighbours (left and right) if the condition doesnt match we shift to that column which has max number in the neighbours
3. Repeat this for row also and we will find the peak element
4. Binary search will reduce the search space 
```

```java
int r = mat.length, c = mat[0].length, max = 0;
int arr[] = new int[2];
boolean flag = true;
for(int i=0; i<r; i++)
{
    for(int j=0; j<c; j++)
    {
        flag = true;
        max = mat[i][j];
        if(i > 0) if(max <= mat[i-1][j]) flag = false;
        if(i < r-1) if(max <= mat[i+1][j]) flag = false;
        if(j > 0) if(max <= mat[i][j-1]) flag = false;
        if(j < c-1) if(max <= mat[i][j+1]) flag = false;
        if(flag)
        {
            arr[0] = i;
            arr[1] = j;
            return arr;
        }
    }
}
return arr;
```

### 32. Matrix Median (Hard)
> [Link](https://takeuforward.org/plus/dsa/problems/matrix-median)

```
1. The core logic to find the median is to guess a number as a median and then get the count of elements where the elements are <= median since the rows are sorted we are using the binary search to find
2. Binary search to guess a median number from the range [1, maxNumberInMatrix]
3. Use a helper function to find the upper bound using binary search at each row for this guessed number and get the total count
4. cnt <= size/2 (size here is row * col) shift left else shift right
5. Return low since that will be the median
```

```java
public int countBefore(int mat[][], int k, int c)
{
    int low = 0, high = c-1, mid = 0, cnt = 0;
    for(int i[] : mat)
    {
        low = 0;
        high = c-1;
        mid = 0;
        while(low <= high)
        {
            mid = low + (high - low)/2;

            if(i[mid] > k) high = mid - 1;
            else low = mid + 1;
        }
        cnt += low;
    }
    return cnt;
}
public int findMedian(int[][] mat) 
{
    int r = mat.length, c = mat[0].length, low = 1, high = mat[0][0], mid = 0, size = r * c, cnt = 0;
    for(int i=0; i<r; i++) high = Math.max(high, mat[i][c-1]);
    while(low <= high)
    {
        mid = low + (high - low)/2;
        cnt = countBefore(mat, mid, c);
        if(cnt <= size/2) low = mid + 1;
        else high = mid - 1;
    }
    return low;
}
```

## Strings

### 1. Remove Outermost Parentheses (Easy)
> [Link](https://leetcode.com/problems/remove-outermost-parentheses/) - Leetcode 1021

```
1. Can be solved using Stack and without Stack also (Below solution is faster non-stack solution)
2. Traverse through the string as character by character
3. Check if its open parantheses bracket if so check the depth is depth > 0 then we have already taken care of the outer parentheses so take the copy of character
4. If depth is 0 then its outer most parantheses so we should skip it and not store in the array
5. If the character is close parantheses bracket then reduce the depth and check the depth > 0 then copy the character or else it will be the outermost paranthese so ignore it
```

```java
int n = s.length(), idx = 0, depth = 0;
char str[] = s.toCharArray();
char ans[] = new char[n];

for(char x : str)
{
    if(x == '(')
    {
        if(depth > 0) ans[idx++] = x;
        depth++;
    }
    else 
    {
        depth--;
        if(depth > 0) ans[idx++] = x;
    }
}

return new String(ans, 0, idx);
```

### 2. Reverse Words in a String (Medium)
> [Link](https://leetcode.com/problems/reverse-words-in-a-string/) - Leetcode 151

```
1. Convert the String to char array and then use 2 pointers to reconstruct the string with no spaces at start and end and just a single space in between words
2. Use 2 pointers, p2 to read the character if any non-space then write it to p1, else skip all space till you get a non-space for this p2 pointer
3. Check if p2 still inside the string range if so add a space at pointer p1
4. Once we cross the string length using p2 then our cleaned string length is p1 (p1 is next idx of the last character)
5. Reverse the whole string
6. Reverse each word one by one in this new cleaned reversed string
7. Return the string of length len
```

```java
public void reverse(char str[], int p1, int p2)
{
    char temp;
    while(p1 < p2)
    {
        temp = str[p1];
        str[p1] = str[p2];
        str[p2] = temp;
        p1++;
        p2--;
    }
}
public String reverseWords(String s)
{
    char str[] = s.toCharArray();
    int n = str.length;
    int p1 = 0, p2 = 0;
    char temp;
    while(p2 < n)
    {
        if(str[p2] != ' ') str[p1++] = str[p2++];
        else
        {
            while(p2 < n && str[p2] == ' ') p2++;
            if(p1 > 0 && p2 < n) str[p1++] = ' ';
        }
    }
    int len = p1;
    reverse(str, 0, len-1);
    p1 = 0;
    p2 = 0;
    while(p2 <= len)
    {
        while(p2 < len && str[p2] != ' ') p2++;
        reverse(str, p1, p2 - 1);
        p2++;
        p1 = p2;
    }
    return new String(str, 0, len);
}
```

### 3. Largest Odd Number in String (Easy)
> [Link](https://leetcode.com/problems/largest-odd-number-in-string/) - Leetcode 1903

```
1. Iterate from the max index and if any odd number is encountered then store the index and break from the loop and return the substring from 0 to index + 1
```

```java
int n = num.length();
boolean flag = false;
char x = ' ';
String res = "";
for(int i=n-1; i>=0; i--)    
{
    x = num.charAt(i);
    switch(x)
    {
        case '1':
            res = num.substring(0, i+1);
            flag = true;
            break;
        case '3':
            res = num.substring(0, i+1);
            flag = true;
            break;
        case '5':
            res = num.substring(0, i+1);
            flag = true;
            break;
        case '7':
            res = num.substring(0, i+1);
            flag = true;
            break;
        case '9':
            res = num.substring(0, i+1);
            flag = true;
            break;
    }
    if(flag) break;
}

return res;
```

### 4. Longest Common Prefix (Easy)
> [Link](https://leetcode.com/problems/longest-common-prefix/) - Leetcode 14

```
1. Either find the smallest word and run the loop for that smallest word length [or]
2. Take the 1st word and use the letters from it and check the same index in other words of the string if present then append it to the result and go to next index character from the 1st word.
```

```java
int n = strs.length, a = strs[0].length();
boolean flag = false; char x = ' ';
StringBuilder res = new StringBuilder("");
for(int i=0; i<a; i++)
{
    x = strs[0].charAt(i);
    for(String s : strs)
    {
        if(i < s.length() && s.charAt(i) == x) continue;
        else 
        {
            flag = true;
            break;
        }
    }
    if(flag) break;
    else res.append(x);
}
return res.toString();
```

### 5. Isomorphic Strings (Easy)
> [Link](https://leetcode.com/problems/isomorphic-strings/) - Leetcode 205

```
1. We have to map character from String s to character of String t in bidirectional mapping
2. So the main condition to check for proper mapping if a -> b and b -> a so when we encounter some other character (x) mapping to b we should check does b map to that character (x) or not if it doesnt map to (x) and it maps to some other character lets say (a) then they are not isomorphic strings
3. So check this is the main condition if(freq1[c1 - 0] != '\u0000' && freq1[c1 - 0] != c2 || freq2[c2 - 0] != '\u0000' && freq2[c2 - 0] != c1)
4. (a !-> null && a !-> b || b !-> null && b !-> a)
```

```java
int n = s.length();
char freq1[] = new char[256];
char freq2[] = new char[256];
char c1 = ' ', c2 = ' ';
for(int i=0; i<n; i++)
{
    c1 = s.charAt(i);
    c2 = t.charAt(i);
    if(freq1[c1 - 0] != '\u0000' && freq1[c1 - 0] != c2 || freq2[c2 - 0] != '\u0000' && freq2[c2 - 0] != c1 ) return false;
    freq1[c1 - 0] = c2;
    freq2[c2 - 0] = c1;
}
return true;
```

### 6. Rotate String (Easy)
> [Link](https://leetcode.com/problems/rotate-string/) - Leetcode 796

```
1. Append the same string to itself 
2. Then make substring and check at the start of each index till the start index + size of the target string
```

```java
if(s.length() != goal.length()) return false;
String con = s + s;
int n = goal.length();
for(int i=0; i<n; i++) if((con.substring(i,i+n)).compareTo(goal) == 0) return true;
return false;
```

### 7. Valid Anagram (Easy)
> [Link](https://leetcode.com/problems/valid-anagram/) - Leetcode 242

```
1. Make two separate frequency map for the characters in Source String and Target String
2. Check that frequency of each character from both the frequency map if all of them match then the are valid anagram or else not
```

```java
int len1 = s.length();
int len2 = t.length();
if(len1 != len2) return false;
int map[] = new int[26];
for(int i=0; i<len1; i++)
{
    int num = s.charAt(i) - 'a';
    map[num]++;
}
for(int i=0; i<len2; i++)
{
    int num = t.charAt(i) - 'a';
    map[num]--;
}
for(int i=0; i<26; i++) if(map[i] != 0) return false;
return true;
```

### 8. Sort Characters by frequency (Easy)
> [Link](https://leetcode.com/problems/sort-characters-by-frequency/) - Leetcode 451

```
1. Map a 2D frequency array of size 128 since the string can have lower case, upper case and digits only 
2. Store ASCII value as Int at idx 0 and cnt of the character at idx 1 in 2D Matrix
3. After building the frequency array sort the 2D map array in descending order based on the frequency values (idx 1)
4. Rebuild the String using this 2D map
```

```java
char str[] = s.toCharArray();
int n = str.length, idx = 0;
int map[][] = new int[128][2]; // 0 -> ascci int value && 1 -> freq cnt
for(int i=0; i<128; i++) map[i][0] = i;
for(char x : str) map[x - 0][1]++;
Arrays.sort(map, (a, b) -> Integer.compare(b[1], a[1]));
for(int i=0; i<128; i++) 
{
    while(map[i][1] > 0)
    {
        str[idx++] = (char)(map[i][0]);
        map[i][1]--;
    }
}
return new String(str);
```

### 9. Maximum Nesting Depth of the Parentheses (Easy)
> [Link](https://leetcode.com/problems/maximum-nesting-depth-of-the-parentheses/) - Leetcode 1614

```
1. Since the question explicity says valid paratheses string so we need not worry about the edge cases
2. If we encounter a open parantheses bracket then increase the depth count and update the max_depth
3. If we encounter a close parantheses bracket then decrease the depth count and in the end return the max_depth
```

```java
int n = s.length(), depth = 0, max_depth = 0;
char str[] = s.toCharArray();
for(int i=0; i<n; i++)
{
    if(str[i] == '(') 
    {
        depth++;
        max_depth = Math.max(max_depth, depth);
    }
    else if(str[i] == ')') depth--;
    else continue;
}
return max_depth;
```

### 10. Roman to Integer (Easy)
> [Link](https://leetcode.com/problems/roman-to-integer/) - Leetcode 13

```
1. Build a function to map Roman characters to their respective numbers
2. Iterate through the Roman String character by character and get the Int value of for character at current and next index
3. If Int value of current idx character is > Int value of next idx character then add (current) it to result
4. If Int value of current idx character is > Int value of next idx character then subtract (current) it from result
5. If a lower value number is before higher value then subtract (current value) or else add (current value)
```

```java
public int getIntFromRoman(char x)
{
    switch(x)
    {
        case 'I': 
            return 1;
        case 'V': 
            return 5;
        case 'X': 
            return 10;
        case 'L': 
            return 50;
        case 'C': 
            return 100;
        case 'D': 
            return 500;
        case 'M': 
            return 1000;
    }
    return 0;
}
public int romanToInt(String s) 
{
    int n = s.length(), curr = 0, next = 0, res = 0;
    for(int i=0; i<n-1; i++)
    {
        curr = getIntFromRoman(s.charAt(i));
        next = getIntFromRoman(s.charAt(i+1));

        if(curr < next) res -= curr;
        else res += curr;
    }
    res += getIntFromRoman(s.charAt(n-1));
    return res;
}
```

### 11. String to Integer (atoi) (Medium)
> [Link](https://leetcode.com/problems/string-to-integer-atoi/) - Leetcode 8

```
Pending
```

```java
Pending
```

### 13. Largest Palindromic Substring (Medium)
> [Link](https://leetcode.com/problems/longest-palindromic-substring/) - Leetcode 5

```
1. Here we use expand from middle and check for palindrome concept rather then find substrings and check for palindrome
2. Use a while loop to iterate from idx 0 to n-1 (here i is nothing but the assumed center of the possible palindrome)
3. Check if we can expand the center to the right side (possible Even length palindrome as well as skip duplicates)
4. Update the value of i for efficient palindrome substring checks
5. Expand left and right making sure pointers are within the string index range and characters are matching
6. Update the start pointer (sp) and end pointer (end) if the new palindrome index difference is greater
7. Return the substring from index `sp` to `end+1`
```

```java
int n = s.length(), i = 0, j = 0, sp = 0, end = 0, left = 0, right = 0;
char str[] = s.toCharArray();
while(i < n)
{
    left = i;
    right = i;
    while(right + 1 < n && str[right + 1] == str[i]) right++;
    i = right + 1;
    while((left - 1) >= 0 && (right + 1) < n && str[left - 1] == str[right + 1])
    {
        left--;
        right++;
    }
    if(right - left > end - sp)
    {
        sp = left;
        end = right;
    }
}
return s.substring(sp, end+1);
```
