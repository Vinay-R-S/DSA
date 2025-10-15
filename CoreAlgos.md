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

# Arrays Algorithms

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


# Sliding Window Algorithms

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

# Linked List Algorithms

This covers the **core Linked list algorithms and patterns**. Each section includes:

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

---

# Heap [or] Priority Queue Algorithms

This covers the **core Heap data structure & algorithms**. Each section includes:

* **Explanation** of the algorithm
* **Java Function Code**
* **Example** to understand it clearly

---

## 1️⃣ Heapify (Build Heap)

**Purpose:** Convert an unsorted array into a heap (max or min). This forms the foundation for heap-based algorithms.

**Logic:** Start from the last non-leaf node and call `heapifyDown()` recursively.

**Java Code:**

```java
import java.util.*;

public class HeapifyBuild {
    public static void heapify(int[] arr, int n, int i) {
        int largest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;

        if (left < n && arr[left] > arr[largest]) largest = left;
        if (right < n && arr[right] > arr[largest]) largest = right;

        if (largest != i) {
            int temp = arr[i]; arr[i] = arr[largest]; arr[largest] = temp;
            heapify(arr, n, largest);
        }
    }

    public static void buildMaxHeap(int[] arr) {
        int n = arr.length;
        for (int i = n / 2 - 1; i >= 0; i--) heapify(arr, n, i);
    }

    public static void main(String[] args) {
        int[] arr = {4, 10, 3, 5, 1};
        buildMaxHeap(arr);
        System.out.println(Arrays.toString(arr)); // [10, 5, 3, 4, 1]
    }
}
```

---

## 2️⃣ Heap Sort

**Purpose:** Sort an array using heap structure.

**Logic:**

1. Build a max heap.
2. Swap root (max) with last element.
3. Reduce heap size and re-heapify.

**Java Code:**

```java
public class HeapSort {
    public static void heapSort(int[] arr) {
        int n = arr.length;
        for (int i = n / 2 - 1; i >= 0; i--) HeapifyBuild.heapify(arr, n, i);

        for (int i = n - 1; i > 0; i--) {
            int temp = arr[0]; arr[0] = arr[i]; arr[i] = temp;
            HeapifyBuild.heapify(arr, i, 0);
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        heapSort(arr);
        System.out.println(Arrays.toString(arr)); // [5, 6, 7, 11, 12, 13]
    }
}
```

---

## 3️⃣ Kth Largest / Smallest Element

**Purpose:** Find Kth largest or smallest element efficiently.

**Logic:** Use a min-heap of size k for largest, or max-heap for smallest.

**Java Code:**

```java
public class KthElement {
    public static int findKthLargest(int[] nums, int k) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        for (int num : nums) {
            minHeap.add(num);
            if (minHeap.size() > k) minHeap.poll();
        }
        return minHeap.peek();
    }
}
```

**Example:**

```
Input: [3,2,1,5,6,4], k=2
Output: 5
```

---

## 4️⃣ Top K Frequent Elements

**Purpose:** Find k most frequent elements using HashMap + Heap.

**Java Code:**

```java
public class TopKFrequent {
    public static int[] topKFrequent(int[] nums, int k) {
        Map<Integer, Integer> freq = new HashMap<>();
        for (int n : nums) freq.put(n, freq.getOrDefault(n, 0) + 1);

        PriorityQueue<Map.Entry<Integer, Integer>> pq =
            new PriorityQueue<>((a, b) -> a.getValue() - b.getValue());

        for (Map.Entry<Integer, Integer> e : freq.entrySet()) {
            pq.add(e);
            if (pq.size() > k) pq.poll();
        }

        int[] res = new int[k];
        for (int i = k - 1; i >= 0; i--) res[i] = pq.poll().getKey();
        return res;
    }
}
```

**Example:**

```
Input: [1,1,1,2,2,3], k=2
Output: [1,2]
```

---

## 5️⃣ Merge K Sorted Lists / Arrays

**Purpose:** Merge K sorted linked lists or arrays efficiently using a min-heap.

**Java Code:**

```java
class ListNode {
    int val;
    ListNode next;
    ListNode(int x) { val = x; }
}

public class MergeKLists {
    public static ListNode mergeKLists(ListNode[] lists) {
        PriorityQueue<ListNode> pq = new PriorityQueue<>((a, b) -> a.val - b.val);
        for (ListNode node : lists) if (node != null) pq.add(node);

        ListNode dummy = new ListNode(0), tail = dummy;
        while (!pq.isEmpty()) {
            ListNode min = pq.poll();
            tail.next = min;
            tail = tail.next;
            if (min.next != null) pq.add(min.next);
        }
        return dummy.next;
    }
}
```

---

## 6️⃣ Sliding Window Median

**Purpose:** Maintain medians of a sliding window using two heaps (max-heap & min-heap).

**Logic:**

