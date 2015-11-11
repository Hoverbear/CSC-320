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

We note $|M| = m$, that is, $M$ has $m$ states.

Assumptions:

* The Turing Machine States are minimal, that is there are no states which are "dead" and never operate.
* Since we are attempting to determine *decidability* we are only seeking to know if $L_{nb}$ will halt on every input. This means we don't actually care about what $M$ does, and do not need it to be decidable.
* No non-determinism.

When $M$ is started on a blank input tape it will make sequential moves according to its defined transitions. Since $L_{nb}$ is satisfied as soon as one non-blank symbol is written we can define $L_{nb}$ to act in these terms:

```
for q in Q_M:
    let a = (Does q replace the currently scanned symbol with another symbol?)
    let b = (Is q reachable from start with only blank transitions?)
    if a AND b:
        accept
    else:
        reject
```

This has a finite running time and both $L_{nb}$ and $\not L_{nb}$ are Turing recognizable.

## Question 6

Assumptions:

* Given the conditions stated regarding $u \prec v$:
    + There is a (possibly infinite) list of (finite) strings.
    + They have a lexicographical ordering.
* $L$ is Turing decidable if $L$ and $\not L$ are Turing recognizable.


We must prove the two parts:

* **If:** If an Enumerator $E$ (which respects $u \prec v$) enumerates $A$, then a Turing Machine $M$ is decidable for $A$.
* **Only-if:** If a Turing Machine $M$ is decidable for language $A$ we can construct an enumerator (which respects $u \prec v$) for $A$.

### Q6. If part

On input $w$:

* Run enumerator $E$ repeatedly until reaching some $e \in E$ where $w \prec e$.
* For each $e$, if $e = w$ **Accept**.

### Q6. Only-If Part

For each possible string in the language:

* For $i$ in $1, 2, 3, ...$:
    + Run $M$ for $i$ steps, if it accepts print it.

If $M$ accepts, it will appear on the list of strings.
