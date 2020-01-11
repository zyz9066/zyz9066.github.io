---
layout: post
title:  "Binary Search Trees"
date:   2018-06-07
tags:  [data structure]
---
# The tree data structures
$$\begin{array}{rc|c}
&\large\underline{Sorted\;Arrays}&\large\underline{Linked\;List}\\
Search:&Fast\;(O(log\,n))&Slow\;(O(n))\\
Insert:&Slow\;(O(n))&Fast\;(O(1))\\
Delete:&Slow\;(O(n))&Fast\;(O(1))
\end{array}$$
## Trees
Nodes, Edges  
Root, Parent, Children, Leaf Node, SUBTREE, Level
# Binary trees
A Tree Node  
Data, Left, Right
<!-- Binary search trees -->
<!-- Finding an item in a binary search tree -->
<!-- Implementing the find method -->
<!-- Inserting an item in a binary search tree -->
# Deleting A Node
Case 1: Node to be deleted is a leaf  
Case 2: Node to be deleted has one child  
Case 3: Node to be deleted has two children, Successor
<!-- Finding smallest and largest values -->
# Tree traversal
* In order
* Pre Order
* Post Order

## In-Order Traversal
1. Traverse the left sub tree.
2. Visit the root.
3. Traverse the right sub tree.

## Pre-Order
1. Visit the root.
2. Traverse the left sub tree.
3. Traverse the right sub tree.

## Post-Order
1. Traverse the left sub tree.
2. Traverse the right sub tree.
3. Visit the root.

<!-- Unbalanced trees vs. balanced trees -->
# Height of a binary tree
$$Layer\;1\;(2^0)\\
Layer\;2\;(2^1)\\
Layer\;3\;(2^2)\\
\vdots\\
Layer\;h\;(2^{h-1})$$  
$$\begin{align}
1+2+4+\cdots+2^{h-1}&=n\\
\frac{(2^h-1)}{(2-1)}&=n\\
or,\;2^h&=n+1\\
or,\;h&=log_2(n+1)\\
&O(log_2\;n)
\end{align}$$
# Time complexity of operations on binary search trees
$$Search(item)=O(log_2\;n)$$  
$$Delete(item)=O(log_2\;n)$$  
$$Insert(item)=O(log_2\;n)$$
