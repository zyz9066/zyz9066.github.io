---
layout: post
title:  "Inheritance and Composition"
date:   2018-01-13
tags:  [object oriented design]
---
# Inheritance situations
### Inheritance describes an "IS A" relationship
* A car *is a* vehicle.
* A bus *is a* vehicle.
* A car is a bus.

* A employee *is a* person.
* A customer *is a* person.
* A customer is a shopping cart.

* A checking account *is a* kind of bank account.
* A savings account *is a* type of bank account.

* A Bentley Continental GT *is a* car *is a* vehicle.
* A Pomeranian *is a* dog *is a* mammal *is an* animal.

### Identifying Inheritance
![]({{site.baseurl}}/images/object oriented design/is a.jpg)

|BankAccount|
|-
|`accountName`<br>`balance`|
|`deposit()`<br>`withdraw()`|

|SavingsAccount|
|-
|(has every thing from BankAccount)<br>`interestRate`|

|CheckingAccount|
|-
|(has every thing from BankAccount)<br>`lastCheckNum`|

|InvestmentAccount|
|-
|(has every thing from BankAccount)<br>`accountRep`<br>**`withdraw()`**|

overriding

|Product|
|-
|`title`<br>`price`|
|`purchase()`<br>`download()`|

|Album|
|-
|`title`<br>`price`<br>**`artist`**|
|`purchase()`<br>`download()`|

|Book|
|-
|`title`<br>`price`<br>**`author`**|
|`purchase()`<br>`download()`|

|Movie|
|-
|`title`<br>`price`<br>**`director`**|
|`purchase()`<br>`download()`|

### Framework inheritance example
FileDialog ---> Dialog ---> Window ---> Container ---> Component ---> Object
# Using inheritance
Java
{% highlight java %}
public class Album extends Product { ... }
{% endhighlight %}
C#
{% highlight c# %}
public class Album : Product { ... }
{% endhighlight %}
VB.NET
{% highlight vb %}
Public Class Album
    Inherits Product ...
{% endhighlight %}
Ruby
{% highlight ruby %}
class Album < Product ...
{% endhighlight %}
C++
{% highlight c++ %}
class Album : Product { ... }
{% endhighlight %}
Objective-C
{% highlight objecctive_c %}
@interface Album : Product { ... }
{% endhighlight %}
### Calling a method in the super / parent /base class
Java
{% highlight java %}
super.doSomething();
{% endhighlight %}
C#
{% highlight c# %}
base.doSomething();
{% endhighlight %}
VB.NET
{% highlight vb %}
MyBase.doSomething();
{% endhighlight %}
Ruby
{% highlight ruby %}
super do_something
{% endhighlight %}
Objective-C
{% highlight objecctive_c %}
[super someMethod];
{% endhighlight %}
C++
{% highlight c++ %}
NamedBaseClass::doSomething();
{% endhighlight %}
# Using abstract classes
**abstract class**

|BankAccount|
|-
|`accountName`<br>`balance`|
|`deposit()`<br>`withdraw()`|

Java
{% highlight java %}
abstract class Bankaccount { ... }
{% endhighlight %}
VB.NET
{% highlight vb %}
Public MustInherit Class BankAccount ...
{% endhighlight %}

**concret class**

|SavingsAccount|
|-
|(has every thing from BankAccount)<br>`interestRate`|

|CheckingAccount|
|-
|(has every thing from BankAccount)<br>`lastCheckNum`|

|InvestmentAccount|
|-
|(has every thing from BankAccount)<br>`accountRep`<br>**`withdraw()`**|

# Using interfaces
Defining interface contracts
{% highlight java %}
interface Printable {

    // method signatures
    void print();
    void printToPDF(String filename);
    
}
{% endhighlight %}
Implementing interfaces
{% highlight java %}
class MyClass implements Printable {

    // method bodies
    public void print() {
        // provide implementation
    }
    public void printToPDF(String filename) {
        // provide implementation
    }
    
    // addtional functionality...
}
{% endhighlight %}
{% highlight java %}
// sometime later
while (genericObject in listOfObjects) {
    if ( genericObject instanceOf Printable ) {
        // if it implements the interface, we can use it
        genericObject.print();
    }
    
}
{% endhighlight %}

|<<Interface>><br>Printable|
|`print()`<br>`printToPDF()`|

MyClass **implementing** Printable

>"Program to an interface, not an implementation."\\
<cite>&mdash; Design Patterns, 1995</cite>

# Using aggregation and composition
### Associations
![]({{site.baseurl}}/images/object oriented design/conceptual model.jpg)
### Aggregation describes a "HAS A" relationship
* A customer *has a* address.
* A car *has a* engine.
* A bank *has many* bank accounts.
* A university *has many* students.

### Aggregation and Composition
![]({{site.baseurl}}/images/object oriented design/has a.jpg)