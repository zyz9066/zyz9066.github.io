---
layout: post
title:  "Advanced Discrete Math Topics"
date:   2018-01-03
tags:  [discrete mathematics]
---
# Graph Theory
### Definition
In graph theory, mathematical structures are used to model pairwise relations between objects.
* A graph in this context is made up of vertices or *nodes* and *edges* that connect them.
* A graph may be *undirected*.
* Graphs are one of the prime objects of study in discrete mathematics.

### Trees
Trees: free tree, rooted tree\\
Tree Terminology
* Root is the base of the tree.
* Trees have parents, children, ancestors, siblings, and descendants.
* Leaves are vertices with no children.
* A tree can also have a subtree.

# Network optimization
### Difinition
Optimization: the process of looking for the best solution, whether this is a shortest path, a minimum spanning tree, or a minimum circuit.
### Prefix Codes
* ASCII and Unicode character sets are examples of fixed length encodings.
* Variable length codes are much more efficient.
* Prefix codes are an example of variable length encoding.

* A textbook has 9,000 instances of the letter a.
* It has instances of the letter z.
* Used a fixed encoding where each letter is 4 bits, it would take up: 9000*4+100*4=36,400 bits of space.
* Instead, let's use a variable length encoding.
* a=1 bit, z=8 bits, 9000*1+100*8=9,800

# Probability
### Definition
Discrete probability theory deal with events that occur in countable sample spaces.
* Observing nature, counting the number of birds.
* Experiments that have well-defined constraints.
* Throwing dice, working with a deck of cards.
* Calculating the probability of events using enumerative combinatorics.

### Tossing Two Die
What are the chances of getting two sixes?
* Identify the power set of two die, $$\mid die1\mid +\mid die2\mid =36$$.
* There is only one combination with two sixes.
* The probability is 1 out of 36 or about 3%.

What are the chances of getting a sum of 7?
* The ordered pairs that add to 7 include: $$\{(1,6),(2,5),(3,4),(4,3),(5,2),(6,1),\}$$
* Therefore, the probability is 6 out of 36 or about 17%.

# Cryptography
Caesar Cipher

|A|B|C|D|E|F|G|H|I|J|K|L|M|N|O|P|Q|R|S|T|U|V|W|X|Y|Z|
|:-:
|X|Y|Z|A|B|C|D|E|F|G|H|I|J|K|L|M|N|O|P|Q|R|S|T|U|V|W|

* Encrypted message: EBIMFPLKQEBTXV
* Decrypted message: HELP IS ON THE WAY