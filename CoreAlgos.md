# Core Algorithms
# Algorithms & Techniques Cheatsheet

## 🧩 Arrays

| #   | Algorithm / Technique         | Purpose                                        |
| --- | ----------------------------- | ---------------------------------------------- |
| 1   | Kadane’s Algorithm            | Maximum subarray sum                           |
| 2   | Moore’s Voting Algorithm      | Find majority element (> n/2 or > n/3)         |
| 3   | Prefix Sum                    | Range sum queries, subarray problems           |
| 4   | Dutch National Flag Algorithm | Sort 0s, 1s, 2s (3-way partition)              |
| 5   | Merge Intervals Algorithm     | Overlapping intervals merge                    |
| 6   | Cyclic Sort                   | Find missing / duplicate numbers in range 1..n |
| 7   | Two Pointers Technique        | Pair sum, remove duplicates, move zeros        |
| 8   | Binary Search (on array)      | Searching / min-max optimization               |
| 9   | Rotate / Reverse Algorithm    | Array rotation, reversing sections             |
| 10  | Prefix XOR / Prefix Min/Max   | For subarray XOR/sum-related problems          |

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

## 🧩 Arrays Algorithms (Basic to Medium)

This README covers the **most common algorithms** related to Arrays that are frequently used in DSA questions. Each section includes:

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

## 3️⃣ Prefix Sum — Range Sum Queries

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

## 4️⃣ Dutch National Flag Algorithm — Sort 0s, 1s, 2s

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

## 5️⃣ Cyclic Sort — Find Missing Numbers in Range [1..n]

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

## 6️⃣ Two Pointers — Remove Duplicates from Sorted Array

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

✅ **Next up:** Sliding Window Algorithms (Fixed & Variable window, Anagram window, Deque max window)

Would you like me to continue with **Sliding Window** next in the same README format?
