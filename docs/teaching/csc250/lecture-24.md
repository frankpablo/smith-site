---
layout: default
title: Lecture24
parent: CSC250
grand_parent: Teaching
nav_order: 24
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 24: Mapping Reducibility
==============================


Outline
-------

This class we'll discuss:

* Recap: Enumeration and Recognizers
* Mapping reducibility


* * *

A Slideshow:
---------------

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTGco9fya_OQAVynFvj-kja8BLbRUIIrFAB1fo6CqbCAPGyB1_WscyYRc2XnGi2CEds17UtxNv1BaMX/embed?start=false&loop=false&delayms=60000" frameborder="0" width="800" height="629" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

---



GUIDED NOTES (Optional)
=======================



  
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



<!-- 
## Recap: Two contradiction machines:

### Contradiction Machine 1: $M_{X}$ to prove $D_{HALT}$ can't exist:

<br>

Suppose $D_{HALT}$ <b>exists and it always replies with a consistent answer</b>:

  $$ 
  \begin{align*} 
  &M_{HALT}: \\
  & \text{On INPUT $< M, \hat{w} >$} \\
  & \quad \text{ if M HALTS on $\hat{w}$, ACCEPT } \\
  & \quad \text{ if M FLOOPS on $\hat{w}$, REJECT } 
  \end{align*} 
  $$  

