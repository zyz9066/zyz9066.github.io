---
layout: post
title:  "Writing Conditional code"
date:   2018-01-04
tags:  [programming fundamentals]
---
# Building with the if statement
### Conditionaal Code
{% highlight javascript %}
if ( condition ) {
    // your conditional code goes here
    // ...
}
{% endhighlight %}
{% highlight javascript %}
if ( condition ) {
    alert("it's true!");
    // etc...
}
{% endhighlight %}
{% highlight javascript %}
if ( a < 50 ) {
    alert("it's true!");
    // etc...
}
if ( b > 20 ) {
    alert("it's true!");
    // etc...
}
if ( c == 99 ) {
    alert("it's true!");
    // etc...
}
if ( c === 99 ) {
    alert("it's true!");
    // etc...
}
if ( d != 100 ) {
    alert("it's true!");
    // etc...
}
{% endhighlight %}
### Terminology
( parentheses ), [ brackets ], { braces }
<!-- Working with complex conditions -->
# Setting comparison operators
### Equality
{% highlight javascript %}
if ( a == b ) {
    // execute this code
}
{% endhighlight %}
Assignment instead of equality
{% highlight javascript %}
var a = 5;
var b = 10;
if ( a = b ) {
    // always true!
}
{% endhighlight %}
### Operators with =

|=|assignment|
|==|equality|
|===|strict equality|

### Comparison
{% highlight javascript %}
if ( a == b ) { ... }
if ( a != b ) { ... }
if ( a === b ) { ... }
if ( a !== b ) { ... }
if ( a > b ) { ... }
if ( a < b ) { ... }
if ( a >= b ) { ... }
if ( a <= b ) { ... }
{% endhighlight %}
### Logical AND / OR
{% highlight javascript %}
if ( a === b && c === d ) { ... }
if ( a === b || c === d ) { ... }
if ( (a > b) && (c < d) ) { ... }
{% endhighlight %}
<!--  Using the switch statement -->