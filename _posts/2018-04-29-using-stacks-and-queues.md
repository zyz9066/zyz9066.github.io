---
layout: post
title:  "Using Stacks and Queues"
date:   2018-04-29
tags:  [data structure]
---
# Using stacks for last-in, first-out
### Using Stacks

|789|
|456|
|123|

`myStack`\\
**Last In, First Out (LIFO)**

||
|456|
|123|

`myStack.push(342);`

|342|
|456|
|123|

`int topElement = myStack.pop();`\\
topElement = 342

||
|456|
|123|

`int topValue = myStack.peek();`\\
topValue = 456

||
|456|
|123|

### Stack - language support

|Java| [`Stack`](https://docs.oracle.com/javase/7/docs/api/java/util/Stack.html "Stack") (`push` / `pop` / `peek`) |
|C#| [`Stack`](https://msdn.microsoft.com/en-us/library/system.collections.stack(v=vs.110).aspx "Stack") (`push` / `pop` / `peek`) |
|Python| use [`lists`](https://docs.python.org/2/tutorial/datastructures.html#using-lists-as-stacks "Using lists as stacks") (`append` / `pop`) |
|Ruby| use [`Array`](http://ruby-doc.org/core-2.5.0/Array.html "Array") (`push` / `pop`) |
|Objective-C| use `NSMutableArray` |
|C++| `std::stack` (`push` / `pop`) |

# Using queues for first-in, first-out
### Using queues

|123|456|789|

`myQueue`\\
**First In, First Out (FIFO)**

|456|789||

### Queue - language support

|Java| [`LinkedList`](https://docs.oracle.com/javase/7/docs/api/java/util/LinkedList.html "LinkedList") (`add` / `remove`) |
|C#| [`Queue`](https://msdn.microsoft.com/en-us/library/system.collections.queue%28v=vs.110%29.aspx "Queue Class") (`enqueue` / `dequeue`) |
|Python| [`queue`](https://docs.python.org/2/library/queue.html "Queue") (`put` / `get`) |
|Ruby| use `Array` (`push` / `shift`) |
|Objective-C| `NSMutableArray` (`addObject` / `removeObjectAtIndex:0`) |
|C++| `std::queue` (`push_back` / `pop_front`)|

Java - `java.util`: [Interface `Queue<E>`](https://docs.oracle.com/javase/7/docs/api/java/util/Queue.html "Queue")

Ruby: [Queue](http://ruby-doc.org/stdlib-1.9.3/libdoc/thread/rdoc/Queue.html "Queue") - This class provides a way to synchronize communication between threads.

# Priority queues and dequeues
### Using priority queues

|123(2)|456(2)|789(2)||

`myPriorityQueue`

|123(2)|456(2)|789(2)|321(1)|

**Typically requires a comparator or compare function**

|321(1)|123(2)|456(2)|789(2)|

### Priority queue - language support

|Java| `PriorityQueue` |
|C#| n/a |
|Python| n/a |
|Ruby| n/a |
|Objective-C| `CFBinaryHeap` |
|C++| `std::priority_queue` |

### Using a deque
Double-ended Queue

|123|456|789|

`myDeque`

|321|456|987|

### Deque - language support

|Java| `LinkedList` implements `Deque` |
|C#| n/a - use `LinkedList` for equivalent |
|Python| `collections.deque` |
|Ruby| n/a - use `Array` |
|Objective-C| n/a - use `NSMutableArray` |
|C++| `std::deque` |

Caution! **Deque vs Dequeue**