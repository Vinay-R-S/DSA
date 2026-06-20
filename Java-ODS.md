# Optimized Java Data Structures and Methods Master Reference

# Goal of This Document

This guide focuses on:
- Most optimized modern Java Data Structures
- Best implementations for time + space
- Competitive Programming usage
- Interview preferred implementations
- Real-world recommended usage
- Important methods with examples

# 1. Array

## Best Use Case
- Fixed size data
- Fastest random access
- Primitive storage

## Declaration
```java
int[] arr = new int[5];
int[] nums = {1,2,3,4};
```

## Time Complexities

| Operation | Complexity |
|---|---|
| Access | O(1) |
| Update | O(1) |
| Search | O(n) |
| Insert | O(n) |
| Delete | O(n) |

## Important Methods

### Access
```java
arr[0]
```

### Update
```java
arr[1] = 10;
```

### Length
```java
arr.length
```

### Traversal
```java
for(int x : arr){
    System.out.println(x);
}
```

# 2. ArrayList (MOST OPTIMIZED LIST)

## Why Preferred?
- Best cache locality
- Faster traversal
- Faster random access
- Lower memory overhead than LinkedList
- Most used List implementation

## Package
```java
import java.util.ArrayList;
```

## Declaration
```java
ArrayList<Integer> list = new ArrayList<>();
```

## Time Complexities

| Operation | Complexity |
|---|---|
| Access | O(1) |
| Add End | O(1)* |
| Insert Middle | O(n) |
| Delete | O(n) |
| Search | O(n) |

## Important Methods

### add(E e)
```java
list.add(10);
```

### add(index, element)
```java
list.add(1, 50);
```

### get(index)
```java
list.get(0);
```

### set(index, value)
```java
list.set(0, 100);
```

### remove(index)
```java
list.remove(1);
```

### remove(object)
```java
list.remove(Integer.valueOf(10));
```

### size()
```java
list.size();
```

### contains()
```java
list.contains(50);
```

### clear()
```java
list.clear();
```

### isEmpty()
```java
list.isEmpty();
```

### indexOf()
```java
list.indexOf(50);
```

### lastIndexOf()
```java
list.lastIndexOf(50);
```

### sort()
```java
Collections.sort(list);
```

### reverse()
```java
Collections.reverse(list);
```

### Traversal
```java
for(int x : list){
    System.out.println(x);
}
```

# 3. LinkedList (USE ONLY WHEN NEEDED)

## Why Usually Avoided?
- Higher memory usage
- Poor cache locality
- Slower traversal
- Random access O(n)

## Use Only For
- Frequent insertion/deletion in middle
- Heavy iterator operations

## Declaration
```java
LinkedList<Integer> list = new LinkedList<>();
```

## Important Methods

### addFirst()
```java
list.addFirst(10);
```

### addLast()
```java
list.addLast(20);
```

### getFirst()
```java
list.getFirst();
```

### getLast()
```java
list.getLast();
```

### removeFirst()
```java
list.removeFirst();
```

### removeLast()
```java
list.removeLast();
```

### peekFirst()
```java
list.peekFirst();
```

### peekLast()
```java
list.peekLast();
```

# 4. Stack (OPTIMIZED USING ARRAYDEQUE)

## Best Modern Implementation
```java
Deque<Integer> st = new ArrayDeque<>();
```

## Why NOT Stack Class?
- Legacy class
- Synchronized
- Slower

## Time Complexities

| Operation | Complexity |
|---|---|
| push | O(1) |
| pop | O(1) |
| peek | O(1) |

## Important Methods

### push()
```java
st.push(10);
```

### pop()
```java
st.pop();
```

### peek()
```java
st.peek();
```

### isEmpty()
```java
st.isEmpty();
```

### size()
```java
st.size();
```

# 5. Queue (BEST IMPLEMENTATION = ARRAYDEQUE)

## Best Modern Queue
```java
Queue<Integer> q = new ArrayDeque<>();
```

## Why Preferred?
- Faster than LinkedList
- Less memory overhead
- Better cache performance

## Time Complexities

| Operation | Complexity |
|---|---|
| offer | O(1) |
| poll | O(1) |
| peek | O(1) |

## Important Methods

### offer()
```java
q.offer(10);
```

### poll()
```java
q.poll();
```

### peek()
```java
q.peek();
```

### isEmpty()
```java
q.isEmpty();
```

### size()
```java
q.size();
```

# 6. PriorityQueue (HEAP)

## Best Use Case
- Min/Max retrieval
- Dijkstra
- Top K problems
- Scheduling

## Declaration

### Min Heap
```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
```

### Max Heap
```java
PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
```

## Time Complexities

| Operation | Complexity |
|---|---|
| offer | O(log n) |
| poll | O(log n) |
| peek | O(1) |

## Important Methods

### offer()
```java
pq.offer(10);
```

