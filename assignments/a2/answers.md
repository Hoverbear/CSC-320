---
title: CSC 320 A2
author: Andrew Hobden (V00788452)
---

## Question 1

### Q1.a

$$ \text{Non-accept: } \{ q_0, q_3, q_4 \} \text{ Accept: } \{ q_1, q_2, q_5 \} $$
$$ \text{Non-accept: } \{ q_0 \} \{ q_3, q_4 \} \text{ Accept: } \{ q_1, q_2, q_5 \} $$
$$ \text{Non-accept: } \{ q_0 \} \{ q_3, q_4 \} \text{ Accept: } \{ q_1, q_2 \} \{ q_5 \} $$

![](img/q1-min.png)\


### Q1.b

The language recognized by this automataton is:

$$ \{ \omega \in \{0,1\}^* : \omega \text{ is of length 1 or } \omega \text{ is of length 3 or more. } \} $$

## Question 2

### Q2.a

$$ \{ 0^n1^m0^n | m,n \geq 0 \} $$

$$ \omega = 0^p1^m0^p $$

$$ x=0^e, y=0^f, z=1^m0^p, e+f=p $$

$$ \omega = xy^0z = 0^{p-f} (0^f)^0 1^m 0^p = 0^{p-f} 1^m 0^p \notin L $$

Since the string does not contain enough $0$'s at the start, this is not regular.

### Q2.b

### Q2.c

## Question 3

### Q3.a

### Q3.b

### Q3.c

## Question 4


## Question 5

## Question 6

## Question 7

## Question 8

## Question 9