* Max-heap holds smaller half, min-heap holds larger half.
* Balance sizes after each insert/remove.

**Java Code (Simplified):**

```java
public class SlidingWindowMedian {
    private PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
    private PriorityQueue<Integer> minHeap = new PriorityQueue<>();

    public void addNum(int num) {
        if (maxHeap.isEmpty() || num <= maxHeap.peek()) maxHeap.add(num);
        else minHeap.add(num);
        balanceHeaps();
    }

    private void balanceHeaps() {
        if (maxHeap.size() > minHeap.size() + 1) minHeap.add(maxHeap.poll());
        else if (minHeap.size() > maxHeap.size()) maxHeap.add(minHeap.poll());
    }

    public double findMedian() {
        if (maxHeap.size() == minHeap.size())
            return (maxHeap.peek() + minHeap.peek()) / 2.0;
        return maxHeap.peek();
    }
}
```

---

## 7️⃣ Priority Queue Scheduling

**Purpose:** Greedy optimization problems like CPU scheduling, meeting rooms, or task ordering.

**Example — Meeting Rooms II:** Minimum number of meeting rooms required.

```java
public class MeetingRoomsII {
    public static int minMeetingRooms(int[][] intervals) {
        Arrays.sort(intervals, (a, b) -> a[0] - b[0]);
        PriorityQueue<Integer> pq = new PriorityQueue<>(); // min-heap for end times

        for (int[] interval : intervals) {
            if (!pq.isEmpty() && pq.peek() <= interval[0]) pq.poll();
            pq.add(interval[1]);
        }
        return pq.size();
    }
}
```

**Example:**

```
Input: [[0,30],[5,10],[15,20]]
Output: 2
```

---

# HashMap [or] Hashing Algorithms

This covers the **core HashMap-based data structure & algorithms**. Each section includes:

* **Explanation** of the algorithm
* **Java Function Code**
* **Example** to understand it clearly

---

## 1️⃣ Two Sum Algorithm

**Purpose:** Find two numbers that add up to a target sum using a HashMap.

**Logic:** Store each number's complement (target - num) in a HashMap and check if it exists.

**Java Code:**

```java
import java.util.*;

public class TwoSum {
    public static int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }
            map.put(nums[i], i);
        }
        return new int[]{};
    }

    public static void main(String[] args) {
        int[] res = twoSum(new int[]{2, 7, 11, 15}, 9);
        System.out.println(Arrays.toString(res)); // [0, 1]
    }
}
```

**Example:**

```
Input: [2,7,11,15], target = 9
Output: [0,1]
```

---

## 2️⃣ Prefix Sum + HashMap

**Purpose:** Count number of subarrays with a sum equal to K.

**Logic:** Use a running sum and store frequency of prefix sums in HashMap.

**Java Code:**

```java
import java.util.*;

public class SubarraySumEqualsK {
    public static int subarraySum(int[] nums, int k) {
        Map<Integer, Integer> map = new HashMap<>();
        map.put(0, 1);
        int sum = 0, count = 0;

        for (int num : nums) {
            sum += num;
            if (map.containsKey(sum - k)) {
                count += map.get(sum - k);
            }
            map.put(sum, map.getOrDefault(sum, 0) + 1);
        }
        return count;
    }

    public static void main(String[] args) {
        int[] arr = {1, 1, 1};
        System.out.println(subarraySum(arr, 2)); // 2
    }
}
```

**Example:**

```
Input: [1,1,1], k = 2
Output: 2
```

---

## 3️⃣ Count Frequency / Distinct Elements

**Purpose:** Count frequency of each element or find number of distinct elements.

**Logic:** Use HashMap to count occurrences.

**Java Code:**

```java
import java.util.*;

public class CountFrequency {
    public static void main(String[] args) {
        int[] nums = {1, 2, 2, 3, 3, 3};
        Map<Integer, Integer> freq = new HashMap<>();

        for (int n : nums) freq.put(n, freq.getOrDefault(n, 0) + 1);

        System.out.println(freq); // {1=1, 2=2, 3=3}
        System.out.println("Distinct elements: " + freq.size()); // 3
    }
}
```

**Example:**

```
Input: [1,2,2,3,3,3]
Output: {1=1, 2=2, 3=3}, Distinct: 3
```

---

## 4️⃣ Group Anagrams

**Purpose:** Group words that are anagrams of each other.

**Logic:** Sort each word or use character counts as key in HashMap.

**Java Code:**

```java
import java.util.*;

public class GroupAnagrams {
    public static List<List<String>> groupAnagrams(String[] strs) {
        Map<String, List<String>> map = new HashMap<>();

        for (String s : strs) {
            char[] chars = s.toCharArray();
            Arrays.sort(chars);
            String key = new String(chars);
            map.computeIfAbsent(key, k -> new ArrayList<>()).add(s);
        }
        return new ArrayList<>(map.values());
    }

    public static void main(String[] args) {
        String[] words = {"eat", "tea", "tan", "ate", "nat", "bat"};
        System.out.println(groupAnagrams(words));
    }
}
```

