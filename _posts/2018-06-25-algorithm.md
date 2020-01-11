---
layout: post
title:  "Algorithm"
date:   2018-06-25
tags:  [algorithm]
---
# Algorithms and Data Structure Overview
## What are algorithms are
* Self-contained sequence of actions
* Perform calculations, data processing, and automated tasks
* Efficient code

## When to really use algorithms
* Compressing data
* Sorting
* Generating random numbers

# Linked List
* Collection of items, in nodes
* Like arrays, but with less limitations

```C#
int[] myArray = new int[50];
```
Head NULL  
Head Tail
# Stack
* A stack is an abstract data type that serves as a collection of elements.
* The stack has two principal operations: push and pop.
* LIFO (last in, first out)

# Queue
A queue is a data structure that serves as a collection of elements.  
Two Main features
* Enqueue
* Dequeue

FIFO (first in, first out)

People in a line
# Binary Search
* Finds the position of a target value within a sorted array
* Continuously compares the target value to the middle element of the array and eliminates irrelevant half of array

Variables to remeber
* The a variable is the array.
* The n variable is the length of array (a.length-1).

~~~~~~~
Function  
Binary search (a,x)

Inputs
a: the array to search inside of
x: the value we are searching for in a

Ouputs
The index position where a[i]==x or -1 if not found

Steps
1. Set p to 0 & set r to n
2. While p<=r, do something
    Set q to [(p+r)/2]
    If x<a[q], then set r=q-1.
    elseIf x>a[q], then set p=q+1
        else return q.
3. Return -1
~~~~~~~
# Linear Search
* Searches target value within a list
* Checks each element of the list until match found or rearches end

Go through these positions, until element found, and then stop
~~~~~~~
Function  
Linear search (a,x)

Inputs
a: the array to search inside of
x: the value we are searching for in a

Ouputs
The index position where a[i]==x or -1 if not found

Steps
1. Set answer to -1
2. For each index i going from 1 to n (last position of a), in order
    if a[i]==x, then set answer to the value of i
3. Return the value of answer as the output
~~~~~~~