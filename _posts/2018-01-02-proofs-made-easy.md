---
layout: post
title:  "Proofs Made Easy"
date:   2018-01-02
tags:  [discrete mathematics]
---
# Write a general outline for a proof
### Direct Proof
Prove that there exists an integer $$x$$, $$x\le 10$$ such that $$x$$ is odd and $$x$$ is a perfect square. $$x=9$$
# Subset Proofs
**Prove $$A\cap B\subseteq B$$:**\\
$$A\cap B=\{x\mid x\in A\land x\in B\}$$
* Suppose $$a\in A\cap B$$
* $$a\in A$$ and $$a\in B$$, by definition of intersection
* $$a\in B$$, by specialization
* $$\therefore A\cap B\subseteq B$$, by definition of subset

# Conditional Proofs
### Definitions
* An integer $$n$$ is even *iff* $$n$$ = twice some integer, written as $$n=2k$$.
* An integer $$n$$ is odd *iff* $$n$$ = twice some integer, written as $$n=2k+1$$.
* An integer $$n$$ is prime *iff* $$n>1$$ and for all positive integers $$r$$ and $$s$$, if $$n=r\cdot s$$, then $$r=1$$ or $$s=1$$.
* An integer $$n$$ is perfect square *iff* $$n=k^2$$ for some integer $$k$$.
* An real number $$r$$ is rational *iff* it can be expressed as a quotient of two integers with a nonozero denominator. Theorem: The sum of any two rational numbers is rational.
* Integers are closed under addition, subtraction, and multiplication.

Prove: If $$r$$ and $$s$$ are any two rational numbers, then $$(r+s)/2$$ is rational.
* Let $$a,b,c,d$$ be integers, where $$b\neq 0$$ and $$d\neq 0$$
* Let $$r=\frac ab$$, $$s=\frac cd$$
* By substitution, $$\frac{\frac ab +\frac cd}{2}=\frac{\frac{ad}{bd} +\frac{cb}{bd}}{2}=\frac{\frac{ad+cb}{bd}\cdot\frac 12}{2\cdot\frac 12}=\frac{ad+cb}{2bd}$$
* let $$p=ad+cb$$ where $$p$$ is an integer, $$k=2bd$$ where $$k$$ is an integer, $$\frac pk$$
* $$\therefore\frac rs$$ is rational

Prove: If $$m$$ is any even integer and $$n$$ is any odd integer, then $$m^2+3n$$ is odd.
* $$m=2k$$ by definition of even integers, $$n=2k+1$$ by definition of odd integers
$$(2k)^2+3(2k+1)\\=4k^2+6k+3\\=4k^2+6k+2+1\\=2(2k^2+3k+1)+1$$
* Let $$p=2k^2+3k+1$$, $$2p+1$$ is odd

Prove: If $$a$$ is any odd integer, then $$a^2+a$$ is even.
* $$a=2k$$ by definition of even integers
$$(2k+1)^2+(2k+1)\\=4k^2+4k+1+2k+1\\=4k^2+6k+2\\=2(2k^2+3k+1)$$
* Let $$p=2k^2+3k+1$$, $$2p$$ is even

# Biconditional Proofs
### Biconditional Statement
* $$p\leftrightarrow q$$ which stands for $$p$$ *iff* $$q$$
* The biconditional statement is true when both $$p$$ and $$q$$ have the same truth values and false if they are different
* $$p$$ is necessary and sufficient for $$q$$
* It is logically equivalent to $$(p\to q)\land(q\to p)$$

$$A-B=\emptyset$$ *iff* $$A\subseteq B$$
* Suppose $$A-B=\emptyset$$, $$x\in A$$, $$x\notin\emptyset$$
* $$x\notin A-B$$, $$x\notin A$$ or $$x\in B$$
* $$x\in A$$ and $$x\in B$$, $$\therefore A\subseteq B$$

* Suppose $$A\subseteq B$$, $$x\in A-B$$
* $$x\in A$$ and $$x\notin B$$
* $$x\in B$$ by definition of subset, $$\therefore A-B=\emptyset$$

# Mathematical Induction
### Proof by Induction
* Used to verify a given theorem.
* Proving elements in a sequence.
* Prove that the base case is true.
* Prove if the theorem holds for $$k$$, then it also holds for $$k+1$$.

Theorem: $$n\ge 1,\sum\limits^n_{j=1}j=\frac{n(n+1)}{2}$$
* Base Case $$n=1$$: $$\sum\limits^1_{j=1}j=\frac{1(1+1)}{2}=\frac 22,1=1$$
* For any integer $$k>1$$: $$\sum\limits^k_{j=1}j=\frac{k(k+1)}{2}$$
* Prove $$k+1$$ is also true: $$\sum\limits^{k+1}_{j=1}j=\frac{(k+1)(k+1+1)}{2}$$\\
$$\sum\limits^k_{j=1}j+k+1=\frac{k(k+1)}{2}+\frac{2(k+1)}{2}=\frac{(k+1)(k+2)}{2}$$, $$\therefore\sum\limits^n_{j=1}j=\frac{n(n+1)}{2},n\ge 1$$

Theorem: $$n\ge 4,2^n\ge 3n$$
* Base Case $$n=4$$: $$2^4\ge 3\cdot4,16\ge 12$$
* For any integer $$k>4$$: $$2^k\ge 3k$$
* Prove $$k+1$$ is also true: $$2^{k+1}\ge 3(k+1)$$\\
$$2^k\cdot 2\ge 3k\cdot 2=3k+3k\ge 3k+3,\therefore 2^n\ge 3n,n\ge 4$$