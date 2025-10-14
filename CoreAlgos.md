# Core Algorithms Algorithms & Techniques Cheatsheet

## 🧩 Arrays

| #   | Algorithm / Technique             | Purpose                                        |
| --- | --------------------------------- | ---------------------------------------------- |
| 1   | Kadane’s Algorithm                | Maximum subarray sum                           |
| 2   | Moore’s Voting Algorithm          | Find majority element (element cnt > n/2)      |
| 3   | Moore’s Voting Algorithm          | Find majority element (element cnt > n/3)      |
| 4   | Prefix Sum                        | Range sum queries, subarray problems           |
| 5   | Dutch National Flag Algorithm     | Sort 0s, 1s, 2s (3-way partition)              |
| 6   | Cyclic Sort                       | Find missing / duplicate numbers in range 1..n |
| 7   | Two Pointers Technique            | Remove duplicates                              |
| 8   | Merge Intervals Algorithm         | Overlapping intervals merge                    |
| 9   | Two Pointers Technique Additional | Move zeros                                     |
| 10  | Binary Search (on array)          | Searching / min-max optimization               |
| 11  | Rotate / Reverse Algorithm        | Array rotation, reversing sections             |
| 12  | Prefix XOR / Prefix Min/Max       | For subarray XOR/sum-related problems          |

---

## 🪟 Sliding Window

| #   | Algorithm / Technique             | Purpose                                  |
| --- | --------------------------------- | ---------------------------------------- |
| 1   | Fixed-size Sliding Window         | Max/min/average sum in fixed window      |
| 2   | Variable-size Window              | Longest/shortest subarray with condition |
| 3   | Deque-based Sliding Window        | Sliding window maximum/minimum           |
| 4   | Anagram Window with HashMap       | Count substrings with matching frequency |
| 5   | Two-pointer Shrink-Expand Pattern | Common in substring problems             |

---

## 🔗 Linked List

| #   | Algorithm / Technique           | Purpose                          |
| --- | ------------------------------- | -------------------------------- |
| 1   | Floyd’s Cycle Detection         | Detect cycle in a linked list    |
| 2   | Reverse Linked List             | Iterative and recursive reversal |
| 3   | Merge Two Sorted Lists          | Common merge step in merge sort  |
| 4   | Find Middle (Fast-Slow pointer) | Split / detect mid               |
| 5   | Remove Nth Node from End        | Two-pointer gap approach         |
| 6   | Palindrome Check                | Compare halves                   |
| 7   | Merge Sort for Linked List      | Sorting without extra space      |
| 8   | Reorder List / Odd-Even List    | Structural reordering            |

---

## 🏔️ Heap / Priority Queue

| #   | Algorithm / Technique         | Purpose                         |
| --- | ----------------------------- | ------------------------------- |
| 1   | Heapify (Build Heap)          | Convert array to heap           |
| 2   | Heap Sort                     | Sort using heap                 |
| 3   | Kth Largest/Smallest          | Maintain min/max heap of size k |
| 4   | Top K Frequent Elements       | Use hashmap + heap              |
| 5   | Merge K Sorted Lists / Arrays | Use min-heap                    |
| 6   | Sliding Window Median         | Two heaps balancing             |
| 7   | Priority Queue Scheduling     | Greedy + heap problems          |

---

## 🧠 Hashmap / Hashing

| #   | Algorithm / Technique                | Purpose                               |
| --- | ------------------------------------ | ------------------------------------- |
| 1   | Two Sum Algorithm                    | Use hashmap for complement            |
| 2   | Prefix Sum + HashMap                 | Subarray sum equals K                 |
| 3   | Count Frequency / Distinct Elements  | Hash counting                         |
| 4   | Group Anagrams                       | Key as sorted string or count         |
| 5   | Longest Substring Without Repetition | HashSet + window                      |
| 6   | LRU Cache Algorithm                  | HashMap + Doubly Linked List          |
| 7   | HashMap-based Sliding Window         | Count frequency in substring problems |

---

## 🌳 Trees

