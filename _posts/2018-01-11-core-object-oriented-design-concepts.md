---
layout: post
title:  "Core Object Oriented Design Concepts"
date:   2018-01-11
tags:  [object oriented design]
---
# Introduction
* Abstraction
* Polymorphism
* Inheritance
* Encapsulation
* Composition
* Association
* Aggregation
* Constructors
* Destructors
* Cardinality
* Singleton
* Class-Responsibility-Collaboration
* Chain-of-Responsibility

building better apps
* clarity
* agility
* accuracy
* maintainability

$$\begin{array}{rl}
 & \textbf{Analysis}\; \small{understand}\\
Object-Oriented & \textbf{Design}\; \small{plan}\\
 & \textbf{Programming}\; \small{build}
\end{array}$$

Software Development Methodologies
* Scrum
* Extreme Programming (XP)
* SSADM
* Unified Process
* Agile Unified Process
* Feature-Driven Development (FDD)
* Cleanroom
* Adaptive Software Development
* Crystal Clear
* Behavior-Driven Development
* Rapid Application Development

waterfall approach, agile / iterative approach
# Why use object-orientation
data, logic
* Logic programming language: Prolog
* Functional programming language: Haskell

### Object Oriented Programming Languages
C++, C#, Java, JavaScript, Perl, PHP, Python, Objective-C, Ruby, VB.NET and many others
# What is an object?
### Computing Objects
Bank Account Object

|`balance`: $500<br>`number`: A7652<br><br>`deposit()`<br>`withdraw()`|

Person Object

|`name`: "Bob"<br>`gender`: male<br><br>`walk()`<br>`run()`|

Person Object

|`name`: "Alice"<br>`gender`: female<br><br>`walk()`<br>`run()`|

* Objects are not always *physical* items
* Objects are not always *visible* items

# What is a class?
* class: the blueprint, object: the house
* one class, multiple objects

### Creating a Class
* type\\
**name**: what is it?\\
Employee, BankAccount, Event, Player, Document, Album
* properties, data\\
**attribute**: what describes it?\\
Width, Height, Color, Score, FileType, Length
* operations\\
**behavior**: what can it do?\\
Play, Open, Search, Save, Print, Create, Delete, Close

### Creating a Bank Account Class
* **name**: BankAccount
* **attribute**: accountNumber, balance, dateOpened, accountType
* **behavior**: open(), close(), deposit(), withdraw()

### Class / Objects
class

|BankAccount|
|-
|`accountNumber`<br>`balance`<br>`dateOpened`<br>`accountType`|
|`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

object (instance)

|A7652<br>$500<br>5/3/2000<br>Checkings<br><br>`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

joeAcct

|B2311<br>-$50<br>1/2/2012<br>Checkings<br><br>`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

aliceAcct

|S2314<br>$7500<br>1/2/1994<br>savings<br><br>`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

samAcct

creating objects = instantiation
### Existing Classes in OO languages
Most OOP languages provide many pre-written generic classes at minimum: strings, dates, collections, file I/O, networking (but often many more)
* Java Class Library
* .NET Framework BCL
* C++ Standard Library
* Ruby Standard Library
* Python Standard Library

# What is Abstraction?
* **A**bstraction
* **P**olymorphism
* **I**nheritance
* **E**ncapsulation

### Abstraction
* focus on the essentials
* ignore the irrelevant
* ignore the unimportant

|BankAccount|
|-
|`accountNumber`<br>`balance`<br>|

# What is Encapsulation?
### Class / Objects
attributes + behaviors

|BankAccount|
|-
|`accountNumber`<br>`balance`<br>`dateOpened`<br>`accountType`|
|`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

|BankAccount|
|-
|`accountNumber`<br><br>`dateOpened`<br>`accountType`|
|`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

"black boxing"

|BankAccount|
|-
|`accountNumber`<br>`balance`<br><br>|
|`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

|BankAccount|
|-
|`accountNumber`<br>`dollars`<br>`cents`<br>|
|`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

# What is Inheritance?

|Person|
|-
|`name`<br>`email`<br>`phone`|
|`changeEmail()`|

|Customer|
|-
|`name`<br>`email`<br>`phone`<br>`customerNumber`|
|`changeEmail()`|

Customer - **Subclass** (Child class) inherits from Person - **Superclass** (Parent class)

|Customer|
|-
|(has every thing from person)<br>`customerNumber`|

|Employee|
|-
|(has every thing from person)<br>`employeeGrade`<br>`join()`<br>`retire()`|

# What is Polymorphism?
"many forms"
* +: addition, concatenation

|BankAccount|
|-
|`accountNumber`<br>`balance`|
|`deposit()`<br>`withdraw()`|

|SavingsAccount|
|-
|(has every thing from BankAccount)<br>`interestRate`|

|CheckingAccount|
|-
|(has every thing from BankAccount)<br>`lastCheckNum`|

|InvestmentAccount|
|-
|(has every thing from BankAccount)<br>`accountRep`<br>`withdraw()`|

overriding