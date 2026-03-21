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
> [Link]()
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