**Example:**

```
Input: ["eat", "tea", "tan", "ate", "nat", "bat"]
Output: [[eat, tea, ate], [tan, nat], [bat]]
```

---

## 5️⃣ Longest Substring Without Repetition

**Purpose:** Find length of longest substring without repeating characters.

**Logic:** Use HashSet to maintain current window and slide it when duplicates appear.

**Java Code:**

```java
import java.util.*;

public class LongestSubstringNoRepeat {
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
        System.out.println(lengthOfLongestSubstring("abcabcbb")); // 3
    }
}
```

**Example:**

```
Input: "abcabcbb"
Output: 3
```

---

## 6️⃣ LRU Cache Algorithm

**Purpose:** Implement Least Recently Used cache using HashMap and Doubly Linked List.

**Logic:** HashMap for O(1) lookup + doubly linked list to track usage order.

**Java Code:**

```java
import java.util.*;

class LRUCache {
    class Node {
        int key, value;
        Node prev, next;
        Node(int k, int v) { key = k; value = v; }
    }

    private int capacity;
    private Map<Integer, Node> map = new HashMap<>();
    private Node head = new Node(0, 0), tail = new Node(0, 0);

    public LRUCache(int capacity) {
        this.capacity = capacity;
        head.next = tail;
        tail.prev = head;
    }

    public int get(int key) {
        if (!map.containsKey(key)) return -1;
        Node node = map.get(key);
        remove(node);
        insert(node);
        return node.value;
    }

    public void put(int key, int value) {
        if (map.containsKey(key)) remove(map.get(key));
        if (map.size() == capacity) remove(tail.prev);
        insert(new Node(key, value));
    }

    private void insert(Node node) {
        map.put(node.key, node);
        node.next = head.next;
        node.prev = head;
        head.next.prev = node;
        head.next = node;
    }

    private void remove(Node node) {
        map.remove(node.key);
        node.prev.next = node.next;
        node.next.prev = node.prev;
    }

    public static void main(String[] args) {
        LRUCache cache = new LRUCache(2);
        cache.put(1, 1);
        cache.put(2, 2);
        System.out.println(cache.get(1)); // 1
        cache.put(3, 3); // removes key 2
        System.out.println(cache.get(2)); // -1
    }
}
```

**Example:**

```
Input: [put(1,1), put(2,2), get(1), put(3,3), get(2)]
Output: [null, null, 1, null, -1]
```

---

## 7️⃣ HashMap-based Sliding Window

**Purpose:** Handle problems like minimum window substring or anagram finding.

**Logic:** Maintain a frequency map and slide window adjusting counts.

**Java Code:**

```java
import java.util.*;

public class MinWindowSubstring {
    public static String minWindow(String s, String t) {
        if (s.length() < t.length()) return "";
        Map<Character, Integer> map = new HashMap<>();
        for (char c : t.toCharArray()) map.put(c, map.getOrDefault(c, 0) + 1);

        int left = 0, count = t.length(), minLen = Integer.MAX_VALUE, start = 0;
        for (int right = 0; right < s.length(); right++) {
            char c = s.charAt(right);
            if (map.containsKey(c)) {
                if (map.get(c) > 0) count--;
                map.put(c, map.get(c) - 1);
            }

            while (count == 0) {
                if (right - left + 1 < minLen) {
                    minLen = right - left + 1;
                    start = left;
                }
                char lc = s.charAt(left++);
                if (map.containsKey(lc)) {
                    map.put(lc, map.get(lc) + 1);
                    if (map.get(lc) > 0) count++;
                }
            }
        }
        return minLen == Integer.MAX_VALUE ? "" : s.substring(start, start + minLen);
    }

    public static void main(String[] args) {
        System.out.println(minWindow("ADOBECODEBANC", "ABC")); // BANC
    }
}
```

**Example:**

```
Input: s = "ADOBECODEBANC", t = "ABC"
Output: "BANC"
```

---

# Tree, Binary Tree & BST Algorithms

This covers the **core Binary Tree & BST algorithms**. Each section includes:

* **Explanation** of the algorithm
* **Java Function Code**
* **Example** to understand it clearly

---

## 1️⃣ DFS Traversal (Preorder, Inorder, Postorder)

**Purpose:** Explore all nodes recursively in different traversal orders.

**Logic:**

* **Preorder:** Root → Left → Right
* **Inorder:** Left → Root → Right
* **Postorder:** Left → Right → Root

**Java Code:**

