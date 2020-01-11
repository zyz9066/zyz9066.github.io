---
layout: post
title:  "More about Strings"
date:   2018-01-06
tags:  [programming fundamentals]
---
# Cleaning up with string concatenation
### Addition vs. Concatenation
{% highlight javascript %}
var foo = 5;
var bar = 5;
alert(foo + bar); // 10
var foo = "5";
var bar = "5";
alert(foo + bar); // 55
var foo = 5
var bar = "5";
alert(foo + bar); // 55 - one is a string
var foo = 5;
var bar = "b";
alert(foo * bar); // NaN
{% endhighlight %}
### Not a Number
{% highlight javascript %}
var foo = "55"; // could be "abc"
var myNumber = Number(foo); // make it a number
// double negative - if NOT NOT a number
if ( !isNaN(myNumber) ) {
    alert("It IS a number");
}
{% endhighlight %}
# Finding patterns in strings
### String Properties
{% highlight javascript %}
var phrase = "This is a simple phrase.";
alert( phrase.length ); // 24
{% endhighlight %}
### String Methods
{% highlight javascript %}
var phrase = "This is a simple phrase.";
alert( phrase.toUpperCase ); // THIS IS A SIMPLE PHRASE.
{% endhighlight %}
### String Comparison
{% highlight javascript %}
var str1 = "Hello";
var str2 = "hello";
// str1 != str2
if ( str1.toLowerCase() == str2.toLowerCase() ) {
    alert("Yes, equal");
}
{% endhighlight %}
{% highlight javascript %}
var str1 = "aardvark";
var str2 = "beluga";
if ( str1 < str2 ) { ... // true
}
var str1 = "aardvark";
var str2 = "Beluga";
if ( str1 < str2 ) { ... // false!
}
{% endhighlight %}
**ABCD...** less than **abcd...**
### String Methods - indexOf
{% highlight javascript %}
var phrase = "We want a groovy keyword.";
var position = phrase.indexOf("groovy"); // 10
// it returns -1 if the term is not found
if ( phrase.indexOf("DDDD") == -1 ) {
    alert("That word does not occur.");
}
// there is also .lastIndexOf()
{% endhighlight %}
### String Methods - Slice
{% highlight javascript %}
var phrase = "Yet another phrase.";
var segment = phrase.slice(6,11); // other
// .substring() .substr() 
{% endhighlight %}
# Introduction to regular expressions
* Built into many programming languages
* Not pleasant, but quite useful
* Two parts: Create expression, Apply and ask if it matches
### Create Regular Expressions
{% highlight javascript %}
var myRE = /hello/;
// or
var myRE = new RegExp("hello");
var myString = "Does this sentence have the word hello in it?";
if ( myRE.test(myString) ) {
    alert("Yes");
}
{% endhighlight %}
### Creating Patterns
{% highlight javascript %}
var myRE = /^hello/; // ^ at the start
var myRE = /hello$/; // $ at the end
var myRE = /hel+o/; // + once or more: "helo","hello","helllllllo"
var myRE = /hel*o/; // * zero or more: "heo",helo","hello","helllllllo"
var myRE = /hel?o/; // ? zero or one: "heo",helo"
var myRE = /hello|goodbye/; // either|or
var myRE = /he..o/; // . any character
var myRE = /\wello/; // \w alphanumeric or _
var myRE = /\bhello/; // \b word boundary
var myRE = /[crnld]ope/; // [...] range of chars: "cope","rope","nope","lope","dope"
{% endhighlight %}
### More Complex Patterns
`/^[0-9]{5}(?:-[0-9]{4})?$/`\\
`/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/`