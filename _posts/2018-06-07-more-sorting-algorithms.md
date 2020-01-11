---
layout: post
title:  "More Sorting Algorithms"
date:   2018-06-07
tags:  [algorithm]
---
# Quicksort
Worst Case: $$O(n^2)$$  
Average Case: $$O(n\,log\,n)$$  
In place sorting
## The Partition Step
PIVOT  
Pseudo-code:
```
Partition(A, start, end)
  pivot = A[end]
  i = start
  for j=start to end-1
    if A[j]<=pivot
      exchange A[i] with A[j]
      i=i+1
  exchange A[i] with A[end]
```
## The Algorithm
Pseudo-code
```
QuickSort(A, start, end)
  if start < end
  pivot = Partition(A, start, end)
  QuickSort(A, start, pivot-1)
  QuickSort(A, pivot+1, end)
```
# Shell sort
Insertion Sort  
>$$O(n^{7/6})-O(n^{3/2})$$
<cite>&mdash; Robert Lafore (D.S & Algorithms in java)</cite>

## Knuth Sequence
$$\begin{align}
\large h&=3h+1\\
h&=1\\
h&=4\\
h&=13\\
h&=40\\
h&=121\\
\vdots\\
Up\;to\;h&<data.length
\end{align}$$
<!-- Shell sort example -->
# Sorting In Linear Time
* Counting Sort  
Data Array of size n: n Reads  
Temp: n Writes, k+1 Reads  
Sorted Data Array of size n: n Writes  
$$O(n)$$
* Radix Sort
* Bucket Sort or Bin-Sort
