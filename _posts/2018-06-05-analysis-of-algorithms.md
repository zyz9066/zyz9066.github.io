---
layout: post
title:  "Analysis of Algorithms"
date:   2018-06-05
tags:  [algorithm]
---
# Analysis of Algorithms
Space complexity  
<big>Time complexity</big>
# How to calculate the time complexity
## How to measure time?
100 - 10 ms

|ITEMS|Algorithm 1(ms)<br>LINEAR GROWTH|Algorithm 2(ms)<br>QUADRATIC GROWTH|
|:-:|:-:|
|200|20|40|
|1000|100|1000|
|10000|1000|100000|

Order of time or Growth of time
# The RAM model of computation
## Types of Time Complexity
* Worst Case $$\surd$$
* Best Case
* Average Case $$\times$$

## RAM Model of Computation
* We have infinite memory.
* Each operation(+,-,\*,/,=) takes unit time.
* For each memory access, unit time is consumed.
* Data may be accessed from RAM or disk, it is assumed that the data is in the RAM.

# Time complexity of bubble sort algorithm
Bubble Sort  
$$\begin{array}{c|c}
Comparison & Swap\\
\hline
1 & 3
\end{array}$$  
Worst Case (5 digits)
$$16+12+8+4\\
=4(4+3+2+1)\\
=4(n-1+n-2+...+2+1)$$
# Pseudo code: Bubble sort algorithm
Bubble Sort  
Pseudo-code:
```
for i=0 to A.length-2
  for j=0 to A.length-2-i
    if A[j]>A[j+1]
      tmp=A[j+1]
      A[j+1]=A[j]
      A[j]=tmp
```
```java
int tmp;
for (int i=0; i < A.length-1; i++) {
  for (int j=0; j < A.length-1-i; j++) {
    if (A[j] > A[j+1]) {
      tmp = A[j+1];
      A[j+1] = A[j];
      A[j] = tmp;
    }
  }
}
```
$$\begin{array}{c|c|c}
i=0 & 0\leq j<n-2 & (n-1)\\
i=1 & 0\leq j<n-3 & (n-2)\\
\vdots & \vdots & \vdots\\
i=n-2 & 0\leq j<0 & 1
\end{array}$$
where `n = A.length`
```
for i=1 to A.length-1
  for j=1 to A.length-1-i
    if A[j]>A[j+1]
      tmp=A[j+1]
      A[j+1]=A[j]
      A[j]=tmp
```
# The Big O notation
Time, n  
OBSERVATIONS:
$$\forall n>n_0,c_2 n^2\ge pn^2+qn+r$$
## Big O
$$\small O(n^2)=\{ f(n):\exists positive\,constants\,c\,and\,n_0\,such\,that\,0\le f(n)\le cn^2\,for\,all\,n>n_0\}$$
$$\small O(g(n))=\{ f(n):\exists positive\,constants\,c\,and\,n_0\,such\,that\,0\le f(n)\le cg(n)\,for\,all\,n>n_0\}$$
# Using Big O notation: Examples
$$5n^2+6\in O(n^2)$$  
$$\begin{array}{lll}
cn^2 & c=6 & n_0=3\\
& c=5.1 & n_0=8
\end{array}$$

$$5n+6\in O(n^2)$$  
$$\begin{array}{lll}
cn^2 & c=11 & n_0=1\\
\end{array}$$

$$n^3+2n^2+4n+8\in O(n^2)$$  
$$cn^2\ge n^3+2n^2+4n+8$$

$$a_mn^m+a_{m-1}n^{m-1}+\cdots +a_0\in O(n^m)$$

$$log\,n\le\sqrt{n}\le n\le n\,log\,n\le n^2\le n^3\le 2^n\le n!$$

# Comparison of running times
`int[] a={1,3,7,8,9,2}`  
access `a[4]`  
`int[] b={5,8,1,...,25,20}` 100 Elements  
access `b[98]`  
$$O(1)$$: Constant Time

$$T_5\approx 50ms,T_{10}\approx 100ms$$  
$$T_{Search}=O(n)$$

A loop inside a loop in an algorithm usually represents a time complexity of $$O(n^2)$$

$$n-1+n-2+\cdots +1$$
