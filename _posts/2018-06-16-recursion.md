---
layout: post
title:  "Recursion"
date:   2018-06-16
tags:  [recursion]
---
# Define recursion
## Definition
* Recursion is when a method calls itself.
* The solution uses smaller instances of the same problem.
* First, we must find the scenario that indicates we are done.
* Without the base case, we have an infinite process.
* Next, the function is defined in terms of itself.
* Note the base case may include more than one condition.
* Recursion is optional; it can be solved with iterative loops.

# Towers of Hanoi
* High priests were given three golden pegs.
* On one peg was 64 golden disks.
* The disks were all different sizes.
* They were stacked from smallest to largest.
* The task was to move all 64 to another peg.
* But there were rules.  
<small>Only move one disk at a time.  
Only the top most disk can be moved each time.  
The disk must be moved to the top of another peg.  
No disk can be placed on top of a smaller one.</small>
* When all 64 disks are moved, the world will come to an end.
* This problem illustrates recursion.

What is the smallest number of steps to move the stack?  
If $$n=3$$, it takes 7 moves or $$2^3-1$$.
# Recursive Examples
## Print List in Reverse Order
Print a list of numbers (or letters/strings) in reverse Order
1. If no items are left, print the first item
2. Print the list, except for the first item, in reverse order

Assume you have a function called reverse:  
reverse(10, 20, 30, 40, 50) $$\Rightarrow$$ reverse(20, 30, 40, 50) 10  
reverse(20, 30, 40, 50) $$\Rightarrow$$ reverse(30, 40, 50) 20 10  
reverse(30, 40, 50) $$\Rightarrow$$ reverse(40, 50) 30 20 10  
reverse(40, 50) $$\Rightarrow$$ reverse(50) 40 30 20 10  
reverse(50) $$\Rightarrow$$ 50 40 30 20 10
## Factorial
* The factorial of $$n$$, is $$n*(n-1)*(n-2)*(n-3)*\ldots *1$$
* Base case
* $$5!-5*4*3*2*1=120$$

```
factorial(5) = 120
  5 * factorial(4)              returns 5 * 24 = 120
      4 * factorial(3)          returns 4 * 6 = 24
          3 * factorial(2)      returns 3 * 2 = 6
              2 * factorial(1)  returns 2 * 1
```
## Greatest Common Divisor
* Base case is when the remainder value reaches zero.
* The recursive case constantly finds the remainder of two numbers.

# Decimal to Binary

$$26=10+6$$

|$$10^4=10,000$$|$$10^3=1,000$$|$$10^2=100$$|$$10^1=10$$|$$10^0=1$$|
|:-:|:-:|:-:|:-:|:-:|
||||2|6|

$$26=16+8+2$$

|$$2^4=16$$|$$2^3=8$$|$$2^2=4$$|$$2^1=2$$|$$2^0=1$$|
|:-:|:-:|:-:|:-:|:-:|
|1|1|0|1|0|

$$26\%2=0\Rightarrow 26/2=13\\
13\%2=1\Rightarrow 13/2=6\\
6\%2=0\Rightarrow 6/2=3\\
3\%2=1\Rightarrow 3/2=1\\
1\%2=1\Rightarrow 1/2=0$$
* **Base case: Quotient is zero.**
* **Recursive case:**  
Number / 2  
Print remainder

# Linked List
* A data structure can be implemented using a linked list.
* It easily conforms to a recursive function.  
<small>A null reference is the base case (an empty list).  
The next instance refers to any linked list that is not empty.</small>

# Power Recursion
* $$x^n$$ = $$x$$ multiplied by itself $$n-1$$ times
* $$x^4=x*x*x*x$$
* If $$n$$ is even: $$x^n=x^{n/2}*x^{n/2}$$
* $$3^4=3*3*3*3=81$$ (three multiplications)
* $$3^4=3^2*3^2=81$$ (two multiplications)
* The benefits of this approach grows exponentially better with larger numbers
* $$3^8=3^4*3^4=3^2*3^2*3^2*3^2=6,561$$ (four multiplications)