```java
class TreeNode {
    int val;
    TreeNode left, right;
    TreeNode(int val) { this.val = val; }
}

public class DFSTraversal {
    public static void preorder(TreeNode root) {
        if (root == null) return;
        System.out.print(root.val + " ");
        preorder(root.left);
        preorder(root.right);
    }

    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    public static void postorder(TreeNode root) {
        if (root == null) return;
        postorder(root.left);
        postorder(root.right);
        System.out.print(root.val + " ");
    }

    public static void main(String[] args) {
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);

        System.out.print("Preorder: "); preorder(root);
        System.out.print("\nInorder: "); inorder(root);
        System.out.print("\nPostorder: "); postorder(root);
    }
}
```

**Example:**

```
Input Tree: [1,2,3,4,5]
Preorder: 1 2 4 5 3
Inorder: 4 2 5 1 3
Postorder: 4 5 2 3 1
```

---

## 2️⃣ BFS (Level Order Traversal)

**Purpose:** Traverse tree level by level using a queue.

**Logic:** Use a queue to process nodes from left to right for each level.

**Java Code:**

```java
import java.util.*;

public class LevelOrderTraversal {
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> res = new ArrayList<>();
        if (root == null) return res;

        Queue<TreeNode> q = new LinkedList<>();
        q.add(root);

        while (!q.isEmpty()) {
            int size = q.size();
            List<Integer> level = new ArrayList<>();

            for (int i = 0; i < size; i++) {
                TreeNode node = q.poll();
                level.add(node.val);
                if (node.left != null) q.add(node.left);
                if (node.right != null) q.add(node.right);
            }
            res.add(level);
        }
        return res;
    }
}
```

**Example:**

```
Input: [1,2,3,4,5]
Output: [[1],[2,3],[4,5]]
```

---

## 3️⃣ Diameter of Binary Tree

**Purpose:** Find the longest path between two nodes.

**Logic:** Diameter = max(left height + right height) for all nodes.

**Java Code:**

```java
public class DiameterBinaryTree {
    static int diameter = 0;

    public static int height(TreeNode root) {
        if (root == null) return 0;
        int left = height(root.left);
        int right = height(root.right);
        diameter = Math.max(diameter, left + right);
        return Math.max(left, right) + 1;
    }

    public static int getDiameter(TreeNode root) {
        height(root);
        return diameter;
    }
}
```

**Example:**

```
Input Tree: [1,2,3,4,5]
Output: Diameter = 3 (Path 4→2→1→3)
```

---

## 4️⃣ Lowest Common Ancestor (LCA)

**Purpose:** Find the lowest node that is ancestor to both given nodes.

**Logic:** If one node lies on left and other on right, current node is LCA.

**Java Code:**

```java
public class LowestCommonAncestor {
    public static TreeNode lca(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null || root == p || root == q) return root;

        TreeNode left = lca(root.left, p, q);
        TreeNode right = lca(root.right, p, q);

        if (left != null && right != null) return root;
        return (left != null) ? left : right;
    }
}
```

**Example:**

```
Input Tree: [3,5,1,6,2,0,8,null,null,7,4], p=5, q=1
Output: LCA = 3
```

---

## 5️⃣ Inorder Successor [or] Predecessor

**Purpose:** Find next or previous node in BST's inorder traversal.

**Logic:**

* Successor: Smallest node greater than key.
* Predecessor: Largest node smaller than key.

**Java Code:**

```java
public class BSTSuccessorPredecessor {
    public static TreeNode inorderSuccessor(TreeNode root, TreeNode p) {
        TreeNode succ = null;
        while (root != null) {
            if (p.val < root.val) {
                succ = root;
                root = root.left;
            } else root = root.right;
        }
        return succ;
    }

    public static TreeNode inorderPredecessor(TreeNode root, TreeNode p) {
        TreeNode pred = null;
        while (root != null) {
            if (p.val > root.val) {
                pred = root;
                root = root.right;
            } else root = root.left;
        }
        return pred;
    }
}
```

**Example:**

```
BST: [20,10,30,5,15,25,35], Node=10
Successor: 15
Predecessor: 5
```

---

## 6️⃣ Serialize [or] Deserialize Binary Tree

**Purpose:** Convert tree to string and reconstruct it back.

**Logic:** Use preorder traversal with 'null' markers for missing nodes.

**Java Code:**

```java
import java.util.*;

public class SerializeDeserializeTree {
    public static String serialize(TreeNode root) {
        if (root == null) return "null,";
        return root.val + "," + serialize(root.left) + serialize(root.right);
    }

    public static TreeNode deserialize(Queue<String> nodes) {
        String val = nodes.poll();
        if (val.equals("null")) return null;
        TreeNode root = new TreeNode(Integer.parseInt(val));
        root.left = deserialize(nodes);
        root.right = deserialize(nodes);
        return root;
    }

    public static TreeNode deserialize(String data) {
        Queue<String> nodes = new LinkedList<>(Arrays.asList(data.split(",")));
        return deserialize(nodes);
    }
}
```

