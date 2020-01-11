---
layout: post
title:  "Exploring the Programming Languages"
date:   2018-01-10
tags:  [programming fundamentals]
---
# Introduction to languages
C, C++, C#, Java, JavaScript, Perl, PHP, Python, Objective-C, Ruby, Visual Basic
# C-based languages
### About

|Characteristics|What's it used for?|
|:-:|:-:|
|*not object-oriented*|*everthing!*|
|*low-level, compiled,<br>strongly typed*|games, utilities, embedded systems<br>operating systems|
|*intermediate / advanced*|*not* typical desktop / web / mobile|

### Example
{% highlight c %}
#include <stdio.h>
// this is a comment
int main (void) {
    int x;
    x = calculateSomeValue();
    printf("Hello\n");
}
{% endhighlight %}
### Getting Started
* **Compiler**: GCC, many IDEs
* **Website**: [gcc.gnu.org](http://gcc.gnu.org)
* **Book**: The C Programming Language ("K&R")

# The Java world
### About

|Characteristics|What's it used for?|
|:-:|:-:|
|*object-oriented<br>huge library (Java Class Library)*|*cross-platform<br>"write once, run anywhere*|
|*high-level, hybrid-compilation,<br>strongly typed, garbage collected*|*desktop applications*|
|*intermediate*|*mobile applications: android*|

### Example
{% highlight java %}
class HelloWorldApp {
    // another main method!
    public static void main(String[] args) {
        int myInt = 55;
        System.out.println("Hello World!");
    }
}
{% endhighlight %}
### Getting Started
* **Compiler / IDE**: Eclipse, Netbeans
* **Website**: [oracle java](http://www.oracle.com/technetwork/java/index.html)

# .NET languages: C# and Visual Basic .NET
### About

|Characteristics|What's it used for?|
|:-:|:-:|
|*object-oriented<br>huge library (.NET Framework)*|*windows desktop apps*|
|*high-level, hybrid-compilation,<br>strongly typed, garbage collected*|*web apps: "ASP.NET"*|
|*intermediate*|*mobile applications: windows phone*|

### Example - C#
{% highlight c# %}
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
{% endhighlight %}
### Example - VB.NET
{% highlight vb %}
Module Module1
    Sub Main()
        System.Console.WriteLine("Hello, world!")
    End Sub
End Module
{% endhighlight %}
### Getting Started
* **Compiler / IDE**: Visual Studio
* **Website**: [docs.microsoft.com](https://docs.microsoft.com/)

# Ruby
### About

|Characteristics|What's it used for?|
|:-:|:-:|
|*object-oriented*|*cross-platform*|
|*high-level, interpreted,<br>garbage collected*|*web apps: Ruby on Rails*|
|*beginner / intermediate*|*utilities*|

### Example
{% highlight ruby %}
puts "Hello,world!"
# this is a comment
def welcome(name)
    puts "hello, #{name}"
end
x = "bob"
welcome(x)
{% endhighlight %}
### Getting Started
* **Editor / IDE**: TextMate, RubyMine, Aptana
* **Website**: [www.rubyonrails.org](https://www.rubyonrails.org), [www.ruby-lang.org](https://www.ruby-lang.org)

# Python
### About

|Characteristics|What's it used for?|
|:-:|:-:|
|*object-oriented<br>large library*|*cross-platform*|
|*high-level, interpreted,<br>strongly typed, garbage collected*|*web apps*|
|*beginner / intermediate*|*embedded scripting language*|

### Example
{% highlight python %}
print 'Hello,world!'
# this is a comment
def sayhello(name):
    print 'hello', name
    
sayhello('simon')
{% endhighlight %}
### Getting Started
* **Editor / IDE**: Eclipse with PyDev, Komodo
* **Website**: [www.python.org](https://www.python.org)

# Objective-C
### About

|Characteristics|What's it used for?|
|:-:|:-:|
|*object-oriented<br>large library (Cocoa)*|*Apple*|
|*high-level, compiled,<br>strongly typed, reference counted*|*Mac desktop development*|
|*intermediate / advanced*|*iOS (iPhone, iPad) development*|

### Example
{% highlight objective_c %}
#import <Foundation/Foundation.h>

int main(int argc, const char *argv[]) {
    NSAutoreleasePool *pool = [[NSAutoreleasePool alloc] init]
    
    NSLog(@"Hello world\n");
    
    [pool drain];
    return 0;
}
{% endhighlight %}
### Getting Started
* **Editor / IDE**: Xcode
* **Website**: [developer.apple.com](https://developer.apple.com)

# Libraries and frameworks
* .NET Framework Class Library
* Java Platform SE API Specification
* Python Standard Library
* iOS Developer Library