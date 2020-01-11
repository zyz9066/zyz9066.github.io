---
layout: post
title:  "Variables and Data Types"
date:   2018-01-04
tags:  [programming fundamentals]
---
# Introduction to variables and data types
### Working with variables
Creating variables
{% highlight javascript %}
var year;
var customerEmail;
var todayDate;
var foo;
var x;
var problems99; // right
var 99problems; // wrong
{% endhighlight %}
letters, numbers, -, $.
{% highlight javascript %}
var year;
year = 2011;
{% endhighlight %}
{% highlight javascript %}
var year = 2011;
{% endhighlight %}
{% highlight javascript %}
year = 2011;
{% endhighlight %}
Variables names are case sensitive
{% highlight javascript %}
var x = 200;
X =210;
{% endhighlight %}
Multiple variables
{% highlight javascript %}
var year, month, day;
{% endhighlight %}
Multiple variables with values
{% highlight javascript %}
var year = 2011;
var month = 10;
var day = 31;
{% endhighlight %}
{% highlight javascript %}
var year = 2011, month = 10, day = 31;
{% endhighlight %}
<!-- # Understanding strong, weak, and duck-typed languages -->
### Weak Typing
{% highlight javascript %}
var myVariable;
myVariable = 200;
myVariable = "Hello";
myVariable = 'Hello';
myVariable = true;
myVariable = false;
{% endhighlight %}
<!-- Working with numbers -->
# Characters and strings
### Strings
{% highlight javascript %}
alert("Hello, world");
{% endhighlight %}
{% highlight javascript %}
var message = "Hello, world";
alert(message);
{% endhighlight %}
### Working with strings
{% highlight javascript %}
var myString = "Double quotes work."; // right
var myString = 'Single quotes work too.'; // right
var myString = 'one or the other"; // wrong
{% endhighlight %}
### Quotes inside quotes
{% highlight javascript %}
var phrase = 'Don't mix your quotes'; // wrong
var phrase = "Don't mix your quotes"; // right
var phrase = "He said "that's fine," and left."; // wrong
var phrase = "He said \"that's fine,\" and left."; // right
{% endhighlight %}
### String Properties
{% highlight javascript %}
var phrase = "This is a simple phrase.";
alert(phrase.length);
{% endhighlight %}
# Working with operators
### Using operators
{% highlight javascript %}
alert("Hello world");
prompt("What is your name?");
{% endhighlight %}
Assignment
{% highlight javascript %}
balance = 500;
{% endhighlight %}
Arithmetic operators
{% highlight javascript %}
var a = 100;
var b = 50;
var result = a + b;
var result = a - b;
var result = a * b;
var result = a / b;
{% endhighlight %}
{% highlight javascript %}
score = score + 10;
score += 10;
score -= 10;
score *= 10;
score /= 10;
{% endhighlight %}
Operator precedence
{% highlight javascript %}
result = 5 + 5 * 10; // 55
result = (5 + 5) * 10; // 100
{% endhighlight %}
Increment / decrement
{% highlight javascript %}
a = a + 1;
a += 1;
a++;
a = a - 1;
a -= 1;
a--;
{% endhighlight %}
<!-- Properly using white space
Adding comments to code for human understanding -->