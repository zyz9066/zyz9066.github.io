---
layout: post
title:  "The Strategy Pattern"
date:   2018-05-04
tags:  [design patterns]
---
# Understanding the pitfalls of inhertance and interfaces
### Inheritance and interfaces
**Inheritance**
* Inheritance is a core principle of OO programming
* But we tend to overuse it
* Often results in design and code that is inflexible

**A car *IS-A* feline**
![]({{site.baseurl}}/images/design patterns/cat.jpg)
**Designing classes for ducks**
![]({{site.baseurl}}/images/design patterns/ducks classes.jpg)
**Adding another duck**
![]({{site.baseurl}}/images/design patterns/add duck.jpg)
**Adding flying**
![]({{site.baseurl}}/images/design patterns/add fly.jpg)
**Adding another duck**
![]({{site.baseurl}}/images/design patterns/add duck2.jpg)
**Problems with our design**
* We have code duplicated across classes
* Hard to gain knowledge of all the ducks
* Changes can affect other ducks
* Runtime behavior changes are difficult

**What about using interfaces?**
* Allow different classes to share similarities
* Not all classes need to have the same behavior

**Implementing ducks with interfaces**
![]({{site.baseurl}}/images/design patterns/interface.jpg)
**Also problematic**
* Solves part of the problem, but...
* Absolutely destroys code reuse
* Becomes a maintenance nightmare
* Does not allow for runtime changes in behaviors other than flying or quacking

# Encapsulating code that varies
### Reviewing our attempts
* **Tried inheritance: it did not work well**\\
Behavior changed across subclasses, and not appropriate for all subclasses to have those behaviors
* **Tried interfaces: also did not work well**\\
Sounded promising, but interfaces supply no implementation and destroyed reuse entirely

## Design Principle #1
Identify the aspects of your code that vary and separate them from what stays the same.

**"Encapsulate What Varies"**
* **If some aspect of code is changing**\\
That's a sign you should pull it out and separate it
* **By separating out the parts of your code that vary**\\
You can extend or alter them without affecting the rest of your code
* *This principle is fundamental to almost every design pattern*

>All patterns let some part of the code vary independently of the other parts, fewer surprises from code changes and increased flexibility in your code

# Programming to a interface
### Identifying what changes
![]({{site.baseurl}}/images/design patterns/ducks class.jpg)
## Design Principle #2
Program to an interface, not an implemnetation.

**Programming to an interface**
![]({{site.baseurl}}/images/design patterns/to interface.jpg)
![]({{site.baseurl}}/images/design patterns/to interface2.jpg)

<!-- Setting behavior dynamically -->

# Exploring the strategy pattern
![]({{site.baseurl}}/images/design patterns/ducks class.jpg)
**Problems**
* Changing code in subclasses
* Duplicated code

### The Strategy Pattern
![]({{site.baseurl}}/images/design patterns/strategy pattern.jpg)
**The Strategy Pattern** defines a family of algorithms, encapsulates each one, and makes them interchangeable. Strategy lets the algorithm vary independently from clients that use it.
# Understanding why HAS-A is better than IS-A
### Stepping back
* **Note we're using a HAS-A relationship**\\
Each duck *has a* FLyBehavior and QuackBehavior
* **Instead of inheriting behavior, we're composing it**\\
A duck is composed with a fly and quack behavior

## Design Principle #3
Favor composition over inheritance.

A Redhead Duck IS-A Duck / A Duck HAS-A FlyBehavior