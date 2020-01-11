---
layout: post
title:  "Programming Style"
date:   2018-01-07
tags:  [programming fundamentals]
---
# Programming style
How you **must** write your code ---> How you **should** write your code
{% highlight javascript %}
var my_var;
var myVar;
var Str_MyVar;
if (x) {
    // ...
}
if (x)
{
    // ...
}
function otherFunction (x) {
    // ...
}
function someFunction (x) {
    otherFunction();
}
{% endhighlight %}
### Style Matters
* Your code should be easily *readable*
* Your code should be *consistent*
* You should know *accepted best practices*

### JavaScript Naming Conventions
`var letters, numbers, $, _ ;`
### Variables and Functions: camelCase
{% highlight javascript %}
var highScore;
var evenHigherScore;
function calculateDistance() {...}
function checkFormFields() {...}
{% endhighlight %}
### Alternative Naming Styles
{% highlight javascript %}
var high_score;
var str_firstname;
{% endhighlight %}
### Brace Style
{% highlight javascript %}
if (x) {
    // ...
} else {
    // ...
}
if (x)
{
    // ...
}
while (x) {
    // ...
}
for (var i = 0; i < 10; i++) {
    // ...
}
function doStuff() {
    // ...
}
{% endhighlight %}
### Define your functions before you call them
{% highlight javascript %}
function someFunction (x) {
    otherFunction();
}
function otherFunction (x) {
    // ...
}
{% endhighlight %}
{% highlight javascript %}
function otherFunction (x) {
    // ...
}
function someFunction (x) {
    otherFunction();
}
{% endhighlight %}
## Guidelines Review
* Use *camelCase* for variables, functions and methods
* Open *curly braces* on the same line
* Define your functions *before* you call them
* *Always* use semicolons to end a statement
* *Always* use var when declaring a variable

### Formal Style Guidelines
Search for "javascript style guidelines"
# Writing pseudocode
### Pseudocode
~~~~~~~
create email variable
ask user for email address
store user's email address in email variable

if email address matches accepted pattern
    add them to email list
else
    show error message
~~~~~~~
~~~~~~~
IF balance < 0
    display "balance is negative!" message
ELSE
    display "balance OK" message
END IF
~~~~~~~
~~~~~~~
set total to zero

get list of numbers

loop through each number in the list
    add each number to total
end loop

if number more than zero
    print "it's positive" message
else
    print "it's zero or less" message
end if
~~~~~~~
~~~~~~~
if missile-image touches spaceship-image
    replace spaceship-image with explosion-image
    play explosion sound
    if remaining-lives counter is zero
        show "game over" message
    else
        subtract 1 from remaining-lives
        show "begin" message
        reset spaceship to starting position
    \ (etc)
~~~~~~~