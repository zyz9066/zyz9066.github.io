---
layout: post
title:  "When Things Go Wrong"
date:   2018-01-08
tags:  [programming fundamentals]
---
# Introduction to debugging
* **syntax** errors
* **logic** errors

**reproduce** the **problem**
### Syntax issues
{% highlight javascript %}
ALert("Hello, world");
alert("Hello, world"):
alert("Hello, world);
{% endhighlight %}
{% highlight javascript %}
function startCountdown() {
    // get contents of the "minutes" text box
    var minutes = document.getElementById("minutes").value;
    /* check if not a number
    if (isNaN(minutes)) {
        alert("Please enter a number!");
        return;
    }
    // how many seconds?
    secondsRemaining = minutes * 60;
    // every second, call the "tick" function
    intervalHandle = setInterval(tick, 1000);
    // hide the form
    document.getElementById("inputArea").style.display = "none";
}
{% endhighlight %}
### Syntax issues - color coding
{% highlight javascript %}
function startCountdown() {
    // get contents of the "minutes" text box
    var minutes = document.getElementById("minutes").value;
    // check if not a number
    if (isNaN(minutes)) {
        alert("Please enter a number!");
        return;
    }
    // how many seconds?
    secondsRemaining = minutes * 60;
    // every second, call the "tick" function
    intervalHandle = setInterval(tick, 1000);
    // hide the form
    document.getElementById("inputArea").style.display = "none";
}
{% endhighlight %}
### Logic issues

|10|10|10|10|10|

50
{% highlight javascript %}
function myFunction() {
    // do stuff
    return 0;
    // do stuff
    // do stuff
    // do stuff
}
{% endhighlight %}
### Arithmetic issues
{% highlight javascript %}
var a = 100;
var b = 0;
var result = a / b;
alert(result);
{% endhighlight %}
<!-- Tracing through a section of code -->
<!-- Understanding error messages -->
# Using debuggers
Firefox: [Firebug](https://getfirebug.com/ "Firebug")