**Example:**

```
Input Tree: [1,2,3,null,null,4,5]
Serialized: 1,2,null,null,3,4,null,null,5,null,null,
Deserialized: Restored Tree
```

---

## 7️⃣ Morris Traversal

**Purpose:** Perform inorder traversal without recursion or stack.

**Logic:** Create temporary threads to predecessor nodes and backtrack.

**Java Code:**

```java
public class MorrisTraversal {
    public static void inorder(TreeNode root) {
        TreeNode curr = root;
        while (curr != null) {
            if (curr.left == null) {
                System.out.print(curr.val + " ");
                curr = curr.right;
            } else {
                TreeNode pre = curr.left;
                while (pre.right != null && pre.right != curr) pre = pre.right;

                if (pre.right == null) {
                    pre.right = curr;
                    curr = curr.left;
                } else {
                    pre.right = null;
                    System.out.print(curr.val + " ");
                    curr = curr.right;
                }
            }
        }
    }
}
```

**Example:**

```
Input Tree: [1,2,3,4,5]
Output (Inorder): 4 2 5 1 3
```

---

## 8️⃣ Balanced Tree Check

**Purpose:** Check if tree is height-balanced.

**Logic:** A tree is balanced if |leftHeight - rightHeight| <= 1 for all nodes.

**Java Code:**

```java
public class BalancedTreeCheck {
    public static int checkHeight(TreeNode root) {
        if (root == null) return 0;
        int left = checkHeight(root.left);
        int right = checkHeight(root.right);
        if (left == -1 || right == -1 || Math.abs(left - right) > 1) return -1;
        return Math.max(left, right) + 1;
    }

    public static boolean isBalanced(TreeNode root) {
        return checkHeight(root) != -1;
    }
}
```

**Example:**

```
Input Tree: [3,9,20,null,null,15,7]
Output: true
```

---

## 9️⃣ Boundary [or] Vertical [or] Zigzag Traversal

**Purpose:** Explore tree in different structural patterns.

**Logic:** Combine BFS and structural mapping using HashMap or deque.

**Java Code (Zigzag Example):**

```java
import java.util.*;

public class ZigzagTraversal {
    public static List<List<Integer>> zigzagLevelOrder(TreeNode root) {
        List<List<Integer>> res = new ArrayList<>();
        if (root == null) return res;

        Queue<TreeNode> q = new LinkedList<>();
        q.add(root);
        boolean leftToRight = true;

        while (!q.isEmpty()) {
            int size = q.size();
            LinkedList<Integer> level = new LinkedList<>();

            for (int i = 0; i < size; i++) {
                TreeNode node = q.poll();
                if (leftToRight) level.addLast(node.val);
                else level.addFirst(node.val);

                if (node.left != null) q.add(node.left);
                if (node.right != null) q.add(node.right);
            }

            res.add(level);
            leftToRight = !leftToRight;
        }
        return res;
    }
}
```

**Example:**

```
Input: [3,9,20,null,null,15,7]
Output: [[3],[20,9],[15,7]]
```

---

## 🔟 BST Operations (Insert [or] Delete [or] Search)

**Purpose:** Perform standard BST operations recursively.

**Logic:** Use BST property to guide recursion.

**Java Code:**

```java
public class BSTOperations {
    public static TreeNode insert(TreeNode root, int val) {
        if (root == null) return new TreeNode(val);
        if (val < root.val) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static TreeNode search(TreeNode root, int val) {
        if (root == null || root.val == val) return root;
        return val < root.val ? search(root.left, val) : search(root.right, val);
    }

    public static TreeNode delete(TreeNode root, int val) {
        if (root == null) return null;
        if (val < root.val) root.left = delete(root.left, val);
        else if (val > root.val) root.right = delete(root.right, val);
        else {
            if (root.left == null) return root.right;
            if (root.right == null) return root.left;

            TreeNode minNode = root.right;
            while (minNode.left != null) minNode = minNode.left;
            root.val = minNode.val;
            root.right = delete(root.right, minNode.val);
        }
        return root;
    }
}
```

**Example:**

```
Insert: [5,3,7] → Insert 4 → [5,3,4,7]
Search: Key 7 → Found
Delete: Key 3 → Tree becomes [5,4,7]
```

---

# Graph Algorithms

This covers the **core Graph algorithms and techniques** used in traversal, shortest paths, MST, and connectivity problems.

Each section includes:

* **Explanation** of the algorithm
* **Java Function Code**
* **Example** to understand it clearly

---

## 1️⃣ BFS (Breadth First Search)

**Purpose:** Find the shortest path in an unweighted graph or traverse level by level.

**Java Code:**