| #   | Algorithm / Technique                  | Purpose                                   |
| --- | -------------------------------------- | ----------------------------------------- |
| 1   | DFS Traversal (Pre/In/Post)            | Recursive exploration                     |
| 2   | BFS (Level Order Traversal)            | Queue-based                               |
| 3   | Diameter of Binary Tree                | Height + recursive traversal              |
| 4   | Lowest Common Ancestor (LCA)           | Recursive or binary lifting               |
| 5   | Inorder Successor / Predecessor        | BST logic                                 |
| 6   | Serialize / Deserialize                | Tree to string and back                   |
| 7   | Morris Traversal                       | Inorder traversal without recursion/stack |
| 8   | Balanced Tree Check                    | Recursive height balance                  |
| 9   | Boundary / Vertical / Zigzag Traversal | BFS + structure logic                     |
| 10  | BST Operations (Insert/Delete/Search)  | Basic recursive logic                     |

---

## 🌐 Graphs

| #   | Algorithm / Technique                 | Purpose                                |
| --- | ------------------------------------- | -------------------------------------- |
| 1   | BFS (Breadth First Search)            | Shortest path (unweighted)             |
| 2   | DFS (Depth First Search)              | Connected components / cycle           |
| 3   | Dijkstra’s Algorithm                  | Shortest path (weighted, non-negative) |
| 4   | Bellman-Ford Algorithm                | Shortest path (negative edges)         |
| 5   | Floyd-Warshall Algorithm              | All-pairs shortest path                |
| 6   | Topological Sort (Kahn’s / DFS)       | DAG ordering                           |
| 7   | Union-Find / DSU                      | Cycle detection, Kruskal’s MST         |
| 8   | Kruskal’s Algorithm                   | MST using DSU                          |
| 9   | Prim’s Algorithm                      | MST using PQ                           |
| 10  | Tarjan’s Algorithm                    | SCCs / bridges / articulation points   |
| 11  | Kosaraju’s Algorithm                  | Strongly Connected Components          |
| 12  | Cycle Detection (Directed/Undirected) | DFS or DSU based                       |

---

## 🔁 Recursion / Backtracking

| #   | Algorithm / Technique               | Purpose                         |
| --- | ----------------------------------- | ------------------------------- |
| 1   | Subset Generation                   | Power set                       |
| 2   | Permutation Generation              | All orderings                   |
| 3   | Combination Sum / N-Queens / Sudoku | Constraint backtracking         |
| 4   | Rat in a Maze / Word Search         | Path finding using recursion    |
| 5   | Backtracking Template               | For all constraint satisfaction |

---

## 📈 Dynamic Programming

| #   | Algorithm / Technique                 | Purpose               |
| --- | ------------------------------------- | --------------------- |
| 1   | Fibonacci / Climb Stairs              | Basic DP introduction |
| 2   | Kadane’s Algorithm (DP)               | Max subarray sum      |
| 3   | Longest Common Subsequence (LCS)      | String DP             |
| 4   | Longest Increasing Subsequence (LIS)  | O(n²) or O(n log n)   |
| 5   | 0/1 Knapsack                          | Classic DP problem    |
| 6   | Coin Change (min / count)             | DP on amount          |
| 7   | Matrix Path (min / unique)            | Grid DP               |
| 8   | Palindrome Partitioning / Subsequence | DP with string cuts   |
| 9   | Edit Distance (Levenshtein)           | String transform DP   |
| 10  | Subset Sum / Partition Equal Subset   | Boolean DP            |

---

## ⚙️ Binary Search & Math

| #   | Algorithm / Technique          | Purpose                   |
| --- | ------------------------------ | ------------------------- |
| 1   | Classic Binary Search          | On sorted arrays          |
| 2   | Binary Search on Answer        | Min/Max feasible solution |
| 3   | Find First/Last Occurrence     | Lower/upper bound logic   |
| 4   | Square Root (Binary Search)    | Newton/Binary approach    |
| 5   | Exponentiation by Squaring     | Fast power                |
| 6   | GCD / LCM (Euclid’s Algorithm) | Number theory basics      |
| 7   | Sieve of Eratosthenes          | Prime generation          |
| 8   | Modular Exponentiation         | For large powers mod m    |

---

## 🧮 Stack / Queue

| #   | Algorithm / Technique                  | Purpose                       |
| --- | -------------------------------------- | ----------------------------- |
| 1   | Next Greater Element (Monotonic Stack) | For each element              |
| 2   | Valid Parentheses                      | Stack matching                |
| 3   | Infix → Postfix Conversion             | Expression evaluation         |
| 4   | Evaluate Postfix Expression            | Reverse Polish notation       |
| 5   | Largest Rectangle in Histogram         | Monotonic stack               |
| 6   | Trapping Rain Water                    | Two pointers / stack approach |

