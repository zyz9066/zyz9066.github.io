---
layout: post
title:  "Control Flow"
date:   2018-06-23
tags:  [java]
---
# Mapping out program control flow
Programs can have different outcomes based on conditions.
## Conditions
* Greater than **>** and greater than or equal to **>=**
* Less than **<** and less than or equal to **<=**
* Equal to **==**
* Not equal to **!=**
* Boolean expression: 5 > 10 (eval to false); 5 < 10 (true);

## Comparison Operator < with a Var
* x = 4
* x < 10 -> a boolean expression
* x evaluates to 4
* 4 < 10 -> a boolean expression
* 4 < 10 evaluates to true

Apply conditional operators to boolean expressions to create more comprehensive boolean expressions.
## Applying Conditional Operations
* AND: the two operands or inputs must evaluate to true for the expression to evaluate to true; otherwise false
* OR: at least one input of the two inputs must evaluate to true for the expression to evaluate to true; otherwise, false
* NOT: taks only one input, and if that input evaluates to false, it returns true; if it evaluates to true, it returns false

## Conditional Operations in Action
* int size
* boolean isBelowLimit = size>=2
* boolean isAboveLimit = size<=12
* Only want to return true if they are both true
* (isBelowLimit&&IsAboveLimit) -> a boolean expression

* int size=5
* boolean isBelowLimit = size>=2 -> evaluates to true
* boolean isAboveLimit = size<=12 -> evaluates to true
* (isBelowLimit&&IsAboveLimit) -> evaluates to true

* int size=2
* boolean isBelowLimit = size>=2 -> evaluates to true
* boolean isAboveLimit = size<=12 -> evaluates to true
* (isBelowLimit&&IsAboveLimit) -> evaluates to true

* int size=1
* boolean isBelowLimit = size>=2 -> evaluates to false
* boolean isAboveLimit = size<=12 -> evaluates to true
* (isBelowLimit&&IsAboveLimit) -> evaluates to false

# Decision-making with IF
Map out a Program Using a UML
* Unified Modeling Language (UML) helps developers visualize the flow of a program

# Loops
A loop is a control flow statement that allows code to be excuted repeatedly based on a boolean condition.

# Libraries
Libraries provide you with extra classes and methods.
## Java Libraries
Java.lang
*Fundamental to the core Java language (math, boolean, byte)

Java.util
* Generic utilites (scanning, formating strings, data manipulation)

Java.net
* Infrastructure for networking