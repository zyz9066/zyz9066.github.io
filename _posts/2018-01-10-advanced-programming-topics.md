---
layout: post
title:  "Advanced Programming Topics"
date:   2018-01-10
tags:  [programming fundamentals]
---
# Memory management across languages
* allocate memory
* create object
* use object
* free memory

memory leak
* allocate memory
* create object
* use object

dangling pointer

$$\begin{array}{r|l}
JavaScript, ActionScript & Automatic\\
Ruby, Python & \\
Java, C\#, VB.NET & Garbage Collection\\
Objective-C & \\
 & Reference Counting\\
C++ & \\
\\
C& \\
 & Manual\\
Assembly\;Language & \\
\end{array}$$

**CPU** Machine Code
# Introduction to algorithms
### Sorting
Bubble sort

|61|13|72|47|14|

|13|61|72|47|14|

|13|61|47|72|14|

|13|61|47|14|72|

|13|47|61|14|72|

|13|47|14|61|72|

|13|14|47|61|72|

~~~~~~~
with list of items
    repeat
        swapped = false
        for i =0 to (list.length - 1)
            if list[i] > list[i+1] then
                swap( list[i], list[i+1] )
                swapped = true
            end if
        end for
until not swapped
~~~~~~~
### Sorting Algorithms
* Bubble sort
* Heapsort
* Quicksort
* Insertion sort
* Selection sort
* Merge sort
* Pancake sort
* Permutation sort
* Cocktail sort
* Comb sort
* Counting sort
* Gnome sort
* Bead sort
* Radix sort
* Shell sort
* Sleep sort
* Strand sort
* ...

# Introduction to multithreading
### Multithreading
main thread, custom thread
### Multithreading Challenges
* competition for resources
* restrictions on updating UI
* language support