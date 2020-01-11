---
layout: post
title:  "Java Basics"
date:   2018-06-22
tags:  [java]
---
# Create code
Anything in real life can be represented in code.
## A Car represented in Code
Attributes: Describing the car class
* License plate number
* Average miles per gallon
* Paint color

Methods: Interacting with the car class
* Check the tail lights
* Change the paint job

With this class, we don't have a car yet, but we know how to make one.  
**Two Independent Car**

|Car A|Car B|
|:-:|:-:|
|License plate: "1BC32E"|License plate: "3D2OBN"|
|Average MPG: 25.5|Average MPG: 13.9|
|Paint color: Blue|Paint color: Black|

Car A and Car B are instances of the 'car' class.
# Strings
* A string is a list of characters
* Strings are immutable
* A single character is called a char

# Array
A container that stores a sequence of values of same type

# Call by value vs. reference

|Argument|Parameter|
|Actual value passed to the function|A variable in a method definition|

When a method is called, the parameters get the value of the arguments that were passed to the function.
## Pass Arguments into a Function
Call by Value  
Call by reference
* A functions receives a reference to each argument, and can modify them

Java uses call by value, so the original arguments of a function are never modified.
# Object-Oriented Programming
* Style of programming where you organize your program around objects rather than actions, and data rather than logic
* Car class with attributes: license plate, average MPG, color
* Car class with methods: changePaintColor(), crash()

## Pillars of Object-Oriented Code
* Encapsulation
* Inheritance
* Polymorphism
* Abstraction (through interfaces)

# Encapsulation
* Encapsulation is the process of wrapping data and methods into single unit (class)
* A way to make programs more secure
* Prevents unauthorized members from accessing certain varibles and methods

* Encapsulation in Java can be known as data hiding
* You can't directly access the private preperties of a class unless you are writing code inside the class itself
* It helps developers better group and organize data
* Developers can easily change code without affecting other parts of the program

# Inheritance
* Inheritance is when one class acquires the methods and fields of another
* The class which inherits the properties of the other is known as a subclass (or derived class, parent class)
* Every object in Java inherits from the Object class implicitly

## Implementing Inheritance
* Keyword extends
* Uses of a class extend to inherit the properties of another class

## Advatages and Disadvantages
Advantages
* Minimize duplication of code
Disadvantages
* Superclass and subclass can be tightly coupled
* Increased effort to jump through levels of abstraction to get appropriate functionality

# Interfaces
* Interfaces are a way to enforce certain fields or methods on a class
* Interfaces do not enforce exactly how these methods should be implemented -- just that you must have them

* Interfaces are the definition of a behavior
* When used, they force classes and objects ot have certain properties without forcing their implementation

## Interfaces in Action
class Dog implements Pet
* play() {...}

class Cat implements Pet
* play() {...}

interface Pet
* play()

# Functional Programming
Another style of programming
* Functional programming focuses on computing results from fucntions rather than performing actions on objects
* Objects are immutable
* Instead of modifying or changing an object, you create a new object which looks like the old object, except for the change

# Learning lambda
We always had to put the definition of a function inside a class.
* Lambda functions are anonymous functions that you can create in Java without the usual code overhead
* A great tool if you need a quick function for a calculation in your code
* They usually have a single purpose and do not affect other objects in the code