If we build the helper machine $M_X$:

  $$ 
  \begin{align*} 
  &M_X: \\
  & On \; INPUT \; < M > \\ 
  & \quad \text{Make } \hat{w} = < M > \color{gray}{ \text{# a copy of the input machine's description} }\\
  & \quad \text{run $M_{HALT} ( < M , \hat{w}>)$}
  \quad \color{gray}{ \text{# run $M_{HALT} ( < M , < M > > )$ } } \\
  & \quad \text{if $M_{HALT}( < M , \hat{w} > )$ returns ACCEPT, FLOOP on purpose } \\
  & \quad \text{if $M_{HALT}( < M , \hat{w} > )$ returns REJECT, ACCEPT } \\
  \end{align*} 
  $$  

And run $M_X$ with input equal to itself, we get:

  $$ 
  \begin{align*} 
  &M_X: \\
  & On \; INPUT \; < M_x > \\
  & \quad \text{run $M_{HALT} ( < M_x , M_x > )$}\\
  & \quad \text{if $M_{HALT}( < M_x ,  M_x > )$ returns ACCEPT, FLOOP on purpose } \\
  & \quad \text{if $M_{HALT}( < M_x ,  M_x > )$ returns REJECT, ACCEPT } \\
  \end{align*} 
  $$ 

This causes an inconsistent response from $D_{HALT}$: a contradiction

therefore, $D_{HALT}$ can't exist.

<br>

![](../../../assets/images/csc250/lecture23/Reduc-15a.png){: width="80%"} 

<br><br>


### Contradiction Machine 2: $M_{OPPOSITE}$ to prove $D_{ATM}$ can't exist:

<br>

Prove that the following Language is NOT Decidable:

$$ ATM = \{ <M, w> \vert \text{ M is a TM that accepts the word w} \}$$

  
Step 1: Assume Is ATM is **Decidable** Now try to use this "fact" to arrive at a contradiction  

Again, this means that $D_{ATM}$ <b>exists and it always replies with a consistent answer</b>.
  
Consider the Machine $M_{OPPOSITE} ( < M> )$  
  
$$ 
\begin{align*} &M_{OPPOSITE}:\\ 
& \quad \text{ On input $ < M > $ }:\\ 
& \quad \text{ Simulate $D_{ATM} \; on \; < M , < M > > $}\\ 
& \quad \text{ If $D_{ATM}$ accepts, REJECT. }\\ 
& \quad \text{ If $D_{ATM}$ rejects, ACCEPT. }\\ 
\end{align*} 
$$  
  
And run $M_{OPPOSITE}$ with input equal to itself, we get:

$$ 
\begin{align*} &M_{OPPOSITE}:\\ 
& \quad \text{ On input $ < M_{OPPOSITE} > $ }:\\ 
& \quad \text{ Simulate $D_{ATM} \; on \; < M_{OPPOSITE} , M_{OPPOSITE} > $}\\ 
& \quad \text{ If $D_{ATM}$ accepts, REJECT. }\\ 
& \quad \text{ If $D_{ATM}$ rejects, ACCEPT. }\\ 
\end{align*} 
$$  

This causes an inconsistent response from $D_{ATM}$: a contradiction

therefore, $D_{ATM}$ can't exist.

![](../../../assets/images/csc250/lecture23/Reduc-15b.png){: width="80%"} 



## Contradiction Machines are hard... but there's a better way

<br><br>

Let's use the knowledge that ATM is undecidable to make a new proof that HALT is undecidable.

<br><br>
  
![](../../../assets/images/csc250/lecture18/Reduc-18.png){: width="80%"} 
  
In other words, $ HALT$ is AT LEAST as hard as $ ATM $  
(So if we can solve HALT, we can, for sure, solve ATM)  
  
  
 <br><br>
  
  
![](../../../assets/images/csc250/lecture18/Reduc-19.png){: width="80%"} 
  
Try it out yourselves first  
  
Think of a way you can get to say:  
if we can solve HALT, we can, for sure, solve ATM  
  
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
Assume HALT is decidable, and so there exists some $D_{HALT}$ that decides, for any input $< M,w>$, whether $M$ halts on $w$.  
  
We'll design the Machine $D_{ATM} $ as follows:  
  
$$ 
\begin{align*} &D_{ATM}:\\
& \text{ On input $ < M, w > $ }:\\
& \text{ Simulate $D_{HALT} \; on \; < M, w > $}\\
& \text{ If $D_{HALT}$ rejects, $M$ doesn't halt, so it did not accept: REJECT. }\\
& \text{ If $D_{HALT}$ accepts, we know $M$ won't loop forever, so }\\
& \quad \text{ Simulate $M$ on $w$ ADWID }\\
\end{align*} 
$$  
  
This machine is a decider for ATM (why?)  
<br>
– it avoided the only problem we had with solving ATM, namely telling the difference between looping and not waiting long enough.  
<br><br>
  
However, we proved that ATM was undecidable by contradiction just a few minutes ago.  
Aaaand...the only condition we need to build $D_{ATM}$ was that $D_{HALT}$ existed, so ...  
<br><br>
Since $D_{ATM}$ can't exist, <b>$D_{HALT} \; $ must not exist</b>.
      </p>
    </details>
  </span>
</div> 

<br><br>

  
  
![](../../../assets/images/csc250/lecture18/Reduc-20.png){: width="80%"} 
  
<b>Example</b>:  
  
Above, we said:  
$ ATM \leq HALT $  
  
Therefore :

1.  $D_{HALT}$ can be used to build $D_{ATM}$

  
![](../../../assets/images/csc250/lecture18/Reduc-21.png){: width="80%"} 
  
<b>Example</b>:  
  
Above, we said:  
$ ATM \leq HALT $  
  
Therefore :

* It is possible that $D_{HALT}$ can be much harder to build than $D_{ATM}$, so if you have $D_{ATM}$, you would still have much more to do.
  
  
* If you want to show equivalence, you have to prove both directions.

  
  
![](../../../assets/images/csc250/lecture18/Reduc-22.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-23.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-24.png){: width="80%"} 
  
Let's go together  
  
Let's try to say ... "if we can solve ATM01, we can, for sure, solve ATM  
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
Assume ATM01 is decidable, and so there exists some $D_{ATM01}$ that decides, for any input $< M >$, whether $M$ accepts $w = 01$.  
  
We'll design the Machine $D_{ATM} $ as follows:  
  
$$ 
\begin{align*} 
&D_{ATM}:\\
& \quad \text{ On input $ < M, w > $ }:\\
& \quad \text{ Simulate $D_{ATM01} \; on \; < M > $}\\
& \quad \text{ If $D_{ATM01}$ accepts, we know $M$ accepts string 01 }\\
& \quad \text{ If $D_{ATM01}$ rejects, we know $M$ doesn't accept string 01 }\\
& \quad \quad \text{ ... }\\
\end{align*} 
$$  
  
Then what?  <br>

$D_{ATM01} $ only gives useful information about the string 01.  
It doesn't even look at the string $w$ (which we need to build $D_{ATM} $).  <br>
  
We’ll have the be a little more clever to get our machine to force it to check $w$.
      </p>
    </details>
  </span>
</div> 

<br><br>

  

![](../../../assets/images/csc250/lecture18/Reduc-25.png){: width="80%"} 
  
Let's go together  
  
Let's use, in addition to $D_{ATM01} $, an extra HELPER machine to help us extend the usefulness of $D_{ATM01} $.  
  
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
Assume ATM01 is decidable, and so there exists some $D_{ATM01}$ that decides, for any input $< M >$, whether $M$ accepts $w = 01$.  
  
We'll design the Machine $D_{ATM} $ as follows:  
  
$$ 
\begin{align*} 
&D_{ATM}:\\
& \text{ On input $ < M, w > $ }:\\
& \text{ 1. build a HELPER machine (but don't run it yet) $Helper_{M,w}$ that is shown below: }\\
& \; \\
& \qquad Helper_{M,w}:\\
& \qquad \text{ On input $ x $ }: \quad \color{gray}{\text{# x: Anything! we don't care} }\\
& \qquad \text{ Ignore $ x $ and run $M$ on $w$ ADWID} \quad \color{gray}{\text{# We hardcode what $Helper_{M,w}$ does} }\\
& \; \\
& \text{ 2. Simulate $D_{ATM01}$ on $Helper_{M,w}$ } ADWID\\
\end{align*} 
$$  
  
  
  
<b>Analysis of cases</b> 
  
What is going on?:

<ul>
  <li>Inside our $D_{ATM} $ machine, we use $D_{ATM01} $ to ask if its input TM $M$ accepts $01$ ...  
    But in order to do it ... <b>it is forced to simulate the input machine $M$</b> ... instead of running $D_{ATM01} $ on $M$, we can have $D_{ATM01} $ run on a <b>Trojan-Horse Machine</b> whose only job is to check if $M$ accepts $w$!</li>
    <br>
  <li>$Helper_{M,w}$ is a TM built solely to check if the $M$ actually accepts the $w$ from the input to $D_{ATM} $ ($ < M, w > $ ).</li>
  <br>
  <li>When $D_{ATM01} $ runs $Helper_{M,w}$ with input $01$, we IGNORE the input and just run $M$ on $w$  
    It will actually answer if $M$ accepts $w$ rather than if the input $Helper_{M,w}$ accepts $01$.
    <ul>
      <li>If $Helper_{M,w}$ replies ACCEPT, then $D_{ATM01}$ would return ACCEPT</li>
      <li>If $Helper_{M,w}$ replies REJECT, then $D_{ATM01}$ would return REJECT</li>
    </ul>
  </li>
  <br>
  <li>The output of $D_{ATM01} $ is NOT actually answering if its input accepts $01$... it is secretly answering the question : "Does $M$ accept $w$?"</li>
</ul>

  
If $D_{ATM01} $ says that $Helper_{M,w}$ accepts 01,  
we know that $M$ must have accepted $w$.  
<br><br>

For any $M, w$ pair that gets passed into $D_{ATM} $, we can construct a hardcoded helper machine and trick $D_{ATM01} $ into telling us the answer,  
in other words...<b>deciding ATM</b>.  
<br><br>

However, This can't be true!!,  
<b>we know ATM is undecidable, so ATM01 must also be undecidable</b>.
      </p>
    </details>
  </span>
</div> 

<br><br>



# Now, let's try it again!


Prove that the following Language is NOT Decidable:

$$ ATM11 = \{ <M> \vert \text{ M is a TM that accepts the word 11} \}$$

 -->