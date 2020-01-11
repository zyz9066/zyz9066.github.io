---
layout: post
title:  "Design Patterns"
date:   2018-05-01
tags:  [design patterns]
---
# Understanding the need for design patterns
**Dealing with Change**\\
*Software Changes*\\
"We need to add a new feature..."\\
"There's a change in the spec..."\\
"We've found a big bug..."
* Software has lots of ways to change
* There are many design patterns to deal with change
* Design patterns address many of the ways software changes over time

**Do Not Worry**\\
Others have been there before you...\\
And they have packaged up this knowledge,
into *Design Patterns*
**Use Design Patterns**\\
By learning them,\\
And then applyiing them to your own OO designs...\\
You will create more flexible and maintainable code
# What are design patterns
**Dealing with Change**
* Design patterns are general solutions to common problems
* A pattern is a guideline for flexible and resilient code design

"I have a problem. When one of my object changes, I need to let all these other objects know. Is there a good way to do that?"
* This is a common problem
* There is a proven method to solve it: **The Observer Pattern**

**Where did design patterns come from?**
* Invented by the "gang of four"
* 23 original patterns
* Now, there are many patterns for many different software problems
* We are focusing on 7 of the most commonly used patterns

# Using design patterns
**How to use design patterns**
* A design pattern is not a library, module or package
* It's a guideline for how to solve a problem
* Higher level than a library
* First understand the pattern, and then use its design in your software

**Shared Vocabulary**\\
"First, register your object with mine, then implement an update method, then when it gets called, cal my geValue method"\\
"Just use the Observer Pattern"
* Shared bocabularies are powerful
* Efficient to communicate designs
* Keep thinking at level of design, not low-level code

**Using (or Reusing) Design Patterns**
* Ultimate in reuse
* Built from years of software development experience
* Saves time, and trial and error
* Not reusing code, reusing *experience*