---
layout: post
title:  "Effective Arguments and Defensible Decisions"
date:   2018-01-02
tags:  [discrete mathematics]
---
# Valid reasoning an inference
### Complex statements
* Stick prices are increasing but interest rates are steady. $$s\land i$$
* '$$p$$ but $$q$$' ---> $$p\land q$$: "It's still light outside but the moon is shining" = "It's still light outside and the moon is shining"
* 'neither $$q$$ nor $$q$$' ---> $$\lnot p\land \lnot q$$: "It's neither red nor green" = "It's not red and it is not green"

# Truth Tables
$$\begin{array}{c|c}
\hline
p &\lnot p\\
\hline
T&F\\
F&T\\
\hline
\end{array}$$\\
$$\begin{array}{c|c|c|c}
\hline
p & q & p\lor q&p\land q\\
\hline
T&T&T&T\\
T&F&T&F\\
F&T&T&F\\
F&F&F&F\\
\hline
\end{array}$$\\
$$\begin{array}{c|c|c|c|c|c}
\hline
p & q & r & p\lor q&q\land r&(p\land q)\land(q\lor r)\\
\hline
T&T&T&T&T&T\\
T&T&F&T&F&T\\
T&F&T&T&F&T\\
T&F&F&T&F&T\\
F&T&T&T&T&T\\
F&T&F&T&F&T\\
F&F&T&F&F&F\\
F&F&F&F&F&F\\
\hline
\end{array}$$
# Identify and evaluate predicates
### Predicates
$$P(x)$$: A logical statement whose truth value is a function of one or more variables is called a predicate.

$$P(x)$$: $$x$$ is an even number. $$P(4)$$: T. $$P(3)$$: F.

$$P(x,y)$$: $$\sqrt{x}=y$$. $$P(36,6)$$: T.
### Quantifiers
* $$\forall$$ --- A Universal quantifier represents "for all"
* $$\exists$$ --- An Existential quantifier represents "there exists"

### Universal Quantifier
* All students completed their homework. $$\forall s$$, $$h$$
* Every student has a driver's license. $$\forall s$$, $$d$$

### Universal Quantifier
* There is a student who completed the homework. $$\exists s$$, $$h$$
* There is a student who has his driver's license. $$\exists s$$, $$d$$

### De Morgan's Law
$$\lnot\forall xP(x)\equiv\exists x,\lnot P(x)$$\\
$$\lnot\exists xP(x)\equiv\forall x,\lnot P(x)$$

