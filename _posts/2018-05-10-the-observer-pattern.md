---
layout: post
title:  "The Observer Pattern"
date:   2018-05-10
tags:  [design patterns]
---
# Using the observer pattern in the real world

### Example
* **A publisher creates a new magazine and begins publishing issues**
You subscribe and receive issues as long as you stay subscribed\\
You can unsubscribe at any time\\
Others can also subscribe\\
If publisher ceases business, you stop receiving issues

### Publishers and Subscribers
![]({{site.baseurl}}/images/design patterns/pub sub.jpg)
# Exploring the observer pattern
### The Observer Pattern
**The Observer Pattern** defines a one-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.\\
Defines a one-to-many relationship
![]({{site.baseurl}}/images/design patterns/sub dep.jpg)
![]({{site.baseurl}}/images/design patterns/sub ob.jpg)
# Understanding the observer pattern
![]({{site.baseurl}}/images/design patterns/weather.jpg)
![]({{site.baseurl}}/images/design patterns/weatherdata.jpg)
<!-- Implementing the observer pattern -->
# Using Java's Observer and Observable classes
### Java's Built-in Observer Pattern
* **Observable class**\\
The subject extends the built-in Observable class\\
Two step process to notify observers
* **Observer interface**\\
Observers implement the Observer interface\\
Observers can pull data from the Subject or the Subject can push data to the Observers
![]({{site.baseurl}}/images/design patterns/observerable.jpg)

### Two Steps to Notify Observers
* **Call `setChanged()` method**\\
Signifies the state has changed in the Subject
* **Call `notifyObservers()`**\\
For pull: `notifyObservers()`\\
For push: `notifyObservers(Object arg)`

### To Receive Notifications
**Observers**\\
`update(Observerable o, Object arg)`

`Subject: notifyObservers(Object arg)`
<!-- Implementing the observer pattern with Java's Observer and Observable classes -->
# The advantages of loose coupling
### Being Loosely Coupled
* **Subjects and observers are "loosely coupled"**\\
They interact,\\
but have little knowledge of each other
* **Subject only knows**\\
The observer implements a specific interface\\
Does not need to know concrete class or anything else

### The Observer
**Subject relies on a *list* of observers**\\
**Observers can be:**
* Added at any time
* Removed at any time
* Or even replaced

**Subject does not care, it keeps doing its job**

**If we want to add new type of observers, modification of the subject is never needed**\\
Observers just need to implement the Observer interface\\
**In fact, no changes to the subject or observers will affect the other**\\
**>That's loose coupling**

>Because object interdependencies are minimized, loose coupling allows us to build more flexible OO architectures

## Design Principle #4
Strive for loosely coupled designs between objects that interact.