---

## 💡 Bit Manipulation

| #   | Algorithm / Technique        | Purpose                  |
| --- | ---------------------------- | ------------------------ |
| 1   | Brian Kernighan’s Algorithm  | Count set bits           |
| 2   | Single Number using XOR      | Unique element detection |
| 3   | Subset Generation using Bits | Bitmask technique        |
| 4   | Power of Two Check           | (n & (n-1)) == 0         |
| 5   | XOR Pair / Max XOR Trie      | Bitwise trie             |
| 6   | Swap using XOR               | Trick questions          |

---

# 🧩 Arrays Algorithms

This covers the **most common algorithms** related to Arrays that are frequently used in DSA questions. Each section includes:

* **Explanation** of the algorithm
* **Java Function Code**
* **Example** to understand it clearly

---

## 1️⃣ Kadane's Algorithm — Maximum Subarray Sum

**Purpose:** Find the contiguous subarray with the maximum sum.

**Logic:**

* Iterate the array, keeping track of the current subarray sum.
* If current sum < 0, reset it to 0.
* Keep track of the maximum sum seen so far.

**Java Code:**

```java
public class KadaneAlgorithm {
    public static int maxSubArray(int[] nums) {
        int maxSum = Integer.MIN_VALUE;
        int currentSum = 0;

        for (int num : nums) {
            currentSum += num;
            maxSum = Math.max(maxSum, currentSum);
            if (currentSum < 0) currentSum = 0;
        }
        return maxSum;
    }

    public static void main(String[] args) {
        int[] arr = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
        System.out.println("Max Subarray Sum: " + maxSubArray(arr)); // Output: 6
    }
}
```

**Example:**

```
Array = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
Max Subarray = [4, -1, 2, 1] → Sum = 6
```

---

## 2️⃣ Moore’s Voting Algorithm — Majority Element

**Purpose:** Find the element that appears more than ⌊n/2⌋ times.

**Logic:**

* Use a candidate and count variable.
* When count = 0, choose new candidate.
* Increase count if current == candidate, else decrease.

**Java Code:**

```java
public class MooreVoting {
    public static int majorityElement(int[] nums) {
        int candidate = 0, count = 0;
        for (int num : nums) {
            if (count == 0) candidate = num;
            count += (num == candidate) ? 1 : -1;
        }
        return candidate;
    }

    public static void main(String[] args) {
        int[] arr = {2, 2, 1, 1, 1, 2, 2};
        System.out.println("Majority Element: " + majorityElement(arr)); // Output: 2
    }
}
```

**Example:**

```
Array = [2, 2, 1, 1, 1, 2, 2]
Majority Element = 2
```

---

## 3️⃣ Moore’s Voting Algorithm — Majority Elements (n/3)

**Purpose**: Find all elements that appear more than ⌊n/3⌋ times.

**Logic:**

* Use two candidates and their respective counts.
* If the current element matches either candidate, increment the corresponding count.
* If not, decrement both counts. If a count reaches zero, replace the candidate.
* A second pass is required to verify the actual counts of the candidates.

**Java Code:**

```java
public class MooreVotingN3 {
    public static List<Integer> majorityElement(int[] nums) {
        List<Integer> result = new Array:
        int candidate1 = 0, candidate2 = 0;
        int count1 = 0, count2 = 0;

        for (int num : nums) {
            if (num == candidate1) {
                count1++;
            } else if (num == candidate2) {
                count2++;
            } else if (count1 == 0) {
                candidate1 = num;
                count1 = 1;
            } else if (count2 == 0) {
                candidate2 = num;
                count2 = 1;
            } else {
                count1--;
                count2--;
            }
        }

        count1 = 0;
        count2 = 0;
        for (int num : nums) {
            if (num == candidate1) count1++;
            else if (num == candidate2) count2++;
        }

        if (count1 > nums.length / 3) result.add(candidate1);
        if (count2 > nums.length / 3) result.add(candidate2);

        return result;
    }

    public static void main(String[] args) {
        int[] arr = {3, 2, 3, 1, 2, 2, 3, 3, 3};
        System.out.println("Majority Elements: " + majorityElement(arr));
    }
}
```