```java
import java.util.*;

public class BFSGraph {
    public static void bfs(int V, List<List<Integer>> adj, int start) {
        boolean[] visited = new boolean[V];
        Queue<Integer> q = new LinkedList<>();
        q.add(start);
        visited[start] = true;

        while (!q.isEmpty()) {
            int node = q.poll();
            System.out.print(node + " ");
            for (int neigh : adj.get(node)) {
                if (!visited[neigh]) {
                    visited[neigh] = true;
                    q.add(neigh);
                }
            }
        }
    }

    public static void main(String[] args) {
        int V = 5;
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i < V; i++) adj.add(new ArrayList<>());
        adj.get(0).addAll(Arrays.asList(1, 2));
        adj.get(1).add(3);
        adj.get(2).add(4);

        bfs(V, adj, 0); // Output: 0 1 2 3 4
    }
}
```

---

## 2️⃣ DFS (Depth First Search)

**Purpose:** Explore connected components or detect cycles using recursion.

**Java Code:**

```java
import java.util.*;

public class DFSGraph {
    public static void dfs(int node, boolean[] visited, List<List<Integer>> adj) {
        visited[node] = true;
        System.out.print(node + " ");
        for (int neigh : adj.get(node)) {
            if (!visited[neigh]) dfs(neigh, visited, adj);
        }
    }

    public static void main(String[] args) {
        int V = 5;
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i < V; i++) adj.add(new ArrayList<>());
        adj.get(0).addAll(Arrays.asList(1, 2));
        adj.get(1).add(3);
        adj.get(2).add(4);

        boolean[] visited = new boolean[V];
        dfs(0, visited, adj); // Output: 0 1 3 2 4
    }
}
```

---

## 3️⃣ Dijkstra’s Algorithm

**Purpose:** Find the shortest path in weighted graphs with non-negative weights.

**Java Code:**

```java
import java.util.*;

class Pair {
    int node, dist;
    Pair(int n, int d) { node = n; dist = d; }
}

public class Dijkstra {
    public static int[] dijkstra(int V, List<List<Pair>> adj, int src) {
        int[] dist = new int[V];
        Arrays.fill(dist, Integer.MAX_VALUE);
        dist[src] = 0;

        PriorityQueue<Pair> pq = new PriorityQueue<>((a, b) -> a.dist - b.dist);
        pq.add(new Pair(src, 0));

        while (!pq.isEmpty()) {
            Pair curr = pq.poll();
            for (Pair edge : adj.get(curr.node)) {
                if (dist[curr.node] + edge.dist < dist[edge.node]) {
                    dist[edge.node] = dist[curr.node] + edge.dist;
                    pq.add(new Pair(edge.node, dist[edge.node]));
                }
            }
        }
        return dist;
    }

    public static void main(String[] args) {
        int V = 5;
        List<List<Pair>> adj = new ArrayList<>();
        for (int i = 0; i < V; i++) adj.add(new ArrayList<>());
        adj.get(0).add(new Pair(1, 2));
        adj.get(0).add(new Pair(2, 4));
        adj.get(1).add(new Pair(2, 1));
        adj.get(2).add(new Pair(3, 7));

        int[] dist = dijkstra(V, adj, 0);
        System.out.println(Arrays.toString(dist)); // [0, 2, 3, 10, ∞]
    }
}
```

---

## 4️⃣ Bellman-Ford Algorithm

**Purpose:** Shortest path algorithm that handles negative edges.

**Java Code:**

```java
import java.util.*;

public class BellmanFord {
    public static void bellmanFord(int V, int[][] edges, int src) {
        int[] dist = new int[V];
        Arrays.fill(dist, Integer.MAX_VALUE);
        dist[src] = 0;

        for (int i = 1; i < V; i++) {
            for (int[] e : edges) {
                int u = e[0], v = e[1], w = e[2];
                if (dist[u] != Integer.MAX_VALUE && dist[u] + w < dist[v]) dist[v] = dist[u] + w;
            }
        }

        System.out.println(Arrays.toString(dist));
    }
}
```

**Example:**

```
Input: edges = {{0,1,5},{1,2,-2},{0,2,4}}, V=3, src=0
Output: [0,5,3]
```

---

## 5️⃣ Floyd-Warshall Algorithm

**Purpose:** All-pairs shortest path using dynamic programming.

**Java Code:**

```java
public class FloydWarshall {
    public static void floydWarshall(int[][] dist) {
        int V = dist.length;
        for (int k = 0; k < V; k++)
            for (int i = 0; i < V; i++)
                for (int j = 0; j < V; j++)
                    if (dist[i][k] + dist[k][j] < dist[i][j])
                        dist[i][j] = dist[i][k] + dist[k][j];

        for (int[] row : dist) System.out.println(Arrays.toString(row));
    }
}
```

**Example:**

```
Input: 3x3 matrix
[[0, 5, INF], [50, 0, 10], [INF, INF, 0]]
Output: [[0, 5, 15], [20, 0, 10], [INF, INF, 0]]
```

