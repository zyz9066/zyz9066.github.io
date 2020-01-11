---
layout: post
title:  "Hashtables"
date:   2018-06-09
tags:  [data structure]
---
# Introduction
Keys, Value  
put(key, object) $$\to O(1)$$  
get(key) $$\to O(1)$$
# Direct access tables
ASSUMPTIONS:
* Keys are drawn from a set of integers, $$s=\{0,1,2,3,\cdots,m-1\}$$
* Keys are distinct

# Hashing
A hash function 'h' maps keys "randomly" into slots (arrays indices) of table T (array)  
**COLLISION**
# Resolving collisions through chaining
$$h(K_1)=h(K_2)=h(K_3)=\cdots=h(K_n)=i$$
## Time Complexity
$$Find(K_j)=O(n)$$  
Average Case  
If we have $$n$$ keys to be put in $$m$$ slots, in each slot we will have (on an average): $$\frac{n}{m}=\alpha$$  
$$Find(K_j)=O(1+\alpha)$$  
Hash Function Call, Average length of the list in the chain  
If, $$n=O(m)\implies\alpha=\frac nm=constant,\;Find(K_j)=O(1)$$
# The Hash Function
Distribute keys uniformly into slots.  
Keys as natural numbers, $$N=\{0,1,2,3\cdots\}$$  
"hash"  
$$\left.
\begin{align}
h&\to 104\\
a&\to 97\\
s&\to 115\\
h&\to 104
\end{align}
\right\}
{\text{Key}_1=420\;\Large\color{red}{\times}\\
\text{Key}_2=(128)^3\times 104+(128)^2\times 97+128\times 115+104=219707880}$$  
Use chaining to resolve the collision  
$$m:
\begin{cases}
\text{A prime number.}\\
\text{Not close to a power of 2 or 10.}
\end{cases}$$
# Open addressing to resolve collisions
Probe step, $$n\le m$$  
Delete is difficult.
# Strategies for open addressing
<u>Linear Probing</u>  
$$h(k,i)=(h(k,0)+i)%m$$  
Problem: Clustering of records

<u>Quadratic Probing</u>  
$$h(k,i)=(h(k,0)+i^2)%m$$

<u>Double Hashing</u>  
$$h(k,i)=(h_1(k)+ih_2(k))%m$$  
Two different hash functions
# Time complexity: Open addressing
<u>Assume Uniform Hashing</u>  
P(h(a)=h(b))=1/m  
<u>Worst case:</u> $$O(n)$$  
<u>Average case:</u>

$$\text{Number of probes}\le\frac{1}{1-\alpha}\qquad\alpha=n/m$$

$$\small\text{if, }\alpha<1\;(i.e.\;n<m)$$

$$\text{If the table is 50% full, }\alpha=0.5$$

$$\small\text{Number of probes}\le 2$$

$$\text{If the table is 80% full, }\alpha=0.8$$

$$\small\text{Number of probes}\le 5$$

$$\alpha\to 1\text{ (near full space utilization), Performance }\downarrow$$
