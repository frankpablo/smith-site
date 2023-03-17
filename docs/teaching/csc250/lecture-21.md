---
layout: default
title: Lecture21
parent: CSC250
grand_parent: Teaching
nav_order: 21
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 21: Undecidability
==============================



Intro to Undecidable Problems (Languages)
-----------------------------------------

  
## Problems as Languages  
  
  
  
In this class, we have converted "finding a solution to a problem" to "Learning to accept words from a Language".  
  
In our world, **Answering a question** means building a machine that recognizes the language-version of that question.  
  
Example problem:  
"Can you come up with a binary string with a pattern of 0s and 1s such that the string is a palindrome"  
  
Example Language-Version:  
$$ L = \{ w \in \Sigma^* | w^R = w \} $$  
  
Example solution:  
(See the CMF, PDA, or TM solutions to this problem)  
  
  
  
  
# Questions about Machines  
  
  
  
Often we'll ask questions about the machines we've seen so far.  
  
Again, **answering a question** means building a machine that recognizes the language-version of that question.  
  
  
  
So, a problem like:  
"Find the set of Turing Machines that have up to 5 states",  
can be rephrased as finding the Language: 

$$ L = \{ < M > | M \text{ is a TM and } M \text{ has fewer than 5 states} \} $$  
  
  
  
  
# Answering with an Algorithm  
  

  
How would you "Solve" the problem for:  

$$ L = \{ < M > | M \text{ is a TM and } M \text{ has fewer than 5 states} \} $$  
  

What could you use to "Solve" (Decide/Recognize) $L$? 


<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
	      Another Turing Machine!! ... A <b>Decider</b> for $L$ we'll call $D_L$

   $$ 
   \begin{align*} & D_L :\\ 
   & \text{On INPUT } < M >\\ 
   & \quad \text{Inspect the description of } M \\ 
   & \quad \quad \text{IF $M$ is not a valid TM: REJECT} \\ 
   & \quad \quad \text{ELSE IF $M$ has fewer than 5 states: ACCEPT} \\ 
   & \quad \quad \text{ELSE: REJECT} \\ 
   \end{align*} 
   $$  

   CAN we get stuck on a loop?  
   (Note that we know something about description $M$ that helps us answer this question)
      </p>
    </details>
  </span>
</div> 
  


# Another Recap (so we don't get lost)
  
<br><br>

![](../../../assets/images/csc250/lecture18/Reduc-02.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-03.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-04.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-05.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-06.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-10.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-11.png){: width="80%"} 
  
  
<!-- Note: this is in PS05 so watch the vdeo recording to hear about how to solve this. (you should be able to clearly explain both approaches)   -->
  
  
  
  
  
  
## Questions about Machines  
  
  
  
### Discuss if you could build $D_L$ for the following language: 

$$L = { < M, w > | TM \; M \text{ accepts } w \text{ in fewer than 10 steps} }$$  
  
  
  
### Discuss if you could build $D_L$ for the following language:  

$$ L = \{ < A > | \text{DFA $A$ accepts an infinite number of words (L(A) is infinite)} \} $$  
  

  
### Discuss if you could build $D_L$ for the following language:  

$$ A_{TM} = \{ < M, w> | \text{TM $M$ accepts } w \} $$  
  



<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
      	<ul>
					<li>Can we prove it is at least recognizable?</li>
					<li>Can we prove it is NOT Decidable?</li>
					<li>Are these two things the same?</li>
				</ul>
      </p>
    </details>
  </span>
</div> 
  

<br><br>


How about ATM?
---------------------

  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-12.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-13.png){: width="80%"} 
  
  
  

Can we come up with a simple proof?  
  


<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>

<b>Proof by construction</b>:  

$$ 
\begin{align*} 
&R_{ATM}:\\ 
& \text{ On input $ < M,w > $ }:\\ 
& \text{ Simulate M on w.}\\ 
& \text{ If it accepts, accept. }\\ 
\end{align*} 
$$
      </p>
    </details>
  </span>
