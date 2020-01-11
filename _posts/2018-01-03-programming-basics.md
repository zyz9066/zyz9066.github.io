---
layout: post
title:  "Programming Basics"
date:   2018-01-03
tags:  [programming fundamentals]
---
# What is programming?
"A computer program is a set of instructions..."

* turn right
* drive one mile
* turn left on Acacia Avenue
* take the second right

### Statements
* BASIC: `LET Balance = 500`
* AppleSript: `set balance to 500`
* Java: `balance = 500;`
* COBOL: `MOVE 500 TO BALANCE`

# What is a programming language?
C, C++, C#, Java, JavaScript, Perl, PHP, Python, Objective-C, Ruby, Visual Basic

$$\begin{array}{r|c}
JavaScript, ActionScript &\\
Ruby, Python & High-Level\;Languages\\
Java, C\#, VB.NET & \\
Objective-C & \\
\\
C++ & \\
\\
C& \\
 & Low-Level\;Languages\\
Assembly\;Language & \\
\end{array}$$

**CPU** Machine Code
# Writing source code
* JavaScript(.js): `alert("Hello, world!");`
* Perl(.pl): `say "Hello, world!";`
* Ruby(.ruby): `puts "Hello, world!";`
* Groovy(.groovy): `say "Hello, world!";`

* ALGOL 68: `print("Hello, world!")`
* Python 3: `print("Hello, world!")`
* Lua: `print("Hello, world!")`

ALGOL 60
{% highlight algol %}
BEGIN
    DISPLAY ("Hello, world!");
END.
{% endhighlight %}

C
{% highlight c %}
#include <stdio.h>
int main(void) {
    printf("Hello, world!\n");
    return 0;
}
{% endhighlight %}

C#
{% highlight c# %}
using System;
class Example {
    static void Main(String[] args) {
        Console.WriteLine("Hello, world!");
    }
}
{% endhighlight %}

Java
{% highlight java %}
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
{% endhighlight %}

Programmer's text editors\\
Integrated development environments (IDE)

# Complied and interpreted languages
### Pros and Cons

|**Compiled**|**Interpreted**|
|:-:|:-:|
|*ready* to run|interpreter required|
|often *faster*|often *slower*|
|source code is *private*|source code is *public*|
|*not* cross-platform|cross-platform|
|inflexible|simple to test|
|extra step|easier to debug|

Intermediate Approach
### Language Examples
* **Compiled**: C, C++, Objective-C
* **Interpreted**: PHP, JavaScript
* **Hybrid**: Java, C#, VB.NET, Python