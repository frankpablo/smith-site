---
layout: default
title: Lecture29
parent: CSC250
grand_parent: Teaching
nav_order: 29
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 29: Mapping Reducibility
=============================================================


Outline
-------

This class we'll discuss:

* Recap: Enumeration and Recognizers
* Mapping reducibility

  

* * *


  
![](../../../assets/images/csc250/lecture24/Enum-36.png){: width="80%"}{: width="80%"}




# Mapping Reducibility



* * *

  

Recap: Reductions
-----------------

  
  
<!-- ![](../../../assets/images/csc250/lecture25/MAP-01.png){: width="80%"}   -->
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-02.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-03.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-04.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-05.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-06.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-07.png){: width="80%"}  
  

**Activity 1** \[2 minutes\] How would you do this reduction?: 

<br><br> 
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-08.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-09.png){: width="80%"}  
  
  
  

  
  
![](../../../assets/images/csc250/lecture25/MAP-10.png){: width="80%"}  
  

**Activity 2** \[2 minutes\] How would you do this reduction?: (Wait; then Click)  
  
  
  
Assume EQTM is decidable, and so there exists some $D_{EQTM}$ that decides, for any input $< M\_1, M\_2>$, whether $M\_1$ Accepts the same language as $M\_2$.  
  
We'll design the Machine $D_{EmptyTM} $ as follows:  
  
$$ \begin{align*} &D_{EmptyTM}:\\ & \text{ On input $ < M > $ }:\\ & \text{ Create (but don't run) $HELPER_{\emptyset}$ such that}\\ & \quad \text{ On input $ < X > $ }:\\ & \quad \quad \text{ Ignore $ < X > $ }\\ & \quad \quad \text{ Reject}\\ & \text{ Now Run $D_{EQTM}$ on input $ < M, HELPER_{\emptyset} $ ADWID}\\ & \text{ If $D_{EQTM}$ accepts, it is only because M accepts no words so our machine ACCEPTS}\\ & \text{ If $D_{EQTM}$ rejects, , it is only because M accepts some w so our machine REJECTS}\\ \end{align*} $$  
  

  
  
![](../../../assets/images/csc250/lecture25/MAP-11.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-12.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-13.png){: width="80%"}  
  

**Activity 3** \[2 minutes\] How would you do this reduction?: (Wait; then Click)  
  
  
  
* Reject if: $D_{EMPTY}$ accepts $M_{M,w}$
* Accept if: $D_{EMPTY}$ rejects $M_{M,w}$

  
  
![](../../../assets/images/csc250/lecture25/MAP-14.png){: width="80%"}  
  
  
  
<!-- ![](../../../assets/images/csc250/lecture25/MAP-14b.png){: width="80%"}   -->
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-15.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-16.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-17.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-18.png){: width="80%"}  
  
  
  
The Emptiness Problem  
  
* Theorem: $\overline{EMPTY-TM}$ is recognizable
* Theorem: $EMPTY-TM$ is undecidable
* Corollary: $EMPTY-TM$is **unrecognizable**
* Proof: If $\overline{EMPTY-TM}$ and $EMPTY-TM$ recognizable,
* that would imply $EMPTY-TM$ is decidable  
  
  
  
This means our Turing Reduction can't catch the ordering between languages... nor can we really use it to establish, from its results a clear idea of the class of languages they belong to. 
  
Issue with EMPTY ≤ ¬EMPTY is that the “Domain” of one is complement of the “Domain” of the other!  
  
  
However, we've actually seen a STRONGER type of reduction  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-19.png){: width="80%"}  
  
Here, The “Domain” of EMPTY corresponds to the “Domain” of EQ!  
  
  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-20.png){: width="80%"}  
  
We could rewrite this as a simple conversion from any word in EmptyTM to a word in EQ\_TM (and similarly a word not in EmptyTM to a word not in EQ\_TM).  
  
We call this a mapping reduction, and denote it $ \leq_m$

  

* * *

  

Mapping Reductions
------------------

  
  
![](../../../assets/images/csc250/lecture25/MAP-21.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-22.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-23.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-24.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-25.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-26.png){: width="80%"}  
  
They’re a way for us to relate problems to one another  
If A reduces to B and B is easy => A is easy too  
More common: if A reduces to be and A is hard => B is hard too  
  
We started with ATM (which we proved was undecidable using a big ugly contradiction )  
Reduced ATM to HALT (ATM ≤ HALT): we showed that if we had a decider HALT, we could use that to decide ATM (so that means HALT must also be undecidable)  
  
We did the same thing with ATM-01  
And EmptyTM  
Later, we also showed that if we had a decider for HALT, we could use that to decide EmptyTM  
And that if we had a decider for EQ_TM, we could yet again decide EmptyTM (mapping)  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-27.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-28.png){: width="80%"}  
  


