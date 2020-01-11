---
layout: post
title:  "Factories"
date:   2018-05-13
tags:  [design patterns]
---
# Encapsulating object creation
### Programming to an Implementation

`Duck duck = new MallardDuck();`
### Coping Strategies
{% highlight java %}
Duck duck
if (picnic) {
    duck = new MallardDuck();
} else if (hunting) {
    duck = new DecoyDuck();
} else if (inBathTub) {
    duck = new RubberDuck();
}
{% endhighlight %}
Separate what varies and encapsulate it.
### Example
{% highlight java %}
Pizza orderPizza(String type) {
    Pizza pizza;
    if (type.equals("cheese")) {
        pizza = new CheesePizza();
    } else if (type.equals("greek")) {
        pizza = new GreekPizza();
    } else if (type.equals("pepperoni")) {
        pizza = new PepperoniPizza();
    }
    pizza.prepare();
    pizza.cook();
}
{% endhighlight %}
### Introducing change
{% highlight java %}
Pizza orderPizza(String type) {
    Pizza pizza;
    if (type.equals("cheese")) {
        pizza = new CheesePizza();
    } else if (type.equals("veggie")) {
        pizza = new VeggiePizza();
    } else if (type.equals("pepperoni")) {
        pizza = new PepperoniPizza();
    }
    pizza.prepare();
    pizza.cook();
}
{% endhighlight %}
# Understanding the Simple Factory idiom
**Encapsulating What Varies**
### Simple Factory
{% highlight java %}
public class SimplePizzaFactory {
    public Pizza createPizza(String type) {
        Pizza pizza = null;
        if (type.equals("cheese")) {
            pizza = new CheesePizza();
        } else if (type.equals("greek")) {
            pizza = new GreekPizza();
        } else if (type.equals("pepperoni")) {
            pizza = new PepperoniPizza();
        }
        return pizza;
    }
}
{% endhighlight %}
### Using the Factory
{% highlight java %}
Pizza orderPizza(String type) {
    Pizza pizza = factory.createPizza(type);
    pizza.prepare();
    pizza.cook();
}
{% endhighlight %}
![]({{site.baseurl}}/images/design patterns/factory.jpg)
![]({{site.baseurl}}/images/design patterns/factory dia.jpg)
<!-- Implementing the Simple Factory idiom -->
# Exploring the factroy method pattern
**Encapsulating What Varies**
![]({{site.baseurl}}/images/design patterns/factory.jpg)
**Two Pizza Stores, Two Different Styles of Pizza**
### What We Do Not Want...
{% highlight java %}
Public Pizza createPizza(String style, String type) {
    Pizza pizza = null;
    if (style.equals("NY")) {
        if (type.equals("cheese")) {
            pizza = new NYStyleCheesePizza();
        } else if ...
        ...
    } else if (style.equals("Chicago")) {
        if (type.equals("cheese")) {
            pizza = new ChicagoStyleCheesePizza();
        } else if ...
        ...
    }
    pizza.prepare();
    pizza.bake();
    pizza.cut();
    pizza.box();
    return pizza;
}
{% endhighlight %}

|**`orderPizza()`**<br>`prepare()`<br>`bake()`<br>`cut()`<br>`box()`|<-- same algorithm -->|**`orderPizza()`**<br>`prepare()`<br>`bake()`<br>`cut()`<br>`box()`|
|**`createPizza()`**<br>NY style veggie<br>NY style clam<br>NY style cheese|<-- different types -->|**`createPizza()`**<br>Chicago style veggie<br>Chicago style clam<br>Chicago style cheese|

**The Factory Method Pattern** defines an interface for creating an object, but lets subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.
![]({{site.baseurl}}/images/design patterns/factory method.jpg)
### Creating a Pizza with Factory Method
* **Instantiate a pizza store**\\
`PizzaStore store = new NYPizzaStore();`
* **Order a pizza**\\
`store.orderPizza("cheese");`
* **In the store, create a pizza**\\
`Pizza pizza = createPizza("cheese");`
* **In the store, prepare the pizza**\\
`pizza.prepare()`, `pizza.bake()`, `pizza.cut()`, `pizza.box()`

<!-- Implementing the factory method pattern -->
## Conclusion
### The Design Patterns
* Strategy Pattern
* Observer Pattern
* Decorator Pattern
* Singleton Pattern
* State Pattern
* Iterator Pattern
* Factory Pattern

### Other Patterns
* Command Pattern
* Adapter Pattern
* Facade Pattern
* Template Method Pattern
* Composite Pattern
* Proxy Pattern
* ...and more

### Compound Patterns
**Model View Controller Pattern (MVC)**\\
Combines Strategy, Observer and Composite patterns\\
Used to separate three parts of a system:
* User interface
* Logic
* Data model

### The Principles
* Encapsulate what varies
* Favor composition over inheritance
* Program to an interface
* Strive for loosely coupled designs
* Classes should remain open to extension, and closed for modification
* A class should have only one reason to change

**A Design Pattern** is a solution to a problem in a context.
* Context: The situation in which the pattern applies.
* Problem: The goal you are trying to achieve.
* Solution: A design that recolves the problem.

### Thiking in Patterns
* Do not make patterns a hammer looking for nails
* Everything is a tradeoff
* Keep designs simple (KISS)
* But, when you see a need , do not reinvent, use patterns
* Do not stop learning patterns