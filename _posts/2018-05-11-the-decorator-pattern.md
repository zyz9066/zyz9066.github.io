---
layout: post
title:  "The Decorator Pattern"
date:   2018-05-11
tags:  [design patterns]
---
# Creating chaos with inheritance
### Class Chaos
**Design a Coffee Shop**

|Beverages for the sale system
|House Blend|$1.99|
|Dark Roast|$2.00|
|Decaf|$2.25|
|Espresso|$4.00|

Each coffee can be served with steamed milk, mocha, soy, whip, and so on...
![]({{site.baseurl}}/images/design patterns/coffee.jpg)
![]({{site.baseurl}}/images/design patterns/coffee chaos.jpg)
### Re-Design
This time let's try using object properties to keep track of the beverage options
![]({{site.baseurl}}/images/design patterns/beverage.jpg)
{% highlight java %}
HouseBlend drink = new HouseBlend();
drink.setSoy();
drink.setWhip();
float cost = drink.cost();
{% endhighlight %}
{% highlight java %}
if (hasMilk()) {
    cost += .10;
}
if (hasSoy()) {
    cost += .20;
}
if (hasWhip()) {
    cost += .10;
}
if (hasMocha()) {
    cost += .15;
}
{% endhighlight %}
### Analyzing the Second Design
**Looks simpler, until we consider:**
* Price changes will alter potentiall all existing code
* New condiments require changing the superclass
* Condiments are not appropriate for some beverages
* Cannot handle all orders (like a double mocha)

**Not the most flexible, maintainable design.**
# Understanding the open-closed principle
**Being Open and Closed**
## Design Principle #5
Classes shoulld be open for extension but closed for modification.

### The Open-Closed Principle Explained
* We want classes to be open to extensions of behavior...
* But we also want classes closed to modification.
* Our goal is to be able to easily augment what we have...
* But without modifying existing code.
* *This is one of the most important design principles.*

### Inheritance
* We know inheritance is powerful...
* But can lead to inflexible designs.
* When we subclass:
* We make static, compile time decisions
* All classes inherit the same behavior

### Composition
* We can still "inherit" behavior
* We can make dynamic runtime decisions
* We can add new behavior without altering existing code...
* Including behaviors not even considered by creator
* Fewer bugs and unintended side effects
* Overall we get more flexible designs.

# Extending behavior with composition
### Decorating with Composition
**Re-Design the Coffee Shop**
![]({{site.baseurl}}/images/design patterns/coffee.jpg)
![]({{site.baseurl}}/images/design patterns/recoffee.jpg)
# Understanding the decorator pattern
**The Decorator Pattern** attaches additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.
### Thinking About the Pattern
**Like most pattern definitions:**
* Describes the role of the pattern,
* But does not tell us how to implement it.

**Decorator Class Diagram**
![]({{site.baseurl}}/images/design patterns/decorator.jpg)
**Coffee Class Diagram**
![]({{site.baseurl}}/images/design patterns/coffeedecorator.jpg)
<!-- Implementing the decorator pattern -->
# Understanding decorators in Java libraries
### Real World Decorators: Java I/O
**`java.io.*`**
![]({{site.baseurl}}/images/design patterns/javaio.jpg)
**`java.io.*` Class Diagram**
![]({{site.baseurl}}/images/design patterns/javaiodiagram.jpg)
<!-- Using java.io decorators -->