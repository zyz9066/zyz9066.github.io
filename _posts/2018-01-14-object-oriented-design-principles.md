---
layout: post
title:  "Object Oriented Design Principles"
date:   2018-01-14
tags:  [object oriented design]
---
<!-- Introduction to object-oriented design principles -->
# Exploring general development principles
### General software development principles
* DRY: Don't Repeat Yourself
* YAGNI: You Ain't Gonna Need It

### Example Code Smells
* Long Methods
* Very short (or long) identifiers
* Pointless comments

```java
// This creates a variable called i and sets it to zero
int i = 0;
```

* God object
* Feature envy

# Introduction to SOLID principles
### SOLID principles of object-oriented design
* S: Single Responsibility Principle
* O: Open / Closed Principle
* L: Liskov Subsititution Principle
* I: Interface Segregation Principle
* D: Dependency Inversion Principle

### Single Responsibility Principle
An object should have one reason to exist, one reason to change - one primary responsibilty
### Open / Closed Principle
Open for extension, but closed to modification
### Liskov Subsititution Principle
Derived classes must be substitutable for their base classes
### Interface Segregation Principle
Multiple specific interfaces are better than one general purpose interface
### Dependency Inversion Principle
Depend on abstractions (layer of abstraction), not on concretions
# Introduction to GRASP principles
General Resposibility Assignment Software Patterns
* Creator
* Controller
* Pure Fabrication
* Information Expert
* High Cohesion
* Indirection
* Low Coupling
* Polymorphism
* Protected Variations

### Expert / Information Expert
Assign the responsibility to the class that has the information needed to fulfill it
### Creator
Who is responsible for creating an object?
### Low Coupling / High Cohesion
* Coupling: the level of dependencies between objects
* Cohesion: the level that a class contains focused, related behaviors

The aim is LOW COUPLING & HIGH COHESION
### Controller
Don't connect UI element directly to business objects (problem: high coupling, low cohesion)
### Pure Fabrication
When the behavior does not belong anywhere else, create a new class
### Indirection
To reduce coupling, introduce an intermediate object
### Polymorphism
* Automatically correct behavior based on type
* As opposed to: conditional logic that checks for particular types
### Protected Variations
Protect the system from changes and variations
* Identify the most likely points of change
* Use multiple techniques: encapsulation, LSP, OCP

## Conclusion
### Reviewing feature support across different object-oriented languages

|Language|Inheritance|Typing|Call to super|Private Methods|Abstract Classes|Interfaces|
|:-|:-:|:-:|:-:|:-:|:-:|:-:|
|**Java**|Single|static|super|Yes|Yes|Yes|
|**C#**|Single|static|base|Yes|Yes|Yes|
|**VB.NET**|Single|static|MyBase|Yes|Yes|Yes|
|**Objective-C**|Single|static/dynamic|super|No|No|Protocols|
|**C++**|Multiple|static|name of class::|Yes|Yes|Abstract Class|
|**Ruby**|Mix-ins|dynamic|super|Yes|n/a|n/a|
|**JavaScript**|Prototype|dynamic|n/a|Yes|n/a|n/a|

### Additional resources
Books
* Software Requirements
* Writing Effective Use Cases
* User Stories Applied for Agile Software Development
* UML Distilled
* Head First Design Patterns
