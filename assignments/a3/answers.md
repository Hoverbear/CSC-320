---
title: CSC 320 A3
author: Andrew Hobden (V00788452)
---

## Question 1

![](img/q1.png)\


## Question 2

The PDA pushes some $n$ zeros onto the stack as it scans zeros, then pops off $n$ zeros as it scans ones.

$\therefore$ the CFG reads $0^n1^n$ and appears as so:

$$ S \rightarrow 0S1 $$

## Question 3

<!-- TODO -->

## Question 4

### Q4.a

Concatenation is closed because two Turing Machines can always be linked together. Consider Turing Machine $A$ which, when complete, transitions to Turing Machine $B$ by marking a $\$$ onto the tape to notate the new "start" of the tape for the second Turing Machine.

### Q4.b

Intersection is closed because we can use the "$k$-tape Machine" construct as discussed in class with two tapes, $L$ and $R$, representing the two Turing machines. Then using the appropriate machine's rules on the appropriate machines tape as the input is read. If both accept then the intersection accepts.

### Q4.c

The complement is closed because we can have Turing Machine $A$ with states $Q$. For each $q_{accept} \in Q$ we can attach a link to a new $q\prime_{reject}$ and attach all $q_{reject} \in Q$ to a new $q\prime_{accept}$.

## Question 5
