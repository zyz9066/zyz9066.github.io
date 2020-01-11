---
layout: post
title:  "Core Programming Syntax"
date:   2018-01-04
tags:  [programming fundamentals]
---
# Why JavaScript
Operating system: C++, Java, C#, Objective-C, Flash(ActionScript), MS Office(VBScript), Web Browser(JavaScript).
* JavaScript is an interpreted language.
* JavaScript is case sensitive.\\
`document.getElementById("example").style.display = "none";`\\
`document.getElementByID("example").style.display = "none";`

{% highlight javascript %}
//show and hide sections of a form
function preparePage() {
    document.getElementById("brochures").onclick = function() {
        if (document.ElementById("brochures").checked) {
            //use CSS style to show it
            document.getElementById("borchures").style.display = "block";
        } else {
            // hide the div
            document.getElementById("first").style.display = "none";
        }
    };
    // now hide it on the initial page load.
    document.getElementById("first").style.display = "none";
}
window.onload = function() {
    preparePage();
};
{% endhighlight %}

<!-- Creating first program in JavaScript -->
# Requesting Input
{% highlight javascript %}
var name = prompt("What is your name?");
alert("Hello, " + name);
{% endhighlight %}