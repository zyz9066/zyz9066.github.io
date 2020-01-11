---
layout: post
title:  "Input and Output"
date:   2018-01-08
tags:  [programming fundamentals]
---
# Input/output and persistence
### Input and Output
input ---> program ---> output
### Graphical User Interfaces
Persistence Support
* **Visual Basic.NET**: Save
* **Objective-C**: writeToFile
* **Java**: write
* **COBOL**: WRITE

# Reading and writing from the DOM
Document Object Model (DOM)
{% highlight html %}
<html>
    <head>
        <title>About JavaScript</title>
    </head>
    <body>
        <h1>Learning JavaScript</h1>
        <p>JavaScript is: </p>
        <ul>
            <li>a language that runs in the browser</li>
            <li>simple, but powerful</li>
            <li>misunderstood</li>
        </ul>
    </body>
</html>
{% endhighlight %}
webpage, pieces, agreed-upon set of terms
### What you can do with the DOM
* "Get the title text"
* "Get the second paragraph"
* "Get the third link in the menu and set it to invisible"
* "Change the background color of all paragraphs"
* "Get all the elements in the list"
* "Find the image call "*logo*" and move it 40 pixels to the right"
* "Change a link so it performs a JavaScript function when clicked"
* "Create a new list and insert between first and second paragraphs"

# Event driven programming
### Event names
`onload, onclick, onmouseover, onblur, onfocus`
### Handling Events
`element.event =`
* `window.onload`
* `nameField.onblur`

{% highlight javascript %}
myelement.onclick = fucntion() {
    // your event handler code
    // ...
    // ...
};
{% endhighlight %}
# Introduction to file I/O
### Reading Files
~~~~~~~
open file at path "myfile.txt"
read contents of file into string variable
close file
~~~~~~~
### Reading Files - Ruby
{% highlight ruby %}
filename = 'simpleexample.txt'
f = File.open(filename, 'r')
f.each_line { |line|
    puts line
}
f.close
{% endhighlight %}
### Writing Files - Ruby
{% highlight ruby %}
message = 'This is for output.'
filename = 'myoutput.txt'
File.open filename, 'w' do |f|
    f.write message
end
{% endhighlight %}
### Breaking Files Apart
~~~~~~~
open file ar path "myfile.txt"
while file has lines left
    read one line
    display line
end
close file
~~~~~~~
Streams