---
layout: post
title:  "Working with Lists"
date:   2018-04-28
tags:  [data structure]
---
# Understanding basic list implementations
### Arrays support direct access

|1|11|11|11|11|12|12|14|14|14|18|20|21|21|22|29|29|37|46|46|56|56|65|65|
|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|

**AKA "Random Access"**
### Lists support sequential access
![]({{site.baseurl}}/images/data structure/lists.jpg)
### Adding / removing arrray elements

|0|123|
|1|9742|
|2|789|
|3|234|
|4|456|
|5|5678|
|6|21|
|7|42|
|8|123|

`myArray.add(999,2);`

|0|123|
|1|9742|
|2|999|
|3|789|
|4|234|
|5|456|
|6|5678|
|7|21|
|8|42|
|9|123|

### Adding / removing list elements
Adding list elements
![]({{site.baseurl}}/images/data structure/add element.jpg)
Removing list elements
![]({{site.baseurl}}/images/data structure/remove element.jpg)

||Arrays|Linked Lists|
|Direct Access|**GOOD**<br>fixed time O(1)|**POOR**<br>linear time O(n)|
|Adding / Removing|**POOR**<br>linear time O(n)|**GOOD**<br>fixed time O(1)|
|Searching|O(n) linear search<br>O(log n) binary search|O(n) linear search|

# Using singly and doubly linked lists
### Singly Linked list
![]({{site.baseurl}}/images/data structure/lists.jpg)
### doubly Linked list
![]({{site.baseurl}}/images/data structure/doubly list.jpg)
**circular doubly linked list**
![]({{site.baseurl}}/images/data structure/circular list.jpg)

# List support across languages
### Linked list language support
Java - `java.util`: [Interface `List<E>`](https://docs.oracle.com/javase/7/docs/api/java/util/List.html "List"), [Class `ArrayList<E>`](https://docs.oracle.com/javase/7/docs/api/java/util/ArrayList.html "ArrayList"), [Class `LinkedList<E>`](https://docs.oracle.com/javase/7/docs/api/java/util/LinkedList.html "LinkedList")

>Operations that index into the list will traverse the list from the beginning or the end, whichever is closer to the specified index.
<cite>`LinkedList` in `java.util`</cite>

|Java| `LinkedList` in `java.util` |
|C#| `LinkedList` in `System.Collections.Generic` |
|Objective-C| n/a |
|Ruby| n/a |
|Python| n/a - "lists" are dynamic arrays, not linked lists|
|C++| `std::list` |

[**How are lists implemented in Python?**](https://docs.python.org/3/faq/design.html#how-are-lists-implemented "How are lists implemented?")

Python’s lists are really variable-length arrays, not Lisp-style linked lists. The implementation uses a contiguous array of references to other objects, and keeps a pointer to this array and the array’s length in a list head structure.

This makes indexing a list `a[i]` an operation whose cost is independent of the size of the list or the value of the index.

When items are appended or inserted, the array of references is resized. Some cleverness is applied to improve the performance of appending items repeatedly; when the array must be grown, some extra space is allocated so the next few times don’t require an actual resize.