**Example:**
``` 
CopyArray = [3, 2, 3, 1, 2, 2, 3, 3, 3]
Majority Elements = [3, 2]
```

## 4️⃣ Prefix Sum — Range Sum Queries

**Purpose:** Quickly calculate sum of elements in range [L, R].

**Logic:**

* Build prefixSum[] where prefix[i] = prefix[i-1] + arr[i].
* Range sum = prefix[R] - prefix[L-1].

**Java Code:**

```java
public class PrefixSumArray {
    public static int[] buildPrefixSum(int[] arr) {
        int[] prefix = new int[arr.length];
        prefix[0] = arr[0];
        for (int i = 1; i < arr.length; i++) {
            prefix[i] = prefix[i - 1] + arr[i];
        }
        return prefix;
    }

    public static int rangeSum(int[] prefix, int L, int R) {
        if (L == 0) return prefix[R];
        return prefix[R] - prefix[L - 1];
    }

    public static void main(String[] args) {
        int[] arr = {2, 4, 6, 8, 10};
        int[] prefix = buildPrefixSum(arr);
        System.out.println(rangeSum(prefix, 1, 3)); // Output: 18
    }
}
```

**Example:**

```
Array = [2, 4, 6, 8, 10]
Range [1,3] → 4 + 6 + 8 = 18
```

---

## 5️⃣ Dutch National Flag Algorithm — Sort 0s, 1s, 2s

**Purpose:** Sort an array of 0s, 1s, and 2s in one pass.

**Logic:**

* Maintain 3 pointers → low, mid, high.
* Swap based on the mid element value.

**Java Code:**

```java
public class DutchFlag {
    public static void sortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.length - 1;

        while (mid <= high) {
            if (nums[mid] == 0) {
                int temp = nums[low];
                nums[low++] = nums[mid];
                nums[mid++] = temp;
            } else if (nums[mid] == 1) {
                mid++;
            } else {
                int temp = nums[mid];
                nums[mid] = nums[high];
                nums[high--] = temp;
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {2, 0, 2, 1, 1, 0};
        sortColors(arr);
        System.out.print("Sorted: ");
        for (int n : arr) System.out.print(n + " "); // Output: 0 0 1 1 2 2
    }
}
```

**Example:**

```
Input: [2, 0, 2, 1, 1, 0]
Output: [0, 0, 1, 1, 2, 2]
```

---

## 6️⃣ Cyclic Sort — Find Missing Numbers in Range [1..n]

**Purpose:** Efficiently detect missing or duplicate numbers.

**Logic:**

* Place each element at its correct index (arr[i] == i+1).
* After sorting, the first index with mismatch gives the missing number.

**Java Code:**

```java
public class CyclicSortMissing {
    public static int findMissingNumber(int[] nums) {
        int i = 0;
        while (i < nums.length) {
            int correct = nums[i] - 1;
            if (nums[i] > 0 && nums[i] <= nums.length && nums[i] != nums[correct]) {
                int temp = nums[i];
                nums[i] = nums[correct];
                nums[correct] = temp;
            } else i++;
        }

        for (i = 0; i < nums.length; i++) {
            if (nums[i] != i + 1) return i + 1;
        }
        return nums.length + 1;
    }

    public static void main(String[] args) {
        int[] arr = {3, 4, -1, 1};
        System.out.println("Missing Number: " + findMissingNumber(arr)); // Output: 2
    }
}
```

**Example:**

```
Array = [3, 4, -1, 1]
Missing Number = 2
```

---

## 7️⃣ Two Pointers — Remove Duplicates from Sorted Array

**Purpose:** In-place removal of duplicates from sorted array.

**Logic:**

* Keep one pointer for unique position, and one for scanning.

**Java Code:**

```java
public class TwoPointersUnique {
    public static int removeDuplicates(int[] nums) {
        if (nums.length == 0) return 0;
        int i = 0;
        for (int j = 1; j < nums.length; j++) {
            if (nums[j] != nums[i]) {
                i++;
                nums[i] = nums[j];
            }
        }
        return i + 1;
    }

    public static void main(String[] args) {
        int[] arr = {1, 1, 2, 2, 3, 4, 4};
        int len = removeDuplicates(arr);
        System.out.print("Unique Array: ");
        for (int i = 0; i < len; i++) System.out.print(arr[i] + " "); // Output: 1 2 3 4
    }
}
```

