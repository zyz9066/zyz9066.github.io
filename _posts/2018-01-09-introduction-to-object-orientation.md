---
layout: post
title:  "Introduction to Object Orientation"
date:   2018-01-09
tags:  [programming fundamentals]
---
# Introduction to object-oriented languages
### Class
It's the blueprint, the definition, the description
### Example classes

|Restaurant|Review|User|

|TextBox|Button|Window|

|Date|TimeZone|VideoPlayer|

### What does a Class define?

|**Attributes**<br>name<br>height<br>weight<br>gender<br>age|**Behavior**<br>walk<br>run<br>jump<br>speak<br>sleep|

|**Properties**<br>name<br>height<br>weight<br>gender<br>age|**Methods**<br>walk<br>run<br>jump<br>speak<br>sleep|

### Object
* The **object** is created from the **class**
* One **class** can create multiple **objects**

Encapsulation
# Using classes and objects
objects
{% highlight javascript %}
var myArray = [1,2,3,4,5];
var myRE = /hello/;
alert( myArray.length );
if ( myRE.test("hello world") ) {
    alert("Yes");
}
{% endhighlight %}
primitives
{% highlight javascript %}
var myNumber = 123;
var isValid = true;
{% endhighlight %}
### JavaScript Date Object
{% highlight javascript %}
var today = new Date();
var y2k = new Date(2000,0,1);
var y2k = new Date(2000,0,1,0,0,0);
today.getMonth(); // returns 0-11
today.getFullYear(); // YYYY (not zero-based)
today.getDate(); // 1-31 day of month
today.getDay(); // 0-6 day of week. 0 == sunday
today.getHours(); // 0-23
{% endhighlight %}
### set Methods of the date object
{% highlight javascript %}
var today = new Date();
today.setMonth(5);
today.setFullYear(2012);
today.setDay(0);
// etc.
{% endhighlight %}
### Using the math object
{% highlight javascript %}
var x = 200.6;
var y = Math.round(x); // 201
var a = 200, b = 10000, c = 4;
var biggest = Math.max(a,b,c);
var smallest = Math.min(a,b,c);
// Math.PI Math.random() .sqrt() .log()
{% endhighlight %}
### JavaScript Classes / Objects
* Array
* RegExp
* Date
* Math

{% highlight javascript %}
var today = new Date();
var myArray = [1,2,3];
var myArray = new Array(1,2,3);
var myRegExp = /hello/;
var myRegExp = new RegExp("hello");
{% endhighlight %}
# Reviewing object-oriented languages
C, C++, C#, Java, JavaScript, Perl, PHP, Python, Objective-C, Ruby, Visual Basic
### Example Classes

|Array|RegExp|Date|
|TextBox|Button|Image|
|FileStream|Cryptography|VedioPlayer|