</div> 

<br><br>
  
Is ATM **decidable**?  
  
  
  
Discuss if you could build $D_L$ for the following language:  

$$ A_{TM} = \{ < M, w> | \text{TM $M$ accepts } w \} $$  
  
Can a $D_{ATM}$ be constructed such that:

1.  It Accepts any $w $ such that $w \in A_{TM}$
  
AND  
  
5.  It Rejects any $w $ such that $w \notin A_{TM}$

  
  
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>

<b>Intuition...Not decidable</b>:  

<ul>
	<li>we can’t tell the difference between looping and “just haven’t waited long enough”.</li>
	<li>But we can't prove "we haven't waited long enough" for each input... (AND we have infinite inputs)</li>
	<li>But we can use another technique to try to prove this... <b>CONTRADICTION</b>!</li>
</ul>
  
If we can find a single example where we can't predict what $D_{ATM}$ will say ... then we have it!
      </p>
    </details>
  </span>
</div> 

<br><br>
  

  
![](../../../assets/images/csc250/lecture18/Reduc-14.png){: width="80%"} 
  
Step 1: Assume Is ATM is **Decidable** Now try to use this "fact" to arrive at a contradiction  
  
  
Consider the Machine $M_{OPPOSITE} ( < M> )$  
  
$$ \begin{align*} &M_{OPPOSITE}:\\ 
& \quad \text{ On input $ < M > $ }:\\ 
& \quad \text{ Simulate $D_{ATM} \; on \; < M , < M > > $}\\ 
& \quad \text{ If $D_{ATM}$ accepts, REJECT. }\\ 
& \quad \text{ If $D_{ATM}$ rejects, ACCEPT. }\\ 
\end{align*} 
$$  
  
  
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-15.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-16.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-17.png){: width="80%"} 
  


  
![](../../../assets/images/csc250/lecture18/Reduc-18.png){: width="80%"} 
  
In other words, $ HALT$ is AT LEAST as hard as $ ATM $  
(So if we can solve HALT, we can, for sure, solve ATM)  
  
  
  
  
  
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
& \quad \text{ On input $ < M, w > $ }:\\ 
& \quad \text{ Simulate $D_{HALT} \; on \; < M, w > $}\\ 
& \quad \text{ If $D_{HALT}$ rejects, $M$ doesn't halt, so it did not accept: REJECT. }\\ 
& \quad \text{ If $D_{HALT}$ accepts, we know $M$ won't loop forever, so }\\ 
& \quad \quad \text{ Simulate $M$ on $w$ ADWID }\\ 
\end{align*} 
$$  
  
This machine is a decider for ATM (why?)  
– it avoided the only problem we had with solving ATM, namely telling the difference between looping and lot waiting long enough.  
<br>
  
However, we proved that ATM was undecidable by contradiction just a few minutes ago.  
Aaaand...the only condition we need to build $D_{ATM}$ was that $D_{HALT}$ existed, so ...  
<b>$D_{HALT} \; $ must not exist</b>.      
      </p>
    </details>
  </span>
</div> 

<br><br>
  



Prep For Midterm
-------------------------------------

  * The midterm is Self-Scheduled starting today
  * The link with the info will be added here: TBD
  * The exam is individual, and will contain multiple-choice as well as free-answer questions.
  * It will be designed for 1.5 hours and you'll have 3 hours to complete it.
  * A single (double sided) aid-sheet will be allowed and you must turn it in.
  * The subjects covered are:

        * Predicate Logic
            * basic proofs
        * Regular Expressions and FAs (DFAs and NFAs)
            * formal definition, 
            * examples
            * closure properties
        * Non-Regularity and the Pumping Lemma
        * Context-Free Grammars and Push-Down Automata
            * formal definition 
            * examples
            * closure properties        
        * Turing Machines
            * formal definition 
            * examples
            * closure properties
            * What can they do and what can't they do