**Example:**

```
Input: [1,1,2,2,3,4,4]
Output: [1,2,3,4]
```

---

## 8️⃣ Merge Intervals — Merge Overlapping Intervals

**Purpose:** Given a list of intervals, merge all overlapping intervals and return the merged list.

**Logic:**

* Sort intervals by start time.
* Iterate and merge current interval with the last merged interval if they overlap.

**Java Code:**

```java
import java.util.*;

public class MergeIntervals {
    public static int[][] merge(int[][] intervals) {
        if (intervals.length <= 1) return intervals;
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]));
        List<int[]> merged = new ArrayList<>();
        int[] current = intervals[0];
        merged.add(current);
        for (int[] interval : intervals) {
            if (interval[0] <= current[1]) { // overlap
                current[1] = Math.max(current[1], interval[1]);
            } else {
                current = interval;
                merged.add(current);
            }
        }
        return merged.toArray(new int[merged.size()][]);
    }

    public static void main(String[] args) {
        int[][] intervals = {{1,3},{2,6},{8,10},{15,18}};
        int[][] res = merge(intervals);
        System.out.print("Merged Intervals: ");
        for (int[] in : res) System.out.print(Arrays.toString(in) + " "); // [[1,6], [8,10], [15,18]]
    }
}
```

**Example:**

```
Input: [[1,3],[2,6],[8,10],[15,18]]
Output: [[1,6],[8,10],[15,18]]
```

---

## 9️⃣ Two Pointers Technique — (Additional Patterns)

**Purpose:** General-purpose method for problems on sorted arrays or when using two indices to scan from both ends.

**Logic:**

* Use two indices (left, right) and move them based on conditions to find pairs, remove elements, or partition array.

**Example Problems & Java Snippets:**

**Pair Sum in Sorted Array (target)**

```java
public class TwoSumSorted {
    public static int[] twoSum(int[] nums, int target) {
        int l = 0, r = nums.length - 1;
        while (l < r) {
            int sum = nums[l] + nums[r];
            if (sum == target) return new int[]{l, r};
            else if (sum < target) l++;
            else r--;
        }
        return new int[]{-1, -1};
    }
}
```

**Move Zeroes (stable) — maintain position for non-zero**

```java
public class MoveZeroes {
    public static void moveZeroes(int[] nums) {
        int pos = 0; // position to place next non-zero
        for (int num : nums) {
            if (num != 0) nums[pos++] = num;
        }
        while (pos < nums.length) nums[pos++] = 0;
    }
}
```

---

## 🔟 Binary Search (on array) — Classic & Variants

**Purpose:** Search in a sorted array; also used as a template for finding boundaries or searching over monotonic predicate (binary search on answer).

**Logic:**

* Maintain low and high pointers; repeatedly check mid.

**Java Code (Find first occurrence of target):**

```java
public class BinarySearchVariants {
    public static int findFirst(int[] nums, int target) {
        int l = 0, r = nums.length - 1;
        int ans = -1;
        while (l <= r) {
            int mid = l + (r - l) / 2;
            if (nums[mid] == target) { ans = mid; r = mid - 1; }
            else if (nums[mid] < target) l = mid + 1;
            else r = mid - 1;
        }
        return ans;
    }
}
```

**Binary Search on Answer (example):** find smallest capacity that ships packages within D days is solved by binary searching over capacities and checking feasibility.

---

## 1️⃣1️⃣ Rotate / Reverse Algorithm — Rotate Array by k

**Purpose:** Rotate an array to the right by `k` steps in-place.

**Logic:**

* Reverse the whole array, reverse first k elements, then reverse remaining n-k elements.

**Java Code:**

```java
public class RotateArray {
    public static void rotate(int[] nums, int k) {
        k = k % nums.length;
        reverse(nums, 0, nums.length - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, nums.length - 1);
    }

    private static void reverse(int[] nums, int i, int j) {
        while (i < j) {
            int t = nums[i]; nums[i] = nums[j]; nums[j] = t;
            i++; j--;
        }
    }

    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5,6,7};
        rotate(arr, 3);
        for (int n : arr) System.out.print(n + " "); // Output: 5 6 7 1 2 3 4
    }
}
```

**Example:**

