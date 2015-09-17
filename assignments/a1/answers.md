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
$$ D = D_1 \cap D_2 \cap D_3 $$

Thus the DFA is:

![](img/1-dfa.png)\

And the Regular Expression is:

```
// TODO
```

## Question 2

### Q2.A
DFA for $L_1$:

![](img/2-l1.png)\


### Q2.B

DFA for $L_2$:

![](img/2-l2.png)\

### Q2.C

DFA for $L_1 \cup L_2$:

```
// TODO
```
