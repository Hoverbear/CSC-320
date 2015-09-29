---
title: CSC 320 A1
author: Andrew Hobden (V00788452)
---

## Question 1

The problem can be described as similarly as:

$$ D = \{ \omega \in (a,b)^* | \omega \text{ contains an odd number of } b \text{ then an even number of } a\} $$

Or:

$$ D_1 = \{ \omega \in (a,b)^* | \omega \text{ contains an even number of } a \} $$
$$ D_2 = \{ \omega \in (a,b)^* | \omega \text{ contains an odd number of } b \} $$
$$ D_3 = \{ \omega \in (a,b)^* | \omega \text{ does not contain the substring } ab \} $$
$$ D = D_1 \cup D_2 \cup   D_3 $$

Thus the DFA is:

![](img/1-dfa.png)\

And the Regular Expression is:

$$b(bb)*(aa)*$$

## Question 2

### Q2.A DFA for $L_1$:

![](img/2-l1.png)\


### Q2.B DFA for $L_2$:

![](img/2-l2.png)\


### Q2.C DFA for $L_1 \cup L_2$:

|       | a     | b     |
|-------|-------|-------|
| (0,A) | (1,B) | (0,A) |
| (0,B) | (1,C) | (0,B) |
| (0,C) | (1,D) | (0,C) |
| (0,D) | (1,D) | (0,D) |
|-------|-------|-------|
| (1,A) | (2,B) | (1,A) |
| (1,B) | (2,C) | (1,B) |
| (1,C) | (2,D) | (1,C) |
| (1,D) | (2,D) | (1,D) |
|-------|-------|-------|
| (2,A) | (2,B) | (2,A) |
| (2,B) | (2,C) | (2,B) |
| (2,C) | (2,D) | (2,C) |
| (2,D) | (2,D) | (2,D) |

![](img/2-l3.png)\


Which simplifies roughly to:

![](img/2-l4.png)\


## Question 3

|         | a       | b           |
|:-------:|:-------:|:------------|
| {1,2}   | {1,2,3} | $\emptyset$ |
| {1,2,3} | {1,2,3} | {2,3}       |
| {2,3}   | {1,2}   | {2,3}       |
| $\emptyset$ | $\emptyset$ | $\emptyset$ |

![](img/3-dfa.png)\


## Question 4

![](img/4-nfa.png)\


## Question 5

This DFA can be described as:

$$ D = \{ \omega \in (a,b)^* | \omega \text{ contains an odd number of } b \} $$

Therefore the regular expression is:

$$ b(bb)* $$


## Question 6

**Notes:**

* This question does not describe what $A$ and $B$ are. (Languages, Reg. Expressions, NFAs, DFAs, Alphabets). Assuming they are NFAs.
* This question uses syntax $A/B=$, which was never covered in class.
* This question does not state the desired format of the answer, providing an NFA.

It is possible to construct something that is regular from a pair of regular constructions. Any $\omega x \in A$ would be found by chaining $B$ onto the end of all of $A$'s accept states, since $\omega$ would match on the $A$, and $x$ would match on the $B$.

![](img/6-nfa.png)\


## Question 7

**Notes:**

* The output is not necessarily ordered by the definition of the language, since $a_i \in A$.
* There is a strict $a_i,b_i$ ordering, meaning that $a_d,a_e,a_f,b_d,b_e,b_f$ may not occur, for example.
* The output will be of even length (because of above).

It is possible to construct a *shuffle* on a pair of regular languages. Any $a_i$ could match on $A$, and be followed by a $b_i$ matching on $B$.

![](img/7-nfa.png)\
