---
layout: post
title:  "The State Pattern"
date:   2018-05-11
tags:  [design patterns]
---
# What is a state machine?
### Managing State
**A Simple State Machine**
![]({{site.baseurl}}/images/design patterns/state.jpg)

{% highlight java %}
final static int SOLD_OUT = 0;
final static int NO_QUARTER = 1;
final static int QUARTER = 2;
final static int SOLD = 3;
int state = NO_QUARTER;
{% endhighlight %}
{% highlight java %}
public void insertQuarter() {
    if (state == QUARTER) {
        System.out.println("ERROR, already a quarter");
    } else if (state == SOLD_OUT) {
        System.out.println("ERROR, machine sold out");
    } else if (state == SOLD) {
        System.out.println("Already getting you a gumball");
    } else if (state == NO_QUARTER) {
        state = HAS_QUARTER;
    }
}
{% endhighlight %}
{% highlight java %}
public void turnCrank() {
    if (state == QUARTER) {
        state = SOLD;
        dispense();
    } else if (state == SOLD_OUT) {
        System.out.println("ERROR, machine sold out");
    } else if (state == SOLD) {
        System.out.println("You can't turn crank twice");
    } else if (state == NO_QUARTER) {
        System.out.println("Insert a quarter first");
    }
}
{% endhighlight %}
### Need One Method Per Transition
{% highlight java %}
pulic void turnCrank();
pulic void insertQuarter();
pulic void ejectQuarter();
pulic void dispense();
pulic void refill();
{% endhighlight %}
### Need Another State
![]({{site.baseurl}}/images/design patterns/add state.jpg)
**Add the New State**\\
So we have to add a new state to every method, and we have to write two new transition methods.\\
**We Need One Test Per State**
# Revisiting the design for a state machine
### Review of State Design
* Is not really OO at all
* Any additions require many changes to code
* Difficult to understand all the states and transitions
* Violates open-closed principle

### Think of Each State as an Object

|**`State`**|
|`insertQuarter()`<br>`ejectQuarter()`<br>`turnCrank()`<br>`dispense()`|

![]({{site.baseurl}}/images/design patterns/stateobj.jpg)
# Understanding the state pattern
### The State Pattern
{% highlight java %}
public class GumballMachine {
    final static int SOLD_OUT = 0;
    final static int NO_QUARTER = 1;
    final static int QUARTER = 2;
    final static int SOLD = 3;
    int state = NO_QUARTER;
    ...
}
{% endhighlight %}
![]({{site.baseurl}}/images/design patterns/stateobj.jpg)
{% highlight java %}
public class GumballMachine {
    ...
    State state = noQuarterState;
    public void insertQuarter() {
        state.insertQuarter();
    }
    ...
}
{% endhighlight %}
![]({{site.baseurl}}/images/design patterns/context state.jpg)
**The State Pattern** allows an object to alter its behavior when its internal state changes. The object will appear to change its class.
### Key Points
* **The pattern encapsulates state into separate classes.**
* **The context delegates to the current state to handle requests.**
* **Once a request is handled, the current state may change.**\\
Each state has different behavior.

* Encapsulate what varies.
* Favor composition over inheritance.
* Keep a class closed for modification but open for extension.
<!-- Implementing the state pattern -->
# Comparing the state and strategy patterns
![]({{site.baseurl}}/images/design patterns/context state.jpg)
![]({{site.baseurl}}/images/design patterns/strategy pattern.jpg)