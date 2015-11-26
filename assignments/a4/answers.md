---
title: CSC 320 A4
author: Andrew Hobden (V00788452)
---

## Question 1

Proving:

$$ L = \{ <M> | M \text{ when started on the blank tape, eventually writes a \$ somewhere on the tape} \} $$

is undecidable.

Noting:

* $A_{TM} = \{ <M,\omega> | \text{ M is a TM and M accepts } \omega \}$
* In class we showed that $A_{TM}$ is undecidable, but recognizable.

### Proving by Contradiction

Presume $L$ is decidable.

We define $L$ as a construction that takes a TM $M$, simulates it on a blank tape, and checks it's simulated tape for a $\$$ at each step until finds one, or halts. From the original definition there are no restrictions on $M$ being recognizable or decidable.

Now, provide $L$ with an undecidable Turing Machine such as $A_{TM}$. $A_{TM}$ may not halt, and may never write a $\$$, therefore $L$ must continue to simulate the input.

This is contradictory since it would mean that $L$ would not halt in some cases, therefore $L$ cannot be decidable.

## Question 2

Showing that

$$L = \{ <M, j> | \text{ M halts on all inputs with less than } j \text{ 1's} \}$$

is a reduction of $HALT_{TM} = \{ <M, \omega> | \text{ M is a TM which halts on } \omega  \}$.

$$ HALT_{TM} \text{ is undecidable } \rightarrow L \text{ is decidable} $$

$$ L \leq_m HALT_{TM} $$

### Proof

Let $M$ be a TM which decides $HALT_{TM}$. We construct a TM $N$ which decides on $L$ using $M$ as a subroutine.

$$ <M, \omega> \in HALT_{TM} \iff <N,j> \in L $$

For any $N$ where $<N,1> \in L$:

$$ N \text{ halts on all inputs with no 1's} $$

On an all zero string $N$ erases the tape, writes down $\omega$ and simulates $M(\omega)$.

$$ <M, \omega> \in HALT_{TM} \iff <N,j> \in L \iff M \text{ halts on any all zero string } $$

## Question 3

$$ E_{TM} = \{ <M> | \text{ M is a TM and } L(M)= \emptyset \} $$

In class we showed that $E_{TM}$ is undecidable.

Showing $\bar E_{TM}$ is recognizable.

We create a construct that non-deterministically starts running the input $M$ in parallel. If any of the paths in $\bar E_{TM}$ accept, $\bar E_{TM}$ can reject. If one or more fails to halt that is fine since we are seeking recognizability.

## Question 4

Showing

$$ \{ <M_1,M_2> | L(M_1) \cap L(M_2) = \emptyset \} $$

is not recognizable.

Using $E_{TM} = \{ <M> | \text{ M is a TM and } L=(M)=\emptyset \}$.

We know that $E_{TM}$ is not decidable and that $\bar E_{TM}$ is recognizable (Q3) therefore this implies that $E_{TM}$ is indeed **not** recognizable. (Since if it was then $E_{TM}$ would be decidable.)

Since running $\{ <M_1,M_2> | L(M_1) \cap L(M_2) = \emptyset \}$ with both $M_1$ and $M_2$ as the same TM as both inputs would effectively be running $E_{TM}$ we can deduce that $\{ <M_1,M_2> | L(M_1) \cap L(M_2) = \emptyset \}$ is not recognizable.

## Question 5

Proving that

$$ T = \{ <M> | M \text{ is a reversible TM } \} $$

Is undecidable.

$M$ is not necessarily decidable or recognizable.

### Proving by Contradiction

Presume $T$ is decidable.

Provide $T$ with an $M$ which is not decidable. Since $T$ is calculating the reverse of strings in $M$ and $M$ may never halt on valid strings, $T$ may not halt either.

This is a contradiction, since we presumed $T$ was decidable.
