---
layout: post
title:  "The Collection Pattern"
date:   2018-05-12
tags:  [design patterns]
---
# Encapsulating iteraion
### Representing Collections

{% highlight java %}
String[] menuItems = new String[MAX_ITEMS];
menuItems[0] = "Regular Pancake Breakfast";
menuItems[1] = "Blueberry Pancakes";
{% endhighlight %}

{% highlight java %}
ArrayList<String> menuItems = new ArrayList<String>();
menuItems.add("Regular Pancake Breakfast");
menuItems.add("Blueberry Pancakes");
{% endhighlight %}

### Processing Collections
{% highlight java %}
public void print(items) {
    for (int i; i < items.size(); i++) {
        String item = items.get(i);
        // print the item
    }
}
{% endhighlight %}
Separate what varies and encapsulate it.
# Exploring the iteration pattern
### The Iterator Pattern
**The Iterator Pattern** provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.
* Ask the object for its iterator.
* Use the iterator to iterate through the items in the aggregate.
* Iteration code now works with any kind of aggregate object.

![]({{site.baseurl}}/images/design patterns/iterator.jpg)
### The Iterator Pattern for Menus
![]({{site.baseurl}}/images/design patterns/menuiterator.jpg)

<!-- Implementing the iteration pattern -->
# Using Java's built-in iterators
### Using Java's built-in iterator interface
* **`java.util.Iterator`**\\
An interface for creating your own iterators\\
The type for built-in collection iterators
* Collection classes like `ArrayList`, `Vector`, `LinkedList`\\
All have a method, `iterator()`, which returns a built-in `java.util.Iterator` instance

**`java.util.Iterator`**
![]({{site.baseurl}}/images/design patterns/util iterator.jpg)
### Using `java.util.Iterator` for the Cafe
* **Remove our own Iterator interface**
* **PancakeHouseMenuIterator not needed**\\
We can use the ArrayList built-in iterator instead
* **DinerMenuIterator implements `java.util.Iterator`**\\
Add an implementation for `remove()` method

<!-- Implementing with Java's built-in iterators -->
# Making sure classes have only one responsibility
### Responsibility
* Every responsibility increases chance of change
* If you have two responsibilities, that is two areas of pontential change
* We want to avoid change whenever possible

## Design  Principle #6
A class should have only one reason to change.

### Separating Aggregates and Iteration
**Be Careful**
* We humans like to combine things
* We like to find commonality
* So, examine your designs and look for multiple reponsibilities
* And if they present areas of change, separate them.