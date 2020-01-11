---
layout: post
title:  "Java: Data Structures"
date:   2018-06-03
tags:  [java, data structure]
---
# What Are Data Structures?
## Types of data structures
* A data structure is a way of collecting and organizing data.
* Choosing the right data structure impacts efficiency.
* Data comes from many sources (e.g., databases and files).
* Many data structures are implemented as linked lists.

* ArrayList - stores objects and can grow and shrink
* LinkedList - uses pointers to keep track of elements
* Vector - can grow and shrink; provides synchronization
* Stack - operates on last in, first out (LIFO)
* Queue - operates on first in, first out (FIFO)

* Collections framework
* Iterable interface

## Pros and Cons
### ArrayList and Vector Advantages
* Provide fast access using indexing
* Memory coherence
* Provide an initial size (optional)
* Use internal arrays for storage, which makes random access fast

### ArrayList and Vector Disadvantages
* Can be time consuming to add elements in the middle
* Waste space if array is not full
* Need to be resized when they reach capacity
* Slower when deleting elements from the middle

### LinkedList Advantages
* Insertion and deletion operations are easily implemented.
* Elements are efficiently added or deleted from the middle of the list.

### LinkedList Disadvantages
* Elements in a linked list must be read sequentially.
* Elements are not stored sequentially in memory.
* Random access to elements can be inefficient.
* Slower iterations and extra memory overhead are required.

## Java Documentation
### Oracle Java Documentation
* [Java API documentation](https://docs.oracle.com/javase/7/docs/api/)
* Includes all packages, classes, and interfaces
* Shows any deprecated classes, methods, etc.

# Using Data Structures
## Collections Framework
### Collection Interface
Collection: Set, Queue, List
* Set: TreeSet, SortedSet, HashSet
* Queue: PriorityQueue, Deque
* List: Vector, ArrayList, LinkedList
Vector: Stack

### Collections Framework
* It provides implementations of data structures.
* There is a Collections class that has static methods.
* The static methods can be used to sort, search, copy, and fill.
* Each method throws a NullPointerException if objects are null.

### Collection Interface
* It defines common operations for data structures.
* Lists store an ordered collection of elements.
* A set stores a group of nonduplicate elements.
* Queues store objects that are processed in the FIFO order.
* Collections are sometimes referred to as containers.
* They are used to store, retrieve, manipulate, and aggregate.
* Some containers store a collection of elements.
* Other containers store key/value pairs, called maps.
* The interface provides basic operations for add and remove.
* It also provides important query operations.
* A commonly used method is `toArray()`, which returns an array.
* To convert from an array to a list, use `Arrays.toList()`.

## Iterable interface
* Each collection has an Iterator object to traverse the elements.
* It provides the tools for walking through a data structure.
* It hides the details of how data is stored.
* The Collection interface extends the Iterable interface.
* Methods in the Iterable interface are `iterator(), foreach()`.
* The `iterator()` method returns an Iterator object.
* The Iterator includes `hasNext(), next(), remove()`.
* The Iterable interface is used to traverse the elements.
* In addition to the Iterable interface, there is a ListIterator.
* The ListIterator is used for list data structures.
* This adds functionality to traverse the list backward.
* Methods include `previous(), hasPrevious(), previousIndex()`.

## ArrayLists
* Implements the List interface
* Is the most frequently used data structure
* Creates an object array that grows as needed
* Can contain duplicate elements
* An ArrayList can hold null values.
* It is not inherently thread safe.
* Quick access is provided to elements based in index position.
* Developers can add or remove elements by index value.
* Easily find the index of the first occurrence of an element.
* The initial size capacity can be set when create.
* The `trimTo()` method can reduce the size.

## LinkedLists
* Prior to Java 7, linked lists were created manually.
* Now, there is a LinkedList class included in the API.
* Access to the elements is linear.
* It uses a doubly linked list to manage the collection of objects.

### Doubly Linked List
Uses a ListIterator to travel backward through the list
## Vectors
* Included with the first release of Java
* Similar to the behavior of an ArrayList
* Automatically provides synchronization, which causes its performance to suffer

## Stacks
* A stack uses a last in, first out order (LIFO).
* It is vertical stack of objects.
* The last element added is the first to come off.
* Items are added and deleted from the same end.
* To add an item, you use the `push()` method.
* To remove an item, you use `pop()`.
* The `peek()` method makes a copy of the first item.
* A stack is an easy way to reverse a collection of values.

## Queues
* A linear list is where items are added to one end and deleted from the other end.
* Examples include waiting in line at a sporting event.
* People join the queue at the end and exit from the front.
* Another example is a print queue.
* `add()` - used to add elements to the end
* `peek()` - returns a copy of the first element
* `remove()` - removes the top element; error if empty
* `poll()` - removes from the top; returns null if the queue is empty