### Negation
To negate a universal statement, it changes to an existential statement.\\
$$\lnot$$(Every student has a draiver's license). $$\exists s$$, $$\lnot d$$

To negate a existential statement, it changes to an universal statement.\\
$$\lnot$$(There is a student who completed his homework). $$\forall s$$, $$\lnot h$$
### Method of Exhaustion
$$U=\{1,3,5,7,9\}$$
* $$\forall x,x\;is\;odd$$: T
* $$\forall x,x+3\ge 7$$: F
* $$\forall x,x\;is\;prime$$: F

$$U=\{1,2,5,8,9\}$$
* $$\exists x,x\;is\;odd$$: T
* $$\exists x,x+3\ge 13$$: F

# Conditional propositions
### Conditional Statements
**Logical Operators**
* A compound proposition is created by connecting individual propositions using logical operators.
* AND is denoted using $$\land$$ symbol, such as $$p\land q$$. The truth value of a compound proposition using the AND operator is only true when both propositions are true.
* OR is denoted using $$\lor$$ symbol, such as $$p\lor q$$. The truth value of a compound proposition using the OR operator is always true except when $$p$$ and $$q$$ are both false.
* If a statement has logical operators, the order of precedence is: $$\lnot (not),\land (and),\lor (or)$$

### Conditional propositions
A conditional statement is read as 'if this, then that'.
* If there is an accident on the highway, then I will be late for work.
* $$p\to q$$ (if $$p$$, then $$q$$). $$p$$ represents the premises and $$q$$ is the conclusion.

### Truth Table
$$\begin{array}{c|c|c}
\hline
p & q & p\to q\\
\hline
T&T&T\\
T&F&F\\
F&T&T\\
F&F&T\\
\hline
\end{array}$$\\
If dogs meow, then cats can fly.
### Contrapositive
Logically equivalent to the original statement. $$p\to q\equiv\lnot q\to\lnot p$$
### Inverse
Not logically equivalent to the original statement. $$p\to q$$, $$\lnot p\to\lnot q$$
### Converse
Not logically equivalent to the original statement. $$p\to q$$, $$q\to p$$
### Negation
$$p\to q\equiv \lnot p\lor q$$\\
$$\lnot(p\to q)\equiv \lnot (p\lor q)\equiv p\land\lnot q$$\\
* $$\lnot$$(If you work hard, then you will succeed).
* $$\lnot$$(You do not work hard or you succeed).
* You work hard and you do not succeed.

# Valid Arguments
### Argument Definition
* A sequence of propositions, called hypotheses.
* Followed by a final proposition, called the conclusion.
* All porpositions are either true or false.
* An argument is either valid to invalid.

### Argument Validity
An argument is valid if the conclusion is true whenever the hypotheses are all true. Otherwise it is invalid.
### Argument Form
An argument contains one or more hypotheses and one conclusion, usually written as: $$p_1,p_2,p_3,...,p_n$$

Today is Monday\\
If today is Monday, then I will have a salad for lunch.\\
Therefore, I will have a salad for lunch

$$p$$ = Today is Monday, $$q$$ = I will have salad for lunch

$$p\\ p\to q\\ \therefore q$$\\
$$\begin{array}{c|c|c}
\hline
p & p\to q& q\\
\hline
T&T&T\\
T&F&F\\
F&T&T\\
F&T&F\\
\hline
\end{array}$$

$$p\to q\\ q\\ \therefore p$$\\
$$\begin{array}{c|c|c|c|c}
\hline
p&q & p\to q&q& p\\
\hline
T&T&T&T&T\\
T&F&F&F&T\\
F&T&T&T&F\\
F&F&T&F&F\\
\hline
\end{array}$$
# Rules of Inference
* Label each predicate in the original argument.
* Rewrite the problem using only the variables and logical connectors ($$\lor,\land,\to,\lnot,etc$$).

If it rains, Cy will be sick. $$p\to q$$\\
Cy is not sick. $$\lnot q$$\\
Therefore, it did not rain. $$\therefore \lnot p$$
### Modus Ponens
$$p\to q\\ p\\ \therefore q$$
### Modus Tollens
$$p\to q\\ \lnot q\\ \therefore\lnot p$$
### Addition
$$p\\ \therefore p\lor q$$
### Simplification
$$p\lor q\\\therefore p$$
### Conjunction
$$p\\q\\\therefore p\land q$$
### Hypothetical Syllogism
$$p\to q\\q\to r\\\therefore p\to r$$

If you have a current password, then you can log on to the network. $$p\to q$$\\
You have a current password. $$p$$\\
Therefore, You can log on to the network. $$\therefore q$$
### Converse Error
$$p\to q\\q\\\therefore p$$

If Joe has the flu, then Joe has a fever. $$p\to q$$\\
Joe has a fever. $$q$$\\
Therefore, Joe has the flu. $$\therefore p$$
### Inverse Error
$$p\to q\\\lnot p\\\therefore\lnot q$$

# Prove Logical Equivalence
### Logically Equivalent
$$p$$: Dogs bark and cats meow.\\
$$q$$: The sky is blue and the grass is green.\\
$$p\equiv q$$
* Truth Tables are used to determine logical equivalence
* By using the canonical form, we can easily determine if the conclusions match without reordering the rows.

$$\lnot(p\lor q)\equiv\lnot p\land\lnot q$$\\
$$\begin{array}{c|c|c|c|c|c|c}
\hline
p & q & p\lor q&\lnot(q\lor q)&\lnot p&\lnot q&\lnot p\land\lnot q\\
\hline
T&T&T&F&F&F&F\\
T&F&T&F&F&T&F\\
F&T&T&F&T&F&F\\
F&F&F&T&T&T&T\\
\hline
\end{array}$$
### De Morgan's Law
$$\lnot (p\lor q)\equiv\lnot p\land\lnot q$$\\
$$\lnot (p\land q)\equiv\lnot p\lor\lnot q$$
### Tautology
A compound proposition is a **tautology** if the proposition is **always true** regardless of the truth value of the individual proposition that occur in it. A simple example is $$p\lor\lnot p$$, this is always true.
### Contradiction
A compound proposition is a **contradiction** if the proposition is **always false** regardless of the truth value of the individual propositions that occur in it. A simple example is $$p\land\lnot p$$, this is always false.
### Laws of Propositional Logic

|Idempotent laws:|$$p\lor p\equiv p$$|$$p\land p\equiv p$$|
|Associative laws:|$$(p\lor q)\lor r\equiv p\lor(q\lor r)$$|$$(p\land q)\land r\equiv p\land(q\land r)$$|
|Commutative laws:|$$p\lor q\equiv q\lor p$$|$$p\land q\equiv q\land p$$|
|Distributive laws:|$$p\lor(q\land r)\equiv(p\lor q)\land(p\lor r)$$|$$p\land(q\lor r)\equiv(p\land q)\lor(p\land r)$$|
|Identity laws:|$$p\lor F\equiv p$$<br>$$p\lor T\equiv T$$|$$p\land F\equiv F$$<br>$$p\land T\equiv p$$|
|Double negation laws:|$$\lnot\lnot p\equiv p$$|
|Complement laws:|$$p\lor \lnot p\equiv T$$<br>$$\lnot T\equiv F$$|$$p\land \lnot p\equiv F$$<br>$$\lnot F\equiv T$$|
|De Morgan's laws:|$$\lnot (p\lor q)\equiv\lnot p\land\lnot q$$|$$\lnot (p\land q)\equiv\lnot p\lor\lnot q$$|
|Absorption laws:|$$p\lor(p\land q)\equiv p$$|$$p\land(p\lor q)\equiv p$$|
|Conditional identities:|$$p\to q\equiv\lnot p\lor q$$|$$p\leftrightarrow q\equiv(p\to q)\land(q\to p)$$|

$$\lnot(\lnot p\land q)\land(p\lor q)\equiv p$$\\
$$\equiv(\lnot\lnot p)\lor\lnot q)\land(p\lor q)$$ <--- De morgan's Law\\
$$\equiv(p\lor\lnot q)\land(p\lor q)$$ <--- Negation Law\\
$$\equiv p\lor(\lnot q\land q)$$ <--- Distributive Law\\
$$\equiv p\lor(q\land\lnot q)$$ <--- Commutative Law, Negation Law\\
$$\equiv p\lor c$$ <--- Identity Law\\
$$\equiv p$$