---

## 6️⃣ Topological Sort (Kahn’s / DFS)

**Purpose:** Order nodes in a DAG where each node appears before its dependents.

**Java Code (Kahn’s Algorithm):**

```java
import java.util.*;

public class TopoSort {
    public static List<Integer> topoSort(int V, List<List<Integer>> adj) {
        int[] indeg = new int[V];
        for (List<Integer> list : adj)
            for (int x : list) indeg[x]++;

        Queue<Integer> q = new LinkedList<>();
        for (int i = 0; i < V; i++) if (indeg[i] == 0) q.add(i);

        List<Integer> res = new ArrayList<>();
        while (!q.isEmpty()) {
            int node = q.poll();
            res.add(node);
            for (int neigh : adj.get(node)) if (--indeg[neigh] == 0) q.add(neigh);
        }
        return res;
    }
}
```

**Example:**

```
Input: 6, edges = [[5,2],[5,0],[4,0],[4,1],[2,3],[3,1]]
Output: [4,5,2,3,1,0]
```

---

## 7️⃣ Union-Find / DSU

**Purpose:** Detect cycles or connect components efficiently.

**Java Code:**

```java
public class DSU {
    int[] parent, rank;

    DSU(int n) {
        parent = new int[n]; rank = new int[n];
        for (int i = 0; i < n; i++) parent[i] = i;
    }

    int find(int x) {
        if (parent[x] != x) parent[x] = find(parent[x]);
        return parent[x];
    }

    void union(int x, int y) {
        int px = find(x), py = find(y);
        if (px == py) return;
        if (rank[px] < rank[py]) parent[px] = py;
        else if (rank[px] > rank[py]) parent[py] = px;
        else { parent[py] = px; rank[px]++; }
    }
}
```

**Example:**

```
Union(0,1), Union(1,2) => find(0)==find(2) → true
```

---

## 8️⃣ Kruskal’s Algorithm

**Purpose:** Find Minimum Spanning Tree (MST) using DSU.

**Java Code:**

```java
import java.util.*;

public class Kruskal {
    static class Edge { int u, v, w; Edge(int a, int b, int c){u=a;v=b;w=c;} }

    public static int kruskalMST(int V, List<Edge> edges) {
        Collections.sort(edges, (a,b) -> a.w - b.w);
        DSU dsu = new DSU(V);
        int mst = 0;
        for (Edge e : edges) {
            if (dsu.find(e.u) != dsu.find(e.v)) {
                mst += e.w;
                dsu.union(e.u, e.v);
            }
        }
        return mst;
    }
}
```

**Example:**

```
Input: edges = [(0,1,1),(1,2,2),(0,2,3)]
Output: 3
```

---

## 9️⃣ Prim’s Algorithm

**Purpose:** Find MST using a priority queue (greedy).

**Java Code:**

```java
import java.util.*;

public class Prim {
    public static int primMST(int V, List<List<Pair>> adj) {
        boolean[] mstSet = new boolean[V];
        int[] key = new int[V];
        Arrays.fill(key, Integer.MAX_VALUE);
        key[0] = 0;

        PriorityQueue<Pair> pq = new PriorityQueue<>((a,b) -> a.dist - b.dist);
        pq.add(new Pair(0,0));

        int res = 0;
        while (!pq.isEmpty()) {
            int u = pq.poll().node;
            if (mstSet[u]) continue;
            mstSet[u] = true;
            res += key[u];
            for (Pair edge : adj.get(u)) {
                if (!mstSet[edge.node] && edge.dist < key[edge.node]) {
                    key[edge.node] = edge.dist;
                    pq.add(new Pair(edge.node, key[edge.node]));
                }
            }
        }
        return res;
    }
}
```

**Example:**

```
Input: Graph with edges (0-1:2, 0-2:3, 1-2:1)
Output: 3
```

---

## 🔟 Tarjan’s Algorithm

**Purpose:** Find Strongly Connected Components (SCCs), bridges, or articulation points.

**Java Code:**

```java
import java.util.*;

public class Tarjan {
    static int time = 0;
    public static void dfs(int u, int parent, List<List<Integer>> adj, int[] disc, int[] low, boolean[] vis) {
        vis[u] = true;
        disc[u] = low[u] = ++time;
        for (int v : adj.get(u)) {
            if (v == parent) continue;
            if (!vis[v]) {
                dfs(v, u, adj, disc, low, vis);
                low[u] = Math.min(low[u], low[v]);
                if (low[v] > disc[u]) System.out.println(u + " - " + v + " is a bridge");
            } else low[u] = Math.min(low[u], disc[v]);
        }
    }
}
```

**Example:**

```
Input: 0-1-2-0 and 1-3
Output: Bridge: 1-3
```

---

## 1️⃣1️⃣ Kosaraju’s Algorithm

