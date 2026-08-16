# Java Built-in Data Structures and Their Methods

## 1. Array

### Declaration

```java
int[] arr = new int[5];
int[] nums = {1, 2, 3, 4};
```

### Important Properties

- Fixed size
- Stores same data type elements
- Index based access
- Faster random access O(1)

### Common Operations

| Operation | Example            | Time Complexity |
| --------- | ------------------ | --------------- |
| Access    | `arr[2]`           | O(1)            |
| Update    | `arr[1] = 10`      | O(1)            |
| Traverse  | `for(int x : arr)` | O(n)            |
| Search    | Linear Search      | O(n)            |

# 2. ArrayList

## Package

```java
import java.util.ArrayList;
```

## Declaration

```java
ArrayList<Integer> list = new ArrayList<>();
```

## Characteristics

- Dynamic array
- Resizable
- Preserves insertion order
- Allows duplicates
- Fast random access

## Common Methods

| Method                  | Description            | Example                           |
| ----------------------- | ---------------------- | --------------------------------- |
| `add(E e)`              | Add element at end     | `list.add(10)`                    |
| `add(int index, E e)`   | Add at index           | `list.add(1, 50)`                 |
| `get(int index)`        | Access element         | `list.get(2)`                     |
| `set(int index, E e)`   | Update element         | `list.set(0, 99)`                 |
| `remove(int index)`     | Remove by index        | `list.remove(1)`                  |
| `remove(Object o)`      | Remove by value        | `list.remove(Integer.valueOf(5))` |
| `size()`                | Returns size           | `list.size()`                     |
| `contains(Object o)`    | Check element exists   | `list.contains(10)`               |
| `isEmpty()`             | Check empty            | `list.isEmpty()`                  |
| `clear()`               | Remove all elements    | `list.clear()`                    |
| `indexOf(Object o)`     | First occurrence index | `list.indexOf(10)`                |
| `lastIndexOf(Object o)` | Last occurrence index  | `list.lastIndexOf(10)`            |
| `sort(Comparator c)`    | Sort list              | `list.sort(null)`                 |
| `toArray()`             | Convert to array       | `list.toArray()`                  |
| `iterator()`            | Returns iterator       | `list.iterator()`                 |

## Traversal

```java
for(int x : list){
    System.out.println(x);
}
```

# 3. LinkedList

## Package

```java
import java.util.LinkedList;
```

## Declaration

```java
LinkedList<Integer> list = new LinkedList<>();
```

## Characteristics

- Doubly linked list
- Dynamic size
- Faster insertion/deletion in middle
- Slower random access

## Common Methods

| Method               | Description               |
| -------------------- | ------------------------- |
| `add(E e)`           | Add element               |
| `addFirst(E e)`      | Add at beginning          |
| `addLast(E e)`       | Add at end                |
| `get(int index)`     | Access element            |
| `getFirst()`         | First element             |
| `getLast()`          | Last element              |
| `remove()`           | Remove first              |
| `removeFirst()`      | Remove first              |
| `removeLast()`       | Remove last               |
| `peek()`             | View first                |
| `peekFirst()`        | View first                |
| `peekLast()`         | View last                 |
| `poll()`             | Retrieve and remove first |
| `pollFirst()`        | Retrieve and remove first |
| `pollLast()`         | Retrieve and remove last  |
| `size()`             | Size of list              |
| `contains(Object o)` | Search element            |
| `clear()`            | Remove all                |

# 4. Stack

## Package

```java
import java.util.Stack;
```

## Declaration

```java
Stack<Integer> st = new Stack<>();
```

## Characteristics

- LIFO (Last In First Out)

## Common Methods

| Method             | Description       |
| ------------------ | ----------------- |
| `push(E e)`        | Insert element    |
| `pop()`            | Remove top        |
| `peek()`           | View top          |
| `empty()`          | Check empty       |
| `search(Object o)` | Position from top |
| `size()`           | Stack size        |
| `clear()`          | Remove all        |

# 5. Queue

