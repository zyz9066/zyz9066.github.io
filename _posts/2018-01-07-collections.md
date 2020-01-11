---
layout: post
title:  "Collections"
date:   2018-01-07
tags:  [programming fundamentals]
---
# Working with arrays
{% highlight javascript %}
var myVar;
myVar = "x";
{% endhighlight %}
### Creating arrays
zero-based index
{% highlight javascript %}
var multipleValues = [];
multipleValues[0] = 50;
multipleValues[1] = 60;
multipleValues[2] = "Hello";
alert(multipleValues[2]); // "Hello"
{% endhighlight %}
### Creating arrays - Shorthand
{% highlight javascript %}
var multipleValues = [ 50,60,"Hello" ];
{% endhighlight %}
# Array behavior
* More than containers of data
* They are smart and do things

### Array Properties
{% highlight javascript %}
var myString = "This is a simple phrase.";
alert(myString.length); // 24
var myArray = [10,20,"test",true,99];
alert(myArray.length); // length is 5, highest index is [4]
{% endhighlight %}
### Array Methods
{% highlight javascript %}
someFunction(); // to call a function
alert("Hello");
var result = calculateValues(5,73);
{% endhighlight %}
"Methods" are functions that belong to an object
{% highlight javascript %}
someObject.someMethod(); // to call a method
myString.toUpperCase();
{% endhighlight %}
{% highlight javascript %}
var myArray = [10,"a",1,40,50];
myArray.reverse();
myArray.sort();
myArray.join();
var lastElement = myArray.pop();
myArray.push(123);
{% endhighlight %}
[JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference "JavaScript Reference")
# Iterating through collections
### Iterating through all elements in an array
{% highlight javascript %}
var i = 0; // start the index at zero!
while ( i < myArray.length ) { // check condition
    // ...
    // ...
    alert("The value is:" + myArray[i]); // use the index to access the current element
    // ...
    i++; // increment the index
}
{% endhighlight %}
# Collections in other languages
General knowledge is useful
### Allowed data in an array
mixed data

|10|32.1|"abc"||FALSE|

specific data

|10|32|54|34|1245|

|"abc"|"def"|"ghi"|"xyz"|"foo"|

### Fixed size / changing size arrays
mutable / immutable

|monday|tuesday|wednesday|thursday|friday|saturday|sunday|

### Associative Arrays

|"abc"|"def"|"ghi"|"xyz"|"foo"|
|a|b|c|d|e|

|alabama|alaska|arizona|arkansas|califonia|colorado|connecticut|...|
|AL|AK|AZ|AR|CA|CO|CT|...|

dictionary, map, table