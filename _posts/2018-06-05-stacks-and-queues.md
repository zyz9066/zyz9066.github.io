---
layout: post
title:  "Stacks and Queues"
date:   2018-06-05
tags:  [data structure]
---
# Stacks
PUSH: Inserts (pushes) an element on to the stack at the top of the stack  
POP: Removes (pops) the topmost element of the stack and returns it  
PEEK: Reads the value of topmost element in the stack without removing it  
**LIFO**: **L**ast **I**n **F**irst **O**ut
<!-- Abstract data types -->
# Implementing stacks using arrays
```
maxSize = 9
int[] stackArray = new int[maxSize]
int top = -1

push(5)
push(12)
push(7)
push(2)
```
`peek()`: returns 2 (element pointed by top)  
`pop()`: returns 7 (element pointed by top) and decrements the value of top thus logically removing the topmost element from the stack

Stack is EMPTY

PUSH = $$O(1)$$  
POP = $$O(1)$$  
PEEK = $$O(1)$$
# Queues
HEAD, TAIL  
ENQUEUE: Inserts an element in the queue from tail towards the head  
DEQUEUE: Removes an element in the queue from the head of the queue  
**FIFO**: **F**irst **I**n **F**irst **O**ut

PEEK
# Queues using arrays
```
maxSize = 8
int[] queueArray = new int[maxSize]
int head = -1
int tail = -1

enqueue(8)
enqueue(12)
enqueue(17)

```
`dequeue()`: Returns 8 (remove element at head)  
`peek()`: Returns 12 (element at head)  
`Math.abs(Tail Index - Head Index) < Length of array`  
`Math.abs(7 - 3) = 4 < 8`  
CIRCULAR QUEUE
# Double-ended Queues (DE Queue)
Insert Right, Insert Left
<!-- Double-ended queues using arrays Priority Queue-->