## Package

```java
import java.util.Queue;
import java.util.LinkedList;
```

## Declaration

```java
Queue<Integer> q = new LinkedList<>();
```

## Characteristics

- FIFO (First In First Out)

## Common Methods

| Method               | Description    |
| -------------------- | -------------- |
| `offer(E e)`         | Insert element |
| `add(E e)`           | Insert element |
| `poll()`             | Remove front   |
| `remove()`           | Remove front   |
| `peek()`             | View front     |
| `element()`          | View front     |
| `size()`             | Queue size     |
| `isEmpty()`          | Check empty    |
| `contains(Object o)` | Search element |
| `clear()`            | Remove all     |

# 6. PriorityQueue (Heap)

## Package

```java
import java.util.PriorityQueue;
```

## Declaration

```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
```

## Characteristics

- Min Heap by default
- Stores elements based on priority

## Max Heap

```java
PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
```

## Common Methods

| Method               | Description     |
| -------------------- | --------------- |
| `offer(E e)`         | Insert          |
| `add(E e)`           | Insert          |
| `poll()`             | Remove smallest |
| `remove()`           | Remove smallest |
| `peek()`             | View smallest   |
| `size()`             | Size            |
| `contains(Object o)` | Search          |
| `clear()`            | Remove all      |

# 7. HashSet

## Package

```java
import java.util.HashSet;
```

## Declaration

```java
HashSet<Integer> set = new HashSet<>();
```

## Characteristics

- No duplicates
- Unordered
- Uses hashing
- Average O(1) operations

## Common Methods

| Method               | Description |
| -------------------- | ----------- |
| `add(E e)`           | Insert      |
| `remove(Object o)`   | Remove      |
| `contains(Object o)` | Search      |
| `size()`             | Size        |
| `isEmpty()`          | Check empty |
| `clear()`            | Remove all  |
| `iterator()`         | Iterator    |

# 8. LinkedHashSet

## Package

```java
import java.util.LinkedHashSet;
```

## Characteristics

- Maintains insertion order
- No duplicates

## Common Methods

- Same as `HashSet`

# 9. TreeSet

## Package

```java
import java.util.TreeSet;
```

## Characteristics

- Sorted order
- No duplicates
- Based on Red Black Tree

## Declaration

```java
TreeSet<Integer> ts = new TreeSet<>();
```

## Common Methods

| Method               | Description      |
| -------------------- | ---------------- |
| `add(E e)`           | Insert           |
| `remove(Object o)`   | Remove           |
| `contains(Object o)` | Search           |
| `first()`            | Smallest element |
| `last()`             | Largest element  |
| `higher(E e)`        | Greater element  |
| `lower(E e)`         | Smaller element  |
| `ceiling(E e)`       | >= element       |
| `floor(E e)`         | <= element       |
| `pollFirst()`        | Remove first     |
| `pollLast()`         | Remove last      |
| `size()`             | Size             |

# 10. HashMap

## Package

```java
import java.util.HashMap;
```

## Declaration

```java
HashMap<Integer, String> map = new HashMap<>();
```

## Characteristics

- Key value pairs
- Unique keys
- Unordered
- Average O(1)

## Common Methods

| Method                        | Description      |
| ----------------------------- | ---------------- |
| `put(K key, V value)`         | Insert/update    |
| `get(Object key)`             | Get value        |
| `remove(Object key)`          | Remove key       |
| `containsKey(Object key)`     | Check key        |
| `containsValue(Object value)` | Check value      |
| `keySet()`                    | All keys         |
| `values()`                    | All values       |
| `entrySet()`                  | Key value pairs  |
| `getOrDefault(K key, V def)`  | Default value    |
| `putIfAbsent(K key, V value)` | Insert if absent |
| `replace(K key, V value)`     | Replace value    |
| `size()`                      | Size             |
| `isEmpty()`                   | Check empty      |
| `clear()`                     | Remove all       |

## Traversal