<!-- 
  Sipser
ATM = {⟨M,w⟩| M is a TM and M accepts w}. P202, 207
THE DIAGONALIZATION METHOD P202  
ATM is not Turing-recognizable. P210
HALTTM ={⟨M,w⟩|MisaTMandMhaltsoninputw}. P216
ETM ={⟨M⟩|M isaTMandL(M)=∅}. P217
EQTM = {⟨M1,M2⟩| M1 and M2 are TMs and L(M1) = L(M2)}. P220
f: Σ∗−→Σ∗ is a computable function P234
EQTM is neither Turing-recognizable nor co-Turing-recognizable. P238
TURING REDUCIBILITY P261 
-->


Mapping Reducibility and Reductions Conclussion
================================================================== 


* * *

  

A Reduction Issuue
------------------

  
  
The Emptiness Problem

* Theorem: $\overline{EMPTY-TM}$ is recognizable
* Theorem: $EMPTY-TM$ is undecidable
* Corollary: $EMPTY-TM$is **unrecognizable**
* Proof: If $\overline{EMPTY-TM}$ and $EMPTY-TM$ recognizable,
* that would imply $EMPTY-TM$ is decidable
  
  
  
  
This means our Turing Reduction Can't catch if the fact that we're reducing outside the same class of languages  
  
Issue with EMPTY ≤ ¬EMPTY is that the “Domain” of one is complement of the “Domain” of the other!  
  
  
  
However, we've actually seen a STRONGER type of reduction  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-19.png){: width="80%"}  
  
Here, The “Domain” of EMPTY corresponds to the “Domain” of EQ!  
  
  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-20.png){: width="80%"}  
  
We could rewrite this as a simple conversion:  
from any word in EmptyTM to a word in EQ_TM (and similarly a word not in EmptyTM to a word not in EQ_TM).  
  
We call this a **mapping reduction**, and denote it $ \leq_m$

  

* * *

  

Mapping Reductions
------------------

  
  
![](../../../assets/images/csc250/lecture25/MAP-21.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-22.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-23.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-24.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-25.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-26.png){: width="80%"}  
  
They’re a way for us to relate problems to one another  
  
If A reduces to B and B is easy => A is easy too  
More common: if A reduces to be and A is hard => B is hard too  
  
We started with ATM (which we proved was undecidable using a big ugly contradiction )  
Reduced ATM to HALT (ATM ≤ HALT): we showed that if we had a decider HALT, we could use that to decide ATM  
(so that means HALT must also be undecidable)  
  
We did the same thing with ATM-01  
And EmptyTM  
  
Later, we also showed that if we had a decider for HALT, we could use that to decide EmptyTM  
And that if we had a decider for EQ_TM, we could yet again decide EmptyTM (mapping)  
  
  
  
  
  
  
  
  
  
![](../../../assets/images/csc250/lecture25/MAP-27.png){: width="80%"}  
  

**Activity 1** \[2 minutes\] How would you do this reduction?: (Wait; then Click)  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
  
$$HALT \leq_m SOMETIMES-HALTS$$ 
  
We want to show that we can take any input and transform it such that:  
if the input was a word in HALT $(< M,w>)$, the output is a word $(< M>)$ in SOMETIMES-HALTS  
  
if the input was NOT a word in HALT, the output is NOT a word in SOMETIMES-HALTS  
  
This suggests that we want to build a helper machine that “amplifies” the behavior of M on w:  
  
$$ \begin{align*} &D_{HALT}:\\ & \text{ On input $ < M,w > $ }:\\ & \text{ Create (but don't run) $HELPER_{M,w}$ such that}\\ & \quad \text{ On input $ < X > $ }:\\ & \quad \quad \text{ Ignore $ < X > $ }\\ & \quad \quad \text{ Run M on w ADWID}\\ & \text{ Now Run $D_{S-H}$ on input $ < HELPER_{M,w} > $ ADWID}\\ \end{align*} $$  
  
The only way the helper halts is if M halts on w (if this is the case, it halts on EVERY input). Otherwise, it loops.  
In other words, if $< M,w>$ was in HALT, then the helper will be in SOMETIMES-HALTS,  
and if $< M,w>$ is NOT in HALT, then the helper won’t be in SOMETIMES-HALT.  
  
Thus, we’ve defined a mapping that from problems in HALT to problems in SOMETIMES-HALTS, proving that SOMETIMES-HALTS is at least as difficult as HAL, and so must be undecidable.  
      </p>
    </details>
  </span>
</div> 

<br><br>

  

* * *