```
Input: [1,2,3,4,5,6,7], k=3
Output: [5,6,7,1,2,3,4]
```

---

## 1️⃣2️⃣ Prefix XOR / Prefix Min/Max — Useful Prefix-Based Tricks

**Purpose:** Support fast queries or compute properties of subarrays (XOR, min, max) using prefix accumulators.

**Logic & Examples:**

**Prefix XOR (find subarray with given XOR)**

* Build prefixXor where prefixXor[i] = arr[0] ^ ... ^ arr[i].
* XOR of subarray [L..R] = prefixXor[R] ^ (L>0 ? prefixXor[L-1] : 0).

**Java Code (Count subarrays with given XOR):**

```java
import java.util.*;

public class SubarrayXor {
    public static int countSubarraysWithXor(int[] arr, int target) {
        Map<Integer, Integer> freq = new HashMap<>();
        int prefix = 0, count = 0;
        freq.put(0, 1);
        for (int num : arr) {
            prefix ^= num;
            int need = prefix ^ target;
            count += freq.getOrDefault(need, 0);
            freq.put(prefix, freq.getOrDefault(prefix, 0) + 1);
        }
        return count;
    }

    public static void main(String[] args) {
        int[] arr = {4,2,2,6,4};
        System.out.println(countSubarraysWithXor(arr, 6)); // Output depends on array
    }
}
```

**Prefix Min/Max**

* Useful for answering range min/max queries if combined with suffix arrays or segment trees. Build prefixMax[i] = max(prefixMax[i-1], arr[i]) and similar for prefixMin.

---


# 🪟 Sliding Window Algorithms

This covers the **core sliding window algorithms and patterns** used in array and string problems. Each section includes:

* **Explanation** of the algorithm
* **Java Function Code**
* **Example** to understand it clearly

---

## 1️⃣ Fixed Size Sliding Window — Maximum Sum Subarray of Size K

**Purpose:** Find the subarray of size `k` having the maximum sum.

**Logic:**

* Compute the sum of the first `k` elements.
* Slide the window by 1 step: subtract the element that goes out and add the element that comes in.

**Java Code:**

```java
public class FixedWindowMaxSum {
    public static int maxSum(int[] arr, int k) {
        int windowSum = 0, maxSum = 0;
        for (int i = 0; i < k; i++) windowSum += arr[i];
        maxSum = windowSum;

        for (int i = k; i < arr.length; i++) {
            windowSum += arr[i] - arr[i - k];
            maxSum = Math.max(maxSum, windowSum);
        }
        return maxSum;
    }

    public static void main(String[] args) {
        int[] arr = {2, 1, 5, 1, 3, 2};
        int k = 3;
        System.out.println("Max Sum of size " + k + ": " + maxSum(arr, k)); // Output: 9
    }
}
```

**Example:**

```
Array = [2,1,5,1,3,2], k=3
Windows: [2,1,5]=8, [1,5,1]=7, [5,1,3]=9, [1,3,2]=6
Max Sum = 9
```

---

## 2️⃣ Variable Size Window — Longest Subarray with Sum ≤ K

**Purpose:** Find the longest subarray whose sum is less than or equal to K.

**Logic:**

* Expand the window by adding elements.
* Shrink from the left while sum > K.

**Java Code:**

```java
public class VariableWindowSumK {
    public static int longestSubArraySumK(int[] arr, int k) {
        int left = 0, sum = 0, maxLen = 0;

        for (int right = 0; right < arr.length; right++) {
            sum += arr[right];
            while (sum > k) {
                sum -= arr[left++];
            }
            maxLen = Math.max(maxLen, right - left + 1);
        }
        return maxLen;
    }

    public static void main(String[] args) {
        int[] arr = {4, 1, 1, 1, 2, 3, 5};
        int k = 5;
        System.out.println("Longest Subarray ≤ " + k + ": " + longestSubArraySumK(arr, k)); // Output: 4
    }
}
```

**Example:**

```
Array = [4,1,1,1,2,3,5], K=5
Longest Subarray = [1,1,1,2] → length 4
```

---

## 3️⃣ Sliding Window Maximum — Using Deque

**Purpose:** Find the maximum element in every window of size `k`.

**Logic:**

* Use a deque to store indices of useful elements in current window.
* Remove smaller elements as they are useless.

**Java Code:**

