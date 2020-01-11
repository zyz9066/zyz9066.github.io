---
layout: post
title:  "Sets, Trees, and Graphs"
date:   2018-04-30
tags:  [data structure]
---
# Using sets
**Working with sets**
* A set is an *unordered* collection of objects
* No index, sequence, or key
* No duplicates
* Fast lookup - for checking membership, not retrieval
![]({{site.baseurl}}/images/data structure/sets.jpg)

`mySet.contains(obj5);` Yes\\
`mySet.contains(obj9);` No
### Set implementation with hash table

|0||
|1||
|2||
|3||
|...|...|

`mySet.add(obj1);`
~~~~~~~
obj1-->| hash function |-->3
~~~~~~~

|0||
|1||
|2||
|3|obj1|
|...|...|

`mySet.add(obj2);`
~~~~~~~
obj2-->| hash function |-->0
~~~~~~~

|0|obj2|
|1||
|2||
|3|obj1|
|...|...|

`if (mySet.contains(obj1))`
~~~~~~~
obj1-->| hash function |-->3
~~~~~~~

|0|obj2|
|1||
|2||
|3|**obj1**|
|...|...|

### Sets - language support

|Java|`HashSet`|
|C#|`HashSet`|
|Python|`set` / `frozenset`|
|Ruby|`Set`|
|Objective-C|`NSSet`, `NSMutableSet`|
|C++|`std::set`|

# Introduction to tree data structures
### Tree data structure
Linked List
![]({{site.baseurl}}/images/data structure/lists.jpg)
Binary tree
![]({{site.baseurl}}/images/data structure/tree.jpg)
siblings: child nodes with same parent\\
leaf node: node with no children
# Understanding binary search trees (BST)
### Binary search tree (BST)
Child nodes: left child (LESS than parent) / right child (MORE than parent)\\
No duplicate keys.
![]({{site.baseurl}}/images/data structure/BST.jpg)
Unbalanced BST
![]({{site.baseurl}}/images/data structure/UBST.jpg)
### BST implementation
**Self-Balancing algorithms** includes:
* Red-Black Trees
* AVL Trees
* Splay Trees
* Scapegoat Trees

### BST / Hash Table comparison

|BST|Hash Table|
|-
|Fast insertion, fast retrieval|Fast insertion, fast retrieval|
|Stays sorted - iterate elements in sequence|Retrieval not in guaranteed order|

### BST - language support

|Java|[`TreeMap`](https://docs.oracle.com/javase/7/docs/api/java/util/TreeMap.html "TreeMap<K,V>")|
|C#|[`SortedDictionary`](https://msdn.microsoft.com/en-us/library/f7fta44c(v=vs.110).aspx "SortedDictionary<TKey, TValue>")|
|Python|n/a|
|Ruby|n/a|
|Objective-C|n/a|
|C++|`std::set`|

# Heap data structures
### Heap implementation
Heaps are implemented as Binary Trees - balanced\\
**Min** Heap or **Max** Heap? - Lowest (or highest) value at the top of the heap
* Min heaprule: a child must always be *greater* than* its parent
* Max heaprule: a child must always be *less* than* its parent

Min Heap
![]({{site.baseurl}}/images/data structure/heap.jpg)
A heap is not a fully sorted data sturcture.

### Heap - language support

|Java|[`PriorityQueue`](https://docs.oracle.com/javase/7/docs/api/java/util/PriorityQueue.html "PriorityQueue<E>")|
|C#|n/a|
|Python|[`heapq`](https://docs.python.org/2/library/heapq.html "heapq")|
|Ruby|n/a|
|Objective-C|[`CFBinaryHeap`](https://developer.apple.com/documentation/corefoundation/cfbinaryheap-s11 "CFBinaryHeap")|
|C++|`std::priority_queue`|

Python: `heapq` - Heaps are binary trees for which every parent node has a value less than or equal to any of its children.\\
Objective-C:  `CFBinaryHeap` - Binary heaps can be useful as priority queues.\\
Java: `PriorityQueue` - An unbounded priority queue based on a priority heap.
# Introduction to graphs
Linked List Data Structure
![]({{site.baseurl}}/images/data structure/lists.jpg)
Tree Data Structure
![]({{site.baseurl}}/images/data structure/tree.jpg)
**Graphs**: Multiply links to each other nodes\\
Terminology: nodes - vertices (singular: vertex), connection - edges\\
Directed / Undirected Graphs: oneway or not\\
Weighted Graphs: value on edges\\
### Graph implementation
Generic "Graph" - **NO** language support
* Linked List
* Trees
* Heaps

## Review
**Arrays**
* Strengths: Direct indexing, Easy to create and use
* Weaknesses: Sorting and searching, Inserting and deleting - particularly if not at start / end

**Linked List**
* Strengths: Inserting and deleting elements, Iterating through the collection
* Weaknesses: Direct access, Searching and sorting

**Stacks and Queues**
* Strengths: Designed for LIFO / FIFO
* Should not be used for: Direct access, Searching and sorting

**Hash Tables**
* Strengths: Speed of insertion and deletion, Speed of access
* Weaknesses: Some overhead, Retrieving in a sorted order, Searching for a specific value

**Sets**
* Strengths: Checking if an object is in a collection, Avoiding duplicates
* Do not use for: Direct access

**Binary Search Trees**
* Strengths: Speed of insertion and deletion, Speed of access, Maintaining sorted order
* Weaknesses: Some overhead

**Fixed Structures are Faster / Smaller**\\
*Choose a fixed (immutable) version where possible*\\
If you need an immutable version to load, consider then copying to a mutable version for lookup