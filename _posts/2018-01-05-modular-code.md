---
layout: post
title:  "Modular Code"
date:   2018-01-05
tags:  [programming fundamentals]
---
# Breaking your code apart

|calculateArea|get window height<br>get window width<br>calculate area<br>store area|
|createMessage|do calculation<br>check value<br>output message|
|animateImage|get image position<br>calculate new value<br>set image position<br>change text color<br>if position correct<br>output message|

### Functions in JavaScript
{% highlight javascript %}
function myFunction () {
    alert("This code is inside the function");
    // loops, if statements, anything!
    // ...
}
// sometime later
myFunction();
myFunction();
myFunction();
{% endhighlight %}
If it's in a function, it won't run unless you call it.
### Where to Declare Functions
{% highlight javascript %}
function myOtherFunction () {
    // lots of code
}
function myFunction () {
    // lots of code
    myOtherFunction();
}
myFunction();
{% endhighlight %}
<!-- Creating and calling functions -->
<!-- Setting parameters and arguments -->
# Variable Scope
{% highlight javascript %}
function simpleFunction () {
    // lots of code
    var x = 500;
    // lots of code
    alert(x);
}
simpleFunction(); // 500
alert(x); // undefined
{% endhighlight %}
{% highlight javascript %}
var x; // global variable
function simpleFunction () {
    // lots of code
    x = 500;
    // lots of code
    alert(x);
}
simpleFunction(); // 500
alert(x); // 500
{% endhighlight %}
# Splitting code into different files
### Linking to multiple JavaScript Files
{% highlight html %}
...
    <div>
        <p>Regular content, etc.</p>
    </div>
    <script src="script.js"></script>
    <script src="morescript.js"></script>
    <script src="evenmorescript.js"></script>
  </body>
</html>
{% endhighlight %}
### Order is important
{% highlight html %}
...
    <div>
        <p>Regular content, etc.</p>
    </div>
    <script src="functions.js"></script>
    <script src="morefunctions.js"></script>
    <script src="script.js"></script>
  </body>
</html>
{% endhighlight %}