```java
for(Map.Entry<Integer, String> e : map.entrySet()){
    System.out.println(e.getKey() + " " + e.getValue());
}
```

# 11. LinkedHashMap

## Package

```java
import java.util.LinkedHashMap;
```

## Characteristics

- Maintains insertion order
- Faster than TreeMap

## Common Methods

- Same as `HashMap`

# 12. TreeMap

## Package

```java
import java.util.TreeMap;
```

## Characteristics

- Sorted keys
- Red Black Tree
- O(log n)

## Declaration

```java
TreeMap<Integer, String> tm = new TreeMap<>();
```

## Common Methods

| Method                    | Description  |
| ------------------------- | ------------ |
| `put(K key, V value)`     | Insert       |
| `get(Object key)`         | Access value |
| `remove(Object key)`      | Remove       |
| `firstKey()`              | Smallest key |
| `lastKey()`               | Largest key  |
| `higherKey(K key)`        | Greater key  |
| `lowerKey(K key)`         | Smaller key  |
| `ceilingKey(K key)`       | >= key       |
| `floorKey(K key)`         | <= key       |
| `pollFirstEntry()`        | Remove first |
| `pollLastEntry()`         | Remove last  |
| `containsKey(Object key)` | Check key    |
| `size()`                  | Size         |

# 13. Deque

## Package

```java
import java.util.Deque;
import java.util.ArrayDeque;
```

## Declaration

```java
Deque<Integer> dq = new ArrayDeque<>();
```

## Characteristics

- Double ended queue
- Insert/remove from both ends

## Common Methods

| Method            | Description           |
| ----------------- | --------------------- |
| `addFirst(E e)`   | Insert front          |
| `addLast(E e)`    | Insert rear           |
| `offerFirst(E e)` | Insert front          |
| `offerLast(E e)`  | Insert rear           |
| `removeFirst()`   | Remove front          |
| `removeLast()`    | Remove rear           |
| `pollFirst()`     | Retrieve/remove front |
| `pollLast()`      | Retrieve/remove rear  |
| `peekFirst()`     | View front            |
| `peekLast()`      | View rear             |
| `size()`          | Size                  |
| `clear()`         | Remove all            |

# 14. ArrayDeque

## Package

```java
import java.util.ArrayDeque;
```

## Characteristics

- Faster than Stack and LinkedList
- Used as stack and queue

## Common Methods

- Same as `Deque`

# 15. Collections Utility Class

## Package

```java
import java.util.Collections;
```

## Common Methods

| Method                       | Description     |
| ---------------------------- | --------------- |
| `sort(list)`                 | Sort ascending  |
| `reverse(list)`              | Reverse list    |
| `shuffle(list)`              | Random shuffle  |
| `max(collection)`            | Maximum element |
| `min(collection)`            | Minimum element |
| `binarySearch(list, key)`    | Binary search   |
| `frequency(collection, obj)` | Count frequency |
| `swap(list, i, j)`           | Swap elements   |
| `fill(list, obj)`            | Fill value      |
| `copy(dest, src)`            | Copy elements   |

# 16. Arrays Utility Class

## Package

```java
import java.util.Arrays;
```

## Common Methods

| Method                   | Description         |
| ------------------------ | ------------------- |
| `sort(arr)`              | Sort array          |
| `binarySearch(arr, key)` | Binary search       |
| `fill(arr, value)`       | Fill array          |
| `equals(arr1, arr2)`     | Compare arrays      |
| `copyOf(arr, size)`      | Copy array          |
| `toString(arr)`          | Convert to string   |
| `deepToString(arr)`      | Nested array string |
| `stream(arr)`            | Convert to stream   |

# 17. Comparator

## Package

```java
import java.util.Comparator;
```

## Example

```java
Comparator<Integer> comp = (a, b) -> b - a;
```

## Used For

- Custom sorting
- PriorityQueue custom ordering
- Collections sorting

## Common Methods

| Method            | Description        |
| ----------------- | ------------------ |
| `compare(a, b)`   | Compare elements   |
| `reversed()`      | Reverse comparator |
| `thenComparing()` | Secondary sorting  |

