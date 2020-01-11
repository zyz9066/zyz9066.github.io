---
layout: post
title:  "Recursion"
date:   2018-06-06
tags:  [algorithm]
---
# Introduction
## Euclid's algorithm
```java
public int gcd (int a, int b) {
  if (b == 0) return a; // Breaking Condition
  return gcd (b, a%b);
}
```
## Calculating Factorials
```java
public int factorial (int n) {
  int result = 1;
  for(int i=1;i<n;i++) {
    result *= i;
  }
  return result;
}
```
Iterative Way  
$$factorial(n)=n*(n-1)*(n-2)*\cdots*1$$  
$$factorial(n)=n*factorial(n-1)$$
```java
public int factorial (int n) {
  return n*factorial(n-1);
}
```
# Understanding recursion
```java
public int factorial(int n) {
  if(n == 0) return 1;
  return n*factorial(n-1);
}
```
Stack Overflow
# Tail recursion
```java
public int factorial (int n, int result) { // ACCUMULATOR
  if (n == 0) return result;
  return factorial(n-1, n*result)
}

factorial (int n) {
  return factorial(n,1);
}
```
* Accumulator - Because it accumulates values of previous calculation, giving us a definite value everytime
* For this type of recursion, we do not need stacks
* The complier of the language should be able to identify it as recursion and Java is not able to do so, hence it will still make use of stack and stack frames and is not able to make use of tail recursion
* Functional programming languages are able to optimize for tail recursion
# Tower of Hanoi
$$move(n,\;'A',\;'C',\;'B')
\begin{cases}
move(n-1,\;'A',\;'B',\;'C')\\[2ex]
Print\;"Moving\;disc\;n\;from\;A\;to\;C"\\[2ex]
move(n-1,\;'B',\;'C',\;'A')
\end{cases}$$
<!-- Tower of Hanoi: Implementation -->
<!-- Merge sort -->
# Merge sort: Pseudocode
Pseudo-code:
```
start = 0
end = A.length - 1
MergeSort(A, start, end)
  if start < end
    middle = Floor[(start + end)/2]
    MergeSort(A, start, middle)
    MergeSort(A, middle+1, end)
    Merge(A, start, middle, end)
```
# Merge step: Pseudocode
Pseudo-code (Merge):  
`Merge(A, start, middle, end)`
$$n_1=mid-start+1\\
n_2=end-mid\\Let\;left[0\cdots n_1]\;and\;right[0\cdots n_2]\;be\;new\;temp\;arrays\\
for\;i=0\;to\;n_1-1\\
\quad left[i]=A[start+i]\\
for\;j=0\;to\;n_2-1\\
\quad right[j]=A[mid+1+j]\\
i,j=0\\
for\;k=start\;to\;end\\
\quad if\;left[i]\le right[j]\\
\qquad A[k]=left[i]\\
\qquad i=i+1\\
\quad else\;A[k]=right[i]\\
\qquad j=j+1$$
# Time complexity of merge sort
Height?  
$$Level\;1:\;1\;array\\
Level\;2:\;2\;arrays\\
Level\;3:\;4\;arrays\\
\vdots\\
Level\;h:\;2^{h-1}\;arrays$$

$$2^{h-1}=n\\
h=1+log_2\,n\\
O(n\,log_2\,n)$$
