---
layout: post
title:  "Introduction to Algorithms"
date:   2018-06-04
tags:  [algorithm]
---
# Euclid's algorithm
## What is an **Algorithm**?
>An algorithm is a way of solving **WELL-SPECIFIED** computational problems.
<cite>&mdash; Cormen et al.</cite>

>An finite set of rules that give a sequence of operations for solving a specific type of problem
<cite>&mdash; Knuth</cite>

1. Put teabag in cup
2. Fill kettle with water
3. Boil kettle
4. Pour water into cup
5. Add milk
6. Stir
7. Drink

## Euclid's algorithm
* <big>Used to find the **GCD** of two positive integers.</big>

Consider two positive integers '$$m$$' and '$$n$$', such that, $$m>n$$.
* **Step 1**: Divide $$m$$ by $$n$$, and let the remainder be $$r$$.
* **Step 2**: If $$r=0$$, the algorithm ends, $$n$$ is the GCD.
* **Step 3**: Set, $$m\rightarrow n$$, $$n\rightarrow r$$, go back to step 1 and continue till, $$r=0$$.

# Bubble sort algorithm
### Rules
* You can only pick one ball at a time.
* Before picking up another ball, you have to drop the existing ball-in-hand, in an empty basket.
* You have to start from the left most basket and arrange the balls moving towards the right.
* You can use a stick to keep track of the sorted part.

# Why Algorithms?
* Gives an idea of running time.
* Help us decide on hardware requirements.
* What is feasible Vs what is possible.
* Improvement is a never ending process.

# Correctness of an Algorithm
**STEP-1**: Statement to be proven.  
**STEP-2**: List all assumptions.  
**STEP-3**: Chain of reasoning from assumptions to the statement.

## Incorrectness of an Algorithm
**STEP-1**: Give a set of data for which the algorithm does not work.  
**STEP-2**: Usually consider small data sets.  
**STEP-3**: Especially consider borderline cases.
