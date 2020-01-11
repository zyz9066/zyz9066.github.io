---
layout: post
title:  "Iteration: Writing Loops"
date:   2018-01-05
tags:  [programming fundamentals]
---
# Introduction to iteration
### Using iteration
{% highlight javascript %}
repeat 5 times {
    statement one
    statement two
}
repeat 5000 times {
    statement one
    statement two
}
keep repeating until told to stop {
    statement one
    statement two
}
go through all fields on a web page {
    statement one
    statement two
}
for every mp3 file in a folder {
    statement one
    statement two
}
{% endhighlight %}
### While Loop
{% highlight javascript %}
var a = 1;
if ( a < 10 ) {
    alert(a);
}
while ( a < 10 ) { // true
    alert(a); // infinite loop!
}
while ( a < 10 ) { // till false
    alert(a);
    a++;
}
{% endhighlight %}
# Writing a while statement
### While Loop
{% highlight javascript %}
var i = 1; // set up the index
while ( i < 10 ) { // check the condition
    // do stuff
    // do stuff
    // do stuff
    // etc...
    i++; // increment the index
}
{% endhighlight %}
Fencepost Error

$$\begin{array}{|c|c|}
10&10&10&10&10
\end{array}$$\\
50, 6
# Creating a for loop
### For Loop
{% highlight javascript %}
for ( var i = 1 ; i < 10 ; i++ ) {
    // do stuff
    // do stuff
    // do stuff
    // etc...
}
{% endhighlight %}
### Do..While Loop
{% highlight javascript %}
var a =1;
do {
    // your code
    a++;
} while ( a < 10 );
{% endhighlight %}
It will always happen at least once!