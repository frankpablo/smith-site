---
layout: default
title: Helpful-Links
parent: CSC250
grand_parent: Teaching
nav_order: 40
#permalink: /docs/teaching/csc110/
---  



* * *

  

A Primer on Induction
---------------------

Induction is an approach to proving a statement about a pattern $P$ or law involving an infinite number of cases  
(one for some input numner of elements): $ P(0), P(1), \dots , P(k), P(k+1), \dots $  
This is done in three steps:  
  

1.  The rule works for a base case, usually $ P(0) $, or $ P(1) $
2.  Asume the rule is valid for some intermediate case $ P(k)$
3.  Prove it works for the next case: $ P(k+1) $

**Example**  

Prove that $1+2+3 \dots + n = \frac{n(n+1)}{2}$ 


1.  Base case $n=1$: $ 1 = \frac{k(k+1)}{2} = \frac{1(1+1)}{2} = \frac{(2)}{2} =1 \qquad \checkmark$
2.  Asume this is true for some $n=k$: $ 1+2+\dots+k = \frac{k(k+1)}{2} \qquad \checkmark$ (OK, sure)
3.  Inductive step $\rightarrow $ show that if step (2) holds, then it holds for $n=k+1$:  
    $$ \begin{alignat}{2} \text{if } 1+2+\dots+k &= \frac{k(k+1)}{2}\text{, then} \\ 1+2+\dots+k+(k+1) &= \frac{k(k+1)}{2} + (k+1) \\ &= \frac{k(k+1) + 2(k+1)}{2}\\ &= \frac{(k+1)(k+2)}{2}\\ &= \frac{(k+1)((k+1)+1)}{2} \qquad \square \end{alignat} $$

  
  
Read the following [Guide to Induction](http://web.stanford.edu/class/archive/cs/cs103/cs103.1164/handouts/240%20Guide%20to%20Induction.pdf) for a deeper dive into the steps.




Universal Turing Machines and the Halting Problem
---------------------


<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSYXztF55L4nMmcZk7tlXEyWcsO3I71P9mhJGT7eD1hFW_74hBVCr7AbOsPgyIsN5f-Da57KfJyrkpz/embed?start=false&loop=false&delayms=60000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>


