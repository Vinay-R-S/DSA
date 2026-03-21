# DSA realted info here

<details>
<summary><h2> Core Algorithms - <code>CoreAlgos.md</code></h2></summary>

##  Arrays

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

##  Sliding Window

| #   | Algorithm / Technique             | Purpose                                  |
| --- | --------------------------------- | ---------------------------------------- |
| 1   | Fixed-size Sliding Window         | Max/min/average sum in fixed window      |
| 2   | Variable-size Window              | Longest/shortest subarray with condition |
| 3   | Deque-based Sliding Window        | Sliding window maximum/minimum           |
| 4   | Anagram Window with HashMap       | Count substrings with matching frequency |
| 5   | Two-pointer Shrink-Expand Pattern | Common in substring problems             |

##  Linked List

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

## Heap / Priority Queue

| #   | Algorithm / Technique         | Purpose                         |
| --- | ----------------------------- | ------------------------------- |
| 1   | Heapify (Build Heap)          | Convert array to heap           |
| 2   | Heap Sort                     | Sort using heap                 |
| 3   | Kth Largest/Smallest          | Maintain min/max heap of size k |
| 4   | Top K Frequent Elements       | Use hashmap + heap              |
| 5   | Merge K Sorted Lists / Arrays | Use min-heap                    |
| 6   | Sliding Window Median         | Two heaps balancing             |
| 7   | Priority Queue Scheduling     | Greedy + heap problems          |

##  Hashmap / Hashing

| #   | Algorithm / Technique                | Purpose                               |
| --- | ------------------------------------ | ------------------------------------- |
| 1   | Two Sum Algorithm                    | Use hashmap for complement            |
| 2   | Prefix Sum + HashMap                 | Subarray sum equals K                 |
| 3   | Count Frequency / Distinct Elements  | Hash counting                         |
| 4   | Group Anagrams                       | Key as sorted string or count         |
| 5   | Longest Substring Without Repetition | HashSet + window                      |
| 6   | LRU Cache Algorithm                  | HashMap + Doubly Linked List          |
| 7   | HashMap-based Sliding Window         | Count frequency in substring problems |

##  Trees

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

##  Graphs

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

##  Recursion / Backtracking

| #   | Algorithm / Technique               | Purpose                         |
| --- | ----------------------------------- | ------------------------------- |
| 1   | Subset Generation                   | Power set                       |
| 2   | Permutation Generation              | All orderings                   |
| 3   | Combination Sum / N-Queens / Sudoku | Constraint backtracking         |
| 4   | Rat in a Maze / Word Search         | Path finding using recursion    |
| 5   | Backtracking Template               | For all constraint satisfaction |

##  Dynamic Programming

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

## Binary Search & Math

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

##  Stack / Queue

| #   | Algorithm / Technique                  | Purpose                       |
| --- | -------------------------------------- | ----------------------------- |
| 1   | Next Greater Element (Monotonic Stack) | For each element              |
| 2   | Valid Parentheses                      | Stack matching                |
| 3   | Infix → Postfix Conversion             | Expression evaluation         |
| 4   | Evaluate Postfix Expression            | Reverse Polish notation       |
| 5   | Largest Rectangle in Histogram         | Monotonic stack               |
| 6   | Trapping Rain Water                    | Two pointers / stack approach |

##  Bit Manipulation

| #   | Algorithm / Technique        | Purpose                  |
| --- | ---------------------------- | ------------------------ |
| 1   | Brian Kernighan’s Algorithm  | Count set bits           |
| 2   | Single Number using XOR      | Unique element detection |
| 3   | Subset Generation using Bits | Bitmask technique        |
| 4   | Power of Two Check           | (n & (n-1)) == 0         |
| 5   | XOR Pair / Max XOR Trie      | Bitwise trie             |
| 6   | Swap using XOR               | Trick questions          |

</details>