### poll()
```java
pq.poll();
```

### peek()
```java
pq.peek();
```

### size()
```java
pq.size();
```

### isEmpty()
```java
pq.isEmpty();
```

# 7. HashSet (BEST GENERAL SET)

## Why Preferred?
- Average O(1)
- Fastest Set implementation

## Declaration
```java
HashSet<Integer> set = new HashSet<>();
```

## Time Complexities

| Operation | Complexity |
|---|---|
| add | O(1) |
| remove | O(1) |
| contains | O(1) |

## Important Methods

### add()
```java
set.add(10);
```

### remove()
```java
set.remove(10);
```

### contains()
```java
set.contains(10);
```

### size()
```java
set.size();
```

### clear()
```java
set.clear();
```

# 8. LinkedHashSet

## Use Case
- Need insertion order + uniqueness

## Declaration
```java
LinkedHashSet<Integer> set = new LinkedHashSet<>();
```

## Important Methods
- Same as HashSet

# 9. TreeSet

## Use Case
- Sorted unique elements

## Internal DS
- Red Black Tree

## Declaration
```java
TreeSet<Integer> ts = new TreeSet<>();
```

## Time Complexities

| Operation | Complexity |
|---|---|
| add | O(log n) |
| remove | O(log n) |
| contains | O(log n) |

## Important Methods

### first()
```java
ts.first();
```

### last()
```java
ts.last();
```

### higher()
```java
ts.higher(10);
```

### lower()
```java
ts.lower(10);
```

### ceiling()
```java
ts.ceiling(10);
```

### floor()
```java
ts.floor(10);
```

# 10. HashMap (MOST IMPORTANT MAP)

## Why Preferred?
- Average O(1)
- Fastest Map implementation
- Most used DS in interviews and CP

## Declaration
```java
HashMap<Integer, Integer> map = new HashMap<>();
```

## Time Complexities

| Operation | Complexity |
|---|---|
| put | O(1) |
| get | O(1) |
| remove | O(1) |

## Important Methods

### put()
```java
map.put(1, 100);
```

### get()
```java
map.get(1);
```

### getOrDefault()
```java
map.getOrDefault(5, 0);
```

### containsKey()
```java
map.containsKey(1);
```

### containsValue()
```java
map.containsValue(100);
```

### remove()
```java
map.remove(1);
```

### keySet()
```java
map.keySet();
```

### values()
```java
map.values();
```

### entrySet()
```java
map.entrySet();
```

### Traversal
```java
for(Map.Entry<Integer,Integer> e : map.entrySet()){
    System.out.println(e.getKey() + " " + e.getValue());
}
```

# 11. LinkedHashMap

## Use Case
- Maintain insertion order
- LRU Cache

## Declaration
```java
LinkedHashMap<Integer,Integer> map = new LinkedHashMap<>();
```

## Important Methods
- Same as HashMap

# 12. TreeMap

## Use Case
- Sorted keys

## Internal DS
- Red Black Tree

## Declaration
```java
TreeMap<Integer,Integer> tm = new TreeMap<>();
```

## Time Complexities

| Operation | Complexity |
|---|---|
| put | O(log n) |
| get | O(log n) |
| remove | O(log n) |

## Important Methods

### firstKey()
```java
tm.firstKey();
```

### lastKey()
```java
tm.lastKey();
```

### higherKey()
```java
tm.higherKey(10);
```

### lowerKey()
```java
tm.lowerKey(10);
```

### ceilingKey()
```java
tm.ceilingKey(10);
```

### floorKey()
```java
tm.floorKey(10);
```

# 13. Deque (DOUBLE ENDED QUEUE)

## Best Implementation
```java
Deque<Integer> dq = new ArrayDeque<>();
```

## Use Cases
- Sliding Window
- Monotonic Queue
- Stack + Queue together

## Important Methods

### addFirst()
```java
dq.addFirst(10);
```

### addLast()
```java
dq.addLast(20);
```

### removeFirst()
```java
dq.removeFirst();
```

### removeLast()
```java
dq.removeLast();
```

### peekFirst()
```java
dq.peekFirst();
```

### peekLast()
```java
dq.peekLast();
```

# 14. ArrayDeque (MOST OPTIMIZED GENERAL PURPOSE DS)

## Why Extremely Important?
- Faster than Stack
- Faster than LinkedList Queue
- Dynamic Circular Array
- Best modern Stack + Queue implementation

## Declaration
```java
ArrayDeque<Integer> dq = new ArrayDeque<>();
```

## Important Methods

### push()
```java
dq.push(10);
```

### pop()
```java
dq.pop();
```

### offer()
```java
dq.offer(20);
```

### poll()
```java
dq.poll();
```

### peek()
```java
dq.peek();
```

# 15. Collections Utility Class

## Package
```java
import java.util.Collections;
```

## Important Methods

### sort()
```java
Collections.sort(list);
```