# 18. Iterator

## Package

```java
import java.util.Iterator;
```

## Example

```java
Iterator<Integer> it = list.iterator();
```

## Common Methods

| Method      | Description       |
| ----------- | ----------------- |
| `hasNext()` | Check next exists |
| `next()`    | Get next element  |
| `remove()`  | Remove current    |

# 19. ListIterator

## Characteristics

- Bidirectional iterator

## Common Methods

| Method          | Description     |
| --------------- | --------------- |
| `hasNext()`     | Forward exists  |
| `next()`        | Move forward    |
| `hasPrevious()` | Backward exists |
| `previous()`    | Move backward   |
| `add(E e)`      | Add element     |
| `set(E e)`      | Update element  |
| `remove()`      | Remove element  |

# 20. Important Interfaces Hierarchy

```text
Iterable
   |
Collection
   |-------------------------------
   |              |               |
 List            Set            Queue
   |              |               |
ArrayList      HashSet         LinkedList
LinkedList     TreeSet         PriorityQueue
Vector         LinkedHashSet   ArrayDeque

Map (Separate Hierarchy)
   |
HashMap
LinkedHashMap
TreeMap
Hashtable
```

# 21. Time Complexities Summary

| Data Structure | Access | Search   | Insert   | Delete   |
| -------------- | ------ | -------- | -------- | -------- |
| Array          | O(1)   | O(n)     | O(n)     | O(n)     |
| ArrayList      | O(1)   | O(n)     | O(1)\*   | O(n)     |
| LinkedList     | O(n)   | O(n)     | O(1)     | O(1)     |
| Stack          | O(n)   | O(n)     | O(1)     | O(1)     |
| Queue          | O(n)   | O(n)     | O(1)     | O(1)     |
| HashSet        | -      | O(1)     | O(1)     | O(1)     |
| TreeSet        | -      | O(log n) | O(log n) | O(log n) |
| HashMap        | -      | O(1)     | O(1)     | O(1)     |
| TreeMap        | -      | O(log n) | O(log n) | O(log n) |
| PriorityQueue  | -      | O(n)     | O(log n) | O(log n) |

# 22. Interview Important Points

## When to Use What?

| Use Case                    | Best Data Structure |
| --------------------------- | ------------------- |
| Fast random access          | Array / ArrayList   |
| Frequent insertion/deletion | LinkedList          |
| Unique elements             | HashSet             |
| Sorted unique elements      | TreeSet             |
| Key-value storage           | HashMap             |
| Sorted key-value storage    | TreeMap             |
| Min/Max retrieval           | PriorityQueue       |
| Stack problems              | Stack / ArrayDeque  |
| Queue problems              | Queue / ArrayDeque  |
| LRU Cache                   | LinkedHashMap       |
| BFS                         | Queue               |
| DFS                         | Stack / Recursion   |

# 23. Competitive Programming Most Used Methods

## ArrayList

```java
list.add(x);
list.get(i);
list.set(i, val);
list.remove(i);
Collections.sort(list);
```

## HashMap

```java
map.put(key, value);
map.get(key);
map.getOrDefault(key, 0);
map.containsKey(key);
```

## HashSet

```java
set.add(x);
set.contains(x);
set.remove(x);
```

## Queue

```java
q.offer(x);
q.poll();
q.peek();
```

## Stack

```java
st.push(x);
st.pop();
st.peek();
```

## PriorityQueue

```java
pq.offer(x);
pq.poll();
pq.peek();
```

# 24. Notes

- `HashMap` does not maintain order.
- `LinkedHashMap` maintains insertion order.
- `TreeMap` sorts keys.
- `HashSet` uses hashing internally.
- `TreeSet` uses Red Black Tree.
- `PriorityQueue` is heap based.
- `ArrayDeque` is preferred over Stack in modern Java.
- `Collections.sort()` works only on objects, not primitive arrays.
- `Arrays.sort()` works for primitive arrays.
