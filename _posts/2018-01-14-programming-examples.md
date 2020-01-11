---
layout: post
title:  "Programming Examples"
date:   2018-01-14
tags:  [programming examples]
---
# Functions
### Benefits of Functions
* Shorter programs -- code can be used over and over
* More robust -- less room to make mistakes

Functions are useful when a program needs to repeat a coded process.
### Code Reuse
Using the same code elements more than once.  
Functions may or may not return a value, depending on their purpose.
### No return value?
Functions executes and returns automatically without passing back any output values.
### Why create a function with the common steps?
Functionalizing Code
* Reuse code for similar tasks
* Change code in one place

### Parameter
Variable name used inside of the function to access input passed to the function
### Parameter vs. Argument
An argument is the value passed to the function.  
A parameter is the variable name used to reference the arguments passed to the function.  
Parameter ~ Arguments  
Parameter != Arguments
### Input Parameters
* Must be uniquely named
* Must pass exact number defined

**Variable Input**  
Allows user to pass any number of arguments to a function  
Asterisk tells Python to expect any number of arguments when the function is called.
### List and Tuple
* Like a list made of Arguments
* Interactions  
Access individual arguments  
Iterate over arguments

### Local Variable in Functions
* Parameters
* Variables created in functions

### Global Variable
Variable created in the main body of the program, outside of any functions  
Functions search for variables locally first. If the variable is not in the local scope, it expands the search to the global scope.  
New, local variable, inside the function  
Syntax is Python specific, to prevent accidental changes to global variables.  
Other languages use unique syntax to differentiate local and global variables.
# Objects
### Attributes
**Method**  
Actions that an object can perform
### Programming Objects
* They are often more complex than simple nouns.
* Many languages have abstract object types.

In Python, everything is an object, with a unique ID and attributes.  
Functions and methods are often referred to as verbs, or actions a program can take.
### OOP
* Object-Oriented Programming
* Ex. Java, Python, C++, VB.NET, and Ruby

Take action on an object without worrying about type
### Common Actions to Take on Objects
* Compare two
* Pass as arguments
* Store in lists or dictionaries

### Class
Defines the attributes and methods of an object  
**`_init_method`**  
Python constructor method for creating new objects; custom_init_ can define unique parameters for a new object.  
When a method is called on an object, Python automatically passes that object as the first argument.  
Self provides a convenient way to access and modify an object within a method.
### Programming with objects
* Attibutes and methods are implemented automatically
* The user only needs to know methods exist to use them.
* You can focus on completing tasks rather than operation details.

Object-oriented programming makes it easy to reuse and maintain code.
### Mutable vs. Immutable
* A mutable object can be modified after creation.
* Immutable objects are stuck in their creation state.

In Python, the plus operator creates a new string containing the concatenated phrase, and binds the new object to the name words.
# Class Inheritance
### Class: Vehicle
Attributes
* Color
* Manufacturer
* Gas level

Method: Drive

|Parent Class:<br><big>Vehicle</big>|
|:-:|
|Methods:<br>\__init__<br>string<br>~~drive~~|

|SubClass:<br><big>Car</big>|
|:-:|
|Methods:<br>window<br>radio|

|SubClass:<br><big>eCar</big>|
|:-:|
|Methods:<br>drive|

### Inherited Attributes and methods
* Keep large programs simple
* Easy-to-maintain code

# Modules and Packages
[Python documentation](http://docs.python.org/3)  
When using more than one or two tools in a module, import the entire module
### From Statements
* Helpful when using one or two tools in a module
* Easy to create name conflicts

Simple Program ---> Complex Program

[Python Module Index](http://docs.python.org/3/py-modindex.html)  
# Lists and Tuples
Floor, Row, Spot  
**GPS Coordinate**  
Longitude: W122$$^\circ$$24'28.7"  
Latitude: N37$$^\circ$$47'15.3"  
Tuples are immutable. They are forever frozen in their creation state.  
Tuples in the Wild: coordinate
# Queues and Stacks
FIFO: first in, first out  
LIFO: last in, first out  
### Blocking Method
The program will wait until method completes before continuing execution.  
Blocking works well when multiple threads or processes use queues to share information.  
`get(false)`  
Keep blocking in mind, to avoid locking up a program
### Why use a list as a stack, and not a queue?  
Modules are designed with specific tasks in mind. Using the queue module is slightly more efficient, because it is designed specifically for that purpose.
### lists
* Easily add and remove items from end
* Last in, first out

# Sets
Merge sets with the `.union()` operator
* Store groups of like objects
* Each item unique
* No order

`.intersection()` returns common elements.  
`.difference()` removes common items.  
`.symmetric_difference()`
# Dictionaries
Key - Value  
Index - Value  
Dictionary values can store more than just strings.
# Conditional Execution
Priority  
The most restrictive options should go near the top.
```java
switch(today){
  case "Sunday":
    order = "Spinach";
    break;
  case "Monday":
    order = "Mushroom";
    break;
  ...
  default:
    order = "No Special";
}
```
Dictionary hashing can be quicker than a long if/elif chain.
# Loops
Problems often occur when adding or removing items from a list with a for loop.
### For vs. while
* while  
Runs until is full
* for  
Runs times, or until is full

The break statement ends the for loop once the is full.
# Error Handling
### Try Statement
Contains a block of code. If an error occurs during execution, the try statement catches the exception, preventing a crash.
### Error Checking
* Set conditions
* Validate data against conditions

### Implement Error Checking
* Input from a user or external method
* Methods with logic that relies on conditions being true

### Errors
* Errors built into language.
* Modules and packages often include related errors.
* Programmer can create custom errors with new class definitions.

### Error Handling
* Important for creating robust
* Often overlooked
* Can be trickier than syntax issues

Error handling allows code to execute properly when unexpected events occur.
### Sticky Situations
* Missing an error
* Finding an error, without knowing the cause

# Polling and Event-Driven Programming
### tkinter
* Python module for creating graphical user interfaces
* Easy way to demo event-driven programming

### Event Handlers
Code that is executed when an event occurs
### Waiting State
Event-driven programming handles one event at a time, in the order the events occur.  
Event handlers should execute as quickly as possible.