### reverse()
```java
Collections.reverse(list);
```

### shuffle()
```java
Collections.shuffle(list);
```

### max()
```java
Collections.max(list);
```

### min()
```java
Collections.min(list);
```

### binarySearch()
```java
Collections.binarySearch(list, 10);
```

### frequency()
```java
Collections.frequency(list, 10);
```

### swap()
```java
Collections.swap(list, 0, 1);
```

# 16. Arrays Utility Class

## Package
```java
import java.util.Arrays;
```

## Important Methods

### sort()
```java
Arrays.sort(arr);
```

### binarySearch()
```java
Arrays.binarySearch(arr, 10);
```

### fill()
```java
Arrays.fill(arr, 0);
```

### equals()
```java
Arrays.equals(arr1, arr2);
```

### copyOf()
```java
Arrays.copyOf(arr, 5);
```

### toString()
```java
Arrays.toString(arr);
```

### deepToString()
```java
Arrays.deepToString(matrix);
```

# 17. Comparator

## Use Case
- Custom sorting
- PriorityQueue custom ordering

## Declaration
```java
Comparator<Integer> comp = (a,b) -> b - a;
```

## Example

### Descending Sort
```java
Collections.sort(list, (a,b) -> b-a);
```

### PriorityQueue Max Heap
```java
PriorityQueue<Integer> pq = new PriorityQueue<>((a,b)->b-a);
```

# 18. Iterator

## Declaration
```java
Iterator<Integer> it = list.iterator();
```

## Important Methods

### hasNext()
```java
it.hasNext();
```

### next()
```java
it.next();
```

### remove()
```java
it.remove();
```

# 19. ListIterator

## Use Case
- Bidirectional traversal

## Declaration
```java
ListIterator<Integer> it = list.listIterator();
```

## Important Methods

### hasPrevious()
```java
it.hasPrevious();
```

### previous()
```java
it.previous();
```

### add()
```java
it.add(10);
```

### set()
```java
it.set(100);
```

# 20. Optimized DS Recommendation Table

| Requirement | Best DS |
|---|---|
| Fast random access | Array / ArrayList |
| Dynamic list | ArrayList |
| Stack | ArrayDeque |
| Queue | ArrayDeque |
| Double ended queue | ArrayDeque |
| Fast search unique elements | HashSet |
| Sorted unique elements | TreeSet |
| Fast key-value storage | HashMap |
| Sorted map | TreeMap |
| Priority based retrieval | PriorityQueue |
| LRU Cache | LinkedHashMap |
| Sliding Window | ArrayDeque |
| BFS | Queue + ArrayDeque |
| DFS | Stack using ArrayDeque |

# 21. Time Complexity Summary

| DS | Access | Search | Insert | Delete |
|---|---|---|---|---|
| Array | O(1) | O(n) | O(n) | O(n) |
| ArrayList | O(1) | O(n) | O(1)* | O(n) |
| LinkedList | O(n) | O(n) | O(1) | O(1) |
| ArrayDeque | O(1) | O(n) | O(1) | O(1) |
| HashSet | - | O(1) | O(1) | O(1) |
| TreeSet | - | O(log n) | O(log n) | O(log n) |
| HashMap | - | O(1) | O(1) | O(1) |
| TreeMap | - | O(log n) | O(log n) | O(log n) |
| PriorityQueue | - | O(n) | O(log n) | O(log n) |

# 22. Most Important Competitive Programming Templates

## Fast Frequency Map
```java
HashMap<Integer,Integer> freq = new HashMap<>();
freq.put(x, freq.getOrDefault(x,0)+1);
```

## Fast Stack
```java
Deque<Integer> st = new ArrayDeque<>();
```

## Fast Queue
```java
Queue<Integer> q = new ArrayDeque<>();
```

## Max Heap
```java
PriorityQueue<Integer> maxHeap = new PriorityQueue<>((a,b)->b-a);
```

## Min Heap
```java
PriorityQueue<Integer> minHeap = new PriorityQueue<>();
```

## Fast Unique Storage
```java
HashSet<Integer> set = new HashSet<>();
```

# 23. Modern Java Best Practices

## DO
- Prefer ArrayDeque over Stack
- Prefer ArrayDeque over LinkedList Queue
- Prefer ArrayList over LinkedList
- Use HashMap for most map problems
- Use HashSet for fastest uniqueness checking

## AVOID
- Stack class
- Vector class
- Hashtable
- LinkedList unless specifically needed

# 24. Interview Important Notes

## HashMap
- Allows one null key
- Multiple null values allowed
- Unordered

## TreeMap
- Sorted by keys
- No null keys

## HashSet
- Backed internally by HashMap

## PriorityQueue
- Min Heap by default

## ArrayDeque
- No null elements allowed

## ArrayList
- Dynamic resizing array

## LinkedList
- Doubly linked list

