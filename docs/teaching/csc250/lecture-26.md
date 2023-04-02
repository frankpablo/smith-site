---
layout: default
title: Lecture26
parent: CSC250
grand_parent: Teaching
nav_order: 26
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 26: Reductions and Enumeration
=============================================================


Outline
-------

This class we'll discuss:

* Recap: Reductions

  

* * *


  
  
![](../../../assets/images/csc250/lecture23/Reduc-16.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-17.png){: width=80%}  
(ATM-01 is at least as hard to decide as ATM)  
  
Note that:  

1.  IF a machine $D_{ATM}$ existed, it would receive input $ < M, w > $
2.  IF a machine $D_{ATM-01}$ existed, it would receive input $ < M > $
3.  The order of the proof is:  
    1.  Assume $D_{ATM-01}$ already exists
    2.  We can use it to build another machine that should behave like $D_{ATM}$
    3.  This larger machine, should be able to handle input $ < M, w > $
    4.  You must somehow get a machine with ONLY $ < M > $ as input to handle the input $ < M, w > $
    5.  Note that, as part of the steps, you can build helper machines

  
  
  
  
**Activity 4** \[2 minutes\]:  
In teams, write a Machine that uses $D_{ATM-01}$ to perform the work of $D_{ATM}$ (Wait; then Click)  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-18a.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-18b.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-18c.png){: width=80%}  
  

  
  
![](../../../assets/images/csc250/lecture23/Reduc-19.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-20.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-21a.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-21b.png){: width=80%}  
  
This can be written like this:  
  
Assume EMPTY-TM is decidable, and so there exists some $D_{EMPTY-TM}$ that decides, for any input $< M >$, whether $L (M) $ is empty.  
  
We'll design the Machine $D_{ATM} $ as follows:  
  
$$ \begin{align*} &D_{ATM}:\\ & \text{ On input $ < M, w > $ }:\\ & \text{ Create (but don't run) $HELPER_{M,w}$ such that}\\ & \quad \text{ On input $ < X > $ }:\\ & \quad \quad \text{ Ignore $ < X > $ }\\ & \quad \quad \text{ Run $M$ on $w$ ADWID}\\ & \text{ Now Run $D_{EMPTY-TM}$ on $HELPER_{M,w}$}\\ & \text{ If $D_{EMPTY-TM}$ rejects, invert the result and our machine ACCEPTS}\\ & \text{ If $D_{HALT}$ accepts, , invert the result and our machine REJECTS}\\ \end{align*} $$  
  
As we saw above, the ONLY way $D_{EMPTY-TM}$ Rejects is if $HELPER_{M,W}$ Accepts, which happens ONLY when $M$ accepts $w$.  
  
This means we CAN make $D_{ATM}$ as long as $D_{EMPTY-TM}$ exists.  
  
However, $D_{ATM}$ doesn't exist...which means $D_{EMPTY-TM}$ CANNOT EXIST EITHER.  
  
  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-22.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-23.png){: width=80%}  
  
  
  
![](../../../assets/images/csc250/lecture23/Reduc-24.png){: width=80%}  
  
  
  
This will lead us to a new way of looking at Recognizers: Enumeration.



# Enumeration  
  
  
  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-28.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-29.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-30.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-31.png){: width="80%"}  
  

**Activity 3** \[2 minutes\] In groups, come up with an algorithm to enumerate $\\Sigma^*$?:  

  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-32.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-33.png){: width="80%"}  
  

**Activity 4** \[2 minutes\] In groups,  
How would you prove that, IF you can enumerate a Language, then that language is Recognizable.  
(Wait; then Click)  
  
  
  
Assume L is enumerable, i.e. there exists some machine E_L that can print out all of Ls words.  
Build a machine R_L that uses E_L to print them out one at a time, and compares each one with the input.  
As soon as they match, accept.  
  
This machine accepts only words that are in L, and if a word is in L we’re guaranteed to reach it at some point (though it might take awhile).  
Thus, it recognizes L. QED.  

  
  
![](../../../assets/images/csc250/lecture24/Enum-34.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-35.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture24/Enum-36.png){: width="80%"}