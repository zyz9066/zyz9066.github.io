---
layout: post
title:  "The Singleton Pattern"
date:   2018-05-11
tags:  [design patterns]
---
# What is the singleton pattern?
### One of a Kind
**The Singleton Pattern** ensures a class has only one instance, and provides a global access point to it.

### Singleton Uses
* Connection and thread pools
* Logging facilities
* Preference and registry objects
* Device, printer, and graphics drivers
* UI dialog and other modal controls
* Anywhere you want ot ensure a resource exists only once

### Isn't This Easy?
`new MySingleObject();`
# Understanding the classic singleton pattern
### Why Can't Just Instantiate One?
`new MySingleObject();`\\
`new MySingleObject();`
### Preventing Instantiation
{% highlight java %}
public Singleton {
    private Singleton() {}
}
{% endhighlight %}
{% highlight java %}
public Singleton {
    private Singleton() {}
    
    public static Singleton getInstance() {
        return new Singleton();
    }
}
{% endhighlight %}
{% highlight java %}
public Singleton {
    private static Singleton unique;
    private Singleton() {}
    
    public static Singleton getInstance() {
        if (unique == null) {
            unique = new Singleton();
        }
        return unique;
    }
}
{% endhighlight %}
### Singleton Class Diagram

|***`Singleton`***|
|`static uniqueInstance`|
|`static getInstance()`|

<!-- Implementing the classic singleton pattern -->
# Dealing with multithreading
### Some Subtle Singleton Issues
**Reconsider Code with Threads**
{% highlight java %}
public Singleton {
    private static Singleton unique;
    private Singleton() {}
    
    public static Singleton getInstance() {
        if (unique == null) {
            unique = new Singleton();
        }
        return unique;
    }
}
{% endhighlight %}
### Multiple Thread Singleton
**THREAD #1**
{% highlight java %}
if (unique == null) {
    unique = new Singleton();
}
return unique;
{% endhighlight %}
**THREAD #2**
{% highlight java %}
if (unique == null) {
    unique = new Singleton();
}
return unique;
{% endhighlight %}
### What to do?
* statically initialized
* synchronized - thread safe

<!-- Improving the singleton pattern implementation -->