**Purpose:** Find all Strongly Connected Components (SCCs) using 2 DFS passes.

**Java Code:**

```java
import java.util.*;

public class Kosaraju {
    public static void kosaraju(int V, List<List<Integer>> adj) {
        Stack<Integer> st = new Stack<>();
        boolean[] vis = new boolean[V];

        for (int i = 0; i < V; i++) if (!vis[i]) dfs1(i, adj, vis, st);

        List<List<Integer>> rev = new ArrayList<>();
        for (int i = 0; i < V; i++) rev.add(new ArrayList<>());
        for (int i = 0; i < V; i++) for (int j : adj.get(i)) rev.get(j).add(i);

        Arrays.fill(vis, false);
        while (!st.isEmpty()) {
            int node = st.pop();
            if (!vis[node]) {
                dfs2(node, rev, vis);
                System.out.println();
            }
        }
    }

    static void dfs1(int node, List<List<Integer>> adj, boolean[] vis, Stack<Integer> st) {
        vis[node] = true;
        for (int v : adj.get(node)) if (!vis[v]) dfs1(v, adj, vis, st);
        st.push(node);
    }

    static void dfs2(int node, List<List<Integer>> rev, boolean[] vis) {
        vis[node] = true;
        System.out.print(node + " ");
        for (int v : rev.get(node)) if (!vis[v]) dfs2(v, rev, vis);
    }
}
```

**Example:**

```
Input: Graph with SCCs [[0,1],[1,2],[2,0],[3,4]]
Output:
SCC1: 0 1 2
SCC2: 3 4
```

---

## 1️⃣2️⃣ Cycle Detection (Directed/Undirected)

**Purpose:** Detect cycles in both directed and undirected graphs.

**Java Code:**

### 🔹 Directed Graph — Using DFS (Recursion Stack)

**Idea:**

* Use a DFS traversal.
* Maintain two arrays:

  * `visited[v]` — marks if a node has been visited.
  * `recStack[v]` — marks if a node is currently in the recursion stack.
* If we find a node that is already in the recursion stack → cycle detected.

**Java Code:**

```java
import java.util.*;

class DirectedCycleDetection {
    private int vertices;
    private List<List<Integer>> adj;

    DirectedCycleDetection(int v) {
        vertices = v;
        adj = new ArrayList<>();
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    void addEdge(int u, int v) {
        adj.get(u).add(v);
    }

    boolean isCyclicUtil(int node, boolean[] visited, boolean[] recStack) {
        if (recStack[node]) return true;
        if (visited[node]) return false;

        visited[node] = true;
        recStack[node] = true;

        for (int neighbor : adj.get(node)) {
            if (isCyclicUtil(neighbor, visited, recStack)) return true;
        }

        recStack[node] = false;
        return false;
    }

    boolean isCyclic() {
        boolean[] visited = new boolean[vertices];
        boolean[] recStack = new boolean[vertices];

        for (int i = 0; i < vertices; i++) {
            if (isCyclicUtil(i, visited, recStack)) return true;
        }
        return false;
    }

    public static void main(String[] args) {
        DirectedCycleDetection g = new DirectedCycleDetection(4);
        g.addEdge(0, 1);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);

        System.out.println("Cycle exists (Directed): " + g.isCyclic());
    }
}
```

**Output:**

```
Cycle exists (Directed): true
```

---

### 🔹 Undirected Graph — Using DFS

**Idea:**

* For each unvisited node, perform DFS.
* If we find a neighbor that is visited and not the parent of the current node → cycle detected.

**Java Code:**

```java
import java.util.*;

class UndirectedCycleDetection {
    private int vertices;
    private List<List<Integer>> adj;

    UndirectedCycleDetection(int v) {
        vertices = v;
        adj = new ArrayList<>();
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u);
    }

    boolean isCyclicUtil(int node, boolean[] visited, int parent) {
        visited[node] = true;

        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                if (isCyclicUtil(neighbor, visited, node)) return true;
            } else if (neighbor != parent) {
                return true; // Found a cycle
            }
        }
        return false;
    }

    boolean isCyclic() {
        boolean[] visited = new boolean[vertices];

        for (int i = 0; i < vertices; i++) {
            if (!visited[i]) {
                if (isCyclicUtil(i, visited, -1)) return true;
            }
        }
        return false;
    }

    public static void main(String[] args) {
        UndirectedCycleDetection g = new UndirectedCycleDetection(5);
        g.addEdge(0, 1);
        g.addEdge(1, 2);
        g.addEdge(2, 0);

        System.out.println("Cycle exists (Undirected): " + g.isCyclic());
    }
}
```

**Output:**

```
Cycle exists (Undirected): true
```

**Example:**

```
Directed Graph: 0→1→2→0 → Cycle Detected
Undirected Graph: 0–1–2–0 → Cycle Detected
```

---

