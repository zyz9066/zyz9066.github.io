---
layout: post
title:  "Basic Sorting and Searching Algorithms"
date:   2018-06-05
tags:  [algorithm]
---
# Selection sort
## Coverage
Selection Sort  
Insertion Sort

# Selection sort: Pseudocode
```
for i=0 to A.length-2
  minIndex = i
  for j=i+1 to A.length-1
    if (data[j] < data[minIndex])
      minIndex = j
  tmp = data[minIndex]
  data[minIndex] = data[i]
  data[i] = tmp
```
<!-- Introduction to insertion sort -->
<!-- Applying insertion sort algorithm to cue balls -->
# Insertion sort: Pseudocode
```
for i=0 to A.length-1
  current = A[i]
  j = i - 1
  while j>=0 && A[j]>current
    A[j+1]=A[j]
    j=j-1
  A[j+1]=current
```
# $$O(n^2)$$ sorting algorithms: Comparison
## Comparison

|Insertion Sort|Bubble Sort|Selection Sort|
|:-:|:-:|:-:|
|Relatively good for small lists<br>Relatively good for partially sorted lists|<big>Very inefficient</big>|Better than bubble sort<br>Running time is independent of ordering of elements|

# Stable Vs Unstable Sorts
Unsorted Array: 3, 5, 2, 1, 5', 10  
Stable Sort: 1, 2, 3, 5, 5', 10  
Unstable Sort: 1, 2, 3, 5', 5, 10
```java
public class InsertionSorter {
  public static void main(String[] args) {
    int[] data = {7,3,6,8,2};
    new InsertionSorter().sort(data);
    System.out.println(Arrays.toString(data));
  }

  public void sort(int[] data) {
    for (int i=0; i< data.length; i++) {
      int current = data[i];
      int j = i-1;
      while (j >=0 && data[j] > current) { \\ Stable Sorts
        data[j+1] = data[j];
        j--;
      }
      data[j+1] = current;
    }
  }
}
```
```java
public void sort(int[] data) {
  for (int i=0; i< data.length; i++) {
    int current = data[i];
    int j = i-1;
    while (j >=0 && data[j] >= current) { \\ Unstable Sorts
      data[j+1] = data[j];
      j--;
    }
    data[j+1] = current;
  }
}
```
Unsorted Array

Name|Age
:-:|:-:
John Doe|25
Nancy Cooper|24
Amit Kumar|21
Nancy Cooper|28

Sorted By Age

Name|Age
:-:|:-:
Amit Kumar|21
Nancy Cooper|24
John Doe|25
Nancy Cooper|28

Sorted By Name

Stable Sort

Name|Age
:-:|:-:
Amit Kumar|21
John Doe|25
Nancy Cooper|24
Nancy Cooper|28

Unstable Sort

Name|Age
:-:|:-:
Amit Kumar|21
John Doe|25
Nancy Cooper|28
Nancy Cooper|24

# Searching elements in an unordered array
## Arrays
7, 2, 5, 8, 1, 10  
$$\begin{align}
a[2]=5&: O(1)\\
find(8)&: O(n)\\
delete(item)&: O(n)
\end{align}$$
# Searching elements in an ordered array
## Ordered Arrays
3, 7, 20, 32, 45 ,55, 60, 75  
find(60)  
Finding Index  
$$|\frac{7+0}{2}|=3\Rightarrow a[3]=32$$  
$$|\frac{7+3}{2}|=5\Rightarrow a[5]=55$$  
$$|\frac{7+5}{2}|=6\Rightarrow a[6]=60$$ Found

$$\begin{align}
First\;Search&:\;n\\
Second\;Search&:\;\frac{n}{2}\\
Third\;Search&:\;\frac{n}{4}\\
\vdots\\
(i-1)^{th}\;Search&:\;2\\
i^{th}\;Search&:\;1=\frac{n}{2^{i-1}}
\end{align}$$  
$$2^{i-1}=n\Rightarrow(i-1)=log_2\,n$$
find(item)=$$O(log_2\,n)$$

|n|$$log_2\,n$$|
|:-:|:-:|
|2|1|
|1024|10|
|1048576(Million)|20|
|1099511627776(Trillion)|40|

# Inserting and deleting items in an ordered array
## Ordered Arrays
Insert(52)  
Insert(item)=$$O(n)$$  
Search(item)=$$O(log_2\,n)$$

Delete(55)  
Delete(item)=$$O(n)$$
# Sorting any type of objects
## Sorting objects
Circle.java
```java
public class Circle {

  private double radius;

  public Circle(double radius) {
    this.radius = radius;
  }

  public double area() {
    return Math.PI * this.radius * this.radius;
  }

  public double perimeter() {
    return 2 * Math.PI * this.radius;
  }

  public double getRadius() {
    return this.radius;
  }

  public String toString() {
    return String.valueof(this.radius);
  }
}
```
InsertionSorter.java
```java
public void sort(Circle[] circles) {
  for (int i =0; i < circles.length; i++) {
    Circle current = circles[i];
    int j = i-1;

    while (j >=0 && circles[j].getRadius() > current.getRadius()) {
      circles[j+1] = circles[j];
      j--;
    }

    circles[j+1] = current;
  }
}
```
