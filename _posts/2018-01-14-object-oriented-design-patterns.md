---
layout: post
title:  "Object Oriented Design Patterns"
date:   2018-01-14
tags:  [object oriented design]
---
# Introduction to design patterns
"Gang of Four" / "GoF" book

### Creational Patterns
* Abstract Factory
* Builder
* Factory Method
* Prototype
* Singleton

### Structural Patterns
* Adapter
* Bridge
* Composite
* Decorator
* Facade
* Flyweight
* Proxy

### Behavioral Patterns
* Chain of responsibility
* Command
* Interpreter
* Iterator
* Mediator
* Memento
* Observer
* State
* Strategy
* Template method
* Visitor

# Example: the singleton pattern
### Singleton
* We want to ensure a class only has one instance
* We want one way of accessing it

### Implementing a Singleton in Java
{% highlight java %}
public class MySingleton {
    // placeholder for current singleton object
    private static MySingleton __me = null;
    //private constructor - now no other object can instantiate
    private MySingleton() { }
    // this is now you ask for the singleton
    public static MySingleton getInstance() {
        // do I exist?
        if ( __me == null ) {
            // if not, instantiate and store
            __me = new MySingleton();
        }
        return __me;
    }
    
    // addtional functionality
    public someMethod() { //... }
}
{% endhighlight %}
### Using a Singleton in Java
{% highlight java %}
// ask for the singleton
MySingleton single = MySingleton.getInstance();

// use it
single.someMethod();

// or even just call directly
MySingleton.getInstance().someMethod();
{% endhighlight %}
# Example: the memento pattern
### Memento Design Pattern
* Handles "undo" in an object
* Does not violate encapsulation

create

|Originator|
|-
|Original state<br>*<u>memento</u>*|

|Caretaker|
|-
||

pass

|Originator|
|-
|Original state|

|Caretaker|
|-
|*<u>memento</u>*|

change

|Originator|
|-
|changed state|

|Caretaker|
|-
|*<u>memento</u>*|

change

|Originator|
|-
|changed again|

|Caretaker|
|-
|*<u>memento</u>*|

restore

|Originator|
|-
|changed again<br>*<u>memento</u>*|

|Caretaker|
|-
||