```java
import java.util.*;

public class SlidingWindowMaximum {
    public static int[] maxSlidingWindow(int[] nums, int k) {
        Deque<Integer> dq = new LinkedList<>();
        int[] result = new int[nums.length - k + 1];
        int index = 0;

        for (int i = 0; i < nums.length; i++) {
            // Remove indices outside the current window
            if (!dq.isEmpty() && dq.peekFirst() == i - k) dq.pollFirst();

            // Remove smaller values from back
            while (!dq.isEmpty() && nums[dq.peekLast()] < nums[i]) dq.pollLast();

            dq.offerLast(i);

            // Record result when window is valid
            if (i >= k - 1) result[index++] = nums[dq.peekFirst()];
        }
        return result;
    }

    public static void main(String[] args) {
        int[] arr = {1,3,-1,-3,5,3,6,7};
        int k = 3;
        int[] res = maxSlidingWindow(arr, k);
        System.out.print("Max in each window: ");
        for (int n : res) System.out.print(n + " "); // Output: 3 3 5 5 6 7
    }
}
```

**Example:**

```
Array = [1,3,-1,-3,5,3,6,7], k=3
Windows → Max: [3,3,5,5,6,7]
```

---

## 4️⃣ Count of Anagrams in String — Sliding Window + HashMap

**Purpose:** Count number of substrings that are anagrams of a given pattern.

**Logic:**

* Maintain frequency map of pattern.
* Slide window and compare frequency.

**Java Code:**

```java
import java.util.*;

public class CountAnagrams {
    public static int countAnagrams(String text, String pattern) {
        Map<Character, Integer> map = new HashMap<>();
        for (char c : pattern.toCharArray()) map.put(c, map.getOrDefault(c, 0) + 1);

        int count = map.size();
        int i = 0, j = 0, ans = 0;
        int k = pattern.length();

        while (j < text.length()) {
            char c = text.charAt(j);
            if (map.containsKey(c)) {
                map.put(c, map.get(c) - 1);
                if (map.get(c) == 0) count--;
            }

            if (j - i + 1 < k) j++;
            else if (j - i + 1 == k) {
                if (count == 0) ans++;

                char leftChar = text.charAt(i);
                if (map.containsKey(leftChar)) {
                    if (map.get(leftChar) == 0) count++;
                    map.put(leftChar, map.get(leftChar) + 1);
                }
                i++; j++;
            }
        }
        return ans;
    }

    public static void main(String[] args) {
        String text = "forxxorfxdofr";
        String pattern = "for";
        System.out.println("Anagram Count: " + countAnagrams(text, pattern)); // Output: 3
    }
}
```

**Example:**

```
Text = "forxxorfxdofr", Pattern = "for"
Anagrams found at → [for, orf, ofr] → Count = 3
```

---

## 5️⃣ Longest Substring Without Repeating Characters

**Purpose:** Find the length of the longest substring without repeating characters.

**Logic:**

* Use a HashSet or HashMap to track characters in current window.
* If duplicate found, shrink window from left.

**Java Code:**

```java
import java.util.*;

public class LongestUniqueSubstring {
    public static int lengthOfLongestSubstring(String s) {
        Set<Character> set = new HashSet<>();
        int left = 0, maxLen = 0;

        for (int right = 0; right < s.length(); right++) {
            while (set.contains(s.charAt(right))) {
                set.remove(s.charAt(left++));
            }
            set.add(s.charAt(right));
            maxLen = Math.max(maxLen, right - left + 1);
        }
        return maxLen;
    }

    public static void main(String[] args) {
        String s = "abcabcbb";
        System.out.println("Longest Unique Substring Length: " + lengthOfLongestSubstring(s)); // Output: 3
    }
}
```

**Example:**

```
String = "abcabcbb"
Longest Unique Substring = "abc" → length = 3
```

---

✅ **Next Up:** Linked List Algorithms (Floyd’s Cycle Detection, Reverse, Merge, etc.)


---

# Linked List Algorithms

This covers the **core Linked list algorithms and patterns** used in array and string problems. Each section includes:

* **Explanation** of the algorithm
* **Java Function Code**
* **Example** to understand it clearly

---

## 1️⃣ Floyd’s Cycle Detection (Tortoise & Hare)

**Purpose:** Detect if a cycle exists in a linked list.

**Logic:** Use two pointers moving at different speeds. If they meet, a cycle exists.

```java
class ListNode {
    int val;
    ListNode next;
    ListNode(int x) { val = x; next = null; }
}

public class FloydCycleDetection {
    public static boolean hasCycle(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
    }
}
```

**Example:** Detect cycle in linked list using two pointers.

---

## 2️⃣ Reverse Linked List (Iterative & Recursive)

**Iterative Approach:**

```java
public class ReverseList {
    public static ListNode reverseIterative(ListNode head) {
        ListNode prev = null, curr = head;
        while (curr != null) {
            ListNode next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }
        return prev;
    }
}
```

**Recursive Approach:**

```java
public static ListNode reverseRecursive(ListNode head) {
    if (head == null || head.next == null) return head;
    ListNode newHead = reverseRecursive(head.next);
    head.next.next = head;
    head.next = null;
    return newHead;
}
```

---

## 3️⃣ Merge Two Sorted Lists

**Purpose:** Merge two sorted linked lists into one sorted list.

```java
public class MergeSortedLists {
    public static ListNode merge(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode tail = dummy;
        while (l1 != null && l2 != null) {
            if (l1.val < l2.val) {
                tail.next = l1;
                l1 = l1.next;
            } else {
                tail.next = l2;
                l2 = l2.next;
            }
            tail = tail.next;
        }
        tail.next = (l1 != null) ? l1 : l2;
        return dummy.next;
    }
}
```

---

## 4️⃣ Find Middle Node (Fast & Slow Pointers)

```java
public class MiddleOfList {
    public static ListNode findMiddle(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow; // middle node
    }
}
```

**Example:** Used in palindrome check or splitting for merge sort.

---

## 5️⃣ Remove Nth Node from End

**Two-pointer gap approach:**

```java
public class RemoveNthNode {
    public static ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode first = dummy, second = dummy;
        for (int i = 0; i <= n; i++) first = first.next;
        while (first != null) {
            first = first.next;
            second = second.next;
        }
        second.next = second.next.next;
        return dummy.next;
    }
}
```

---

## 6️⃣ Palindrome Check

**Logic:** Find middle, reverse second half, compare both halves.

```java
public class PalindromeList {
    public static boolean isPalindrome(ListNode head) {
        if (head == null || head.next == null) return true;
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        ListNode secondHalf = ReverseList.reverseIterative(slow);
        ListNode firstHalf = head;
        while (secondHalf != null) {
            if (firstHalf.val != secondHalf.val) return false;
            firstHalf = firstHalf.next;
            secondHalf = secondHalf.next;
        }
        return true;
    }
}
```

---

## 7️⃣ Merge Sort for Linked List

**Logic:**

* Find middle using slow/fast.
* Split list and recursively sort halves.
* Merge sorted halves.

```java
public class MergeSortLinkedList {
    public static ListNode mergeSort(ListNode head) {
        if (head == null || head.next == null) return head;
        ListNode mid = MiddleOfList.findMiddle(head);
        ListNode nextToMid = mid.next;
        mid.next = null;

        ListNode left = mergeSort(head);
        ListNode right = mergeSort(nextToMid);
        return MergeSortedLists.merge(left, right);
    }
}
```

---

## 8️⃣ Reorder List / Odd-Even List

**Purpose:** Rearrange nodes for alternating pattern or group odd/even indices.

**Reorder List Example (L0→Ln→L1→Ln-1...)**

```java
public class ReorderList {
    public static void reorder(ListNode head) {
        if (head == null) return;
        // Find middle
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        // Reverse second half
        ListNode second = ReverseList.reverseIterative(slow.next);
        slow.next = null;

        // Merge two halves
        ListNode first = head;
        while (second != null) {
            ListNode tmp1 = first.next;
            ListNode tmp2 = second.next;
            first.next = second;
            second.next = tmp1;
            first = tmp1;
            second = tmp2;
        }
    }
}
```

**Odd-Even List Example:**

```java
public class OddEvenList {
    public static ListNode oddEvenList(ListNode head) {
        if (head == null) return null;
        ListNode odd = head, even = head.next, evenHead = even;
        while (even != null && even.next != null) {
            odd.next = even.next;
            odd = odd.next;
            even.next = odd.next;
            even = even.next;
        }
        odd.next = evenHead;
        return head;
    }
}
```

