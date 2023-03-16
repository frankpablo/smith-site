---
layout: default
title: Lecture23
parent: CSC250
grand_parent: Teaching
nav_order: 23
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 23: More reductions
==============================


## More on Reductions


<br><br>
  
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
& \text{ On input $ < M, w > $ }:\\
& \text{ Simulate $D_{HALT} \; on \; < M, w > $}\\
& \text{ If $D_{HALT}$ rejects, $M$ doesn't halt, so it did not accept: REJECT. }\\
& \text{ If $D_{HALT}$ accepts, we know $M$ won't loop forever, so }\\
& \quad \text{ Simulate $M$ on $w$ ADWID }\\
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

  
  
![](../../../assets/images/csc250/lecture18/Reduc-20.png){: width="80%"} 
  
Example:  
  
Above, we said:  
$ ATM \leq HALT $  
  
Therefore :

1.  $D_{HALT}$ can be used to build $D_{ATM}$

  
![](../../../assets/images/csc250/lecture18/Reduc-21.png){: width="80%"} 
  
Example:  
  
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
&D_{ATM}:\ 
& \text{ On input $ < M, w > $ }:\\
& \text{ Simulate $D_{ATM01} \; on \; < M > $}\\
& \text{ If $D_{ATM01}$ accepts, we know $M$ accepts string 01 }\\
& \text{ If $D_{ATM01}$ rejects, we know $M$ doesn't accept string 01 }\\
& \quad \text{ ... }\\
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
	<li>$Helper_{M,w}$ is a TM built solely to check if the $M$ actually accepts the $w$ from the input to $D_{ATM} $ ($ < M, w > $ ).</li>
	<li>When $D_{ATM01} $ runs $Helper_{M,w}$ with input $01$, we IGNORE the input and just run $M$ on $w$  
    It will actually answer if $M$ accepts $w$ rather than if the input $Helper_{M,w}$ accepts $01$.
		<ul>
			<li>If $Helper_{M,w}$ replies ACCEPT, then $D_{ATM01}$ would return ACCEPT</li>
			<li>If $Helper_{M,w}$ replies REJECT, then $D_{ATM01}$ would return REJECT</li>
		</ul>
	</li>
	<li>The output of $D_{ATM01} $ is NOT actually answering if its input accepts $01$... it is secretly answering the question : "Does $M$ accept $w$?"</li>
</ul>

  
If $D_{ATM01} $ says that $Helper_{M,w}$ accepts 01,  
we know that $M$ must have accepted $w$.  
  
For any $M, w$ pair that gets passed into $D_{ATM} $, we can construct a hardcoded helper machine and trick $D_{ATM01} $ into telling us the answer,  
in other words...<b>deciding ATM</b>.  
  
However, This can't be true!!,  
<b>we know ATM is undecidable, so ATM01 must also be undecidable</b>.
      </p>
    </details>
  </span>
</div> 

<br><br>
  
  
More Reductions: The EMPTY Language
-----------------------------------

  
  
![](../../../assets/images/csc250/lecture18/Reduc-26.png){: width="80%"} 
  
Let's go together  
  
Let's use, in addition to $D_{EMPTY} $, an extra HELPER machine to help us extend the usefulness of $D_{EMPTY} $.  
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
Assume that Empty_TM is decidable, and so there exists some $D_{EMPTY}$ that decides for any input $< M >$ whether $M$’s language is empty.  
  
We'll design the Machine $ D_{ATM} $ as follows:  
  
$$ 
\begin{align*} 
& D_{ATM}:\\ 
& \text{ On input $ < M, w > $ }:\\ 
& \text{ 1. build a HELPER machine (but don't run it yet) $Helper_{M,w}$ that is shown below: }\\ 
& \; \\ 
& \qquad Helper_{M,w}:\\ 
& \qquad \text{ On input $ x $ }: \quad \color{gray}{\text{# x: Anything! we don't care} }\\ 
& \qquad \text{ Ignore $ x $ and run $M$ on $w$ ADWID} \quad \color{gray}{\text{# We hardcode what $Helper_{M,w}$ does} }\\ 
& \; \\ 
& \text{ 2. Simulate $D_{EMPTY}$ on $Helper_{M,w}$ }\\ 
& \qquad \text{ If it accepts, REJECT (if the language of $Helper_{M,w}$ is empty, $M$ doesn’t accept $w$)}\\ 
& \qquad \text{ If it rejects, ACCEPT (the only way $Helper_{M,w}$ accepts anything is if $M$ accepts $w$)}\\ \end{align*} $$ 

<b>Analysis of cases</b>
  
What is going on?:


<ul>
	<li>Inside our $D_{ATM} $ machine, we use $D_{EMPTY} $ to ask if its input TM $M$'s' language is empty ...  
    But in order to do it ... <b>it is forced to simulate the input machine $M$</b> ... instead of running $D_{EMPTY} $ on $M$, we can have $D_{EMPTY} $ run on a <b>Trojan-Horse Machine</b> whose only job is to check if $M$ accepts $w$!</li>
	<li>$Helper_{M,w}$ is a TM built solely to check if the $M$ actually accepts the $w$ from the input to $D_{ATM} $ ($ < M, w >$ ).</li>
	<li>When $D_{EMPTY} $ runs on $Helper_{M,w}$, it simlates $Helper_{M,w}$ (on some unimportant input); $Helper_{M,w}$ IGNORES the input and just runs $M$ on $w$  
    It will actually answer if $M$ accepts $w$ rather than if the input $Helper_{M,w}$ has an empty language.
		<ul>
			<li>If $D_{EMPTY}$ returns ACCEPT, then $Helper_{M,w}$ rejects all words (because $M$ rejects $w$), so return REJECT</li>
			<li>If If $D_{EMPTY}$ returns REJECT it was because $Helper_{M,w}$ accepted, which means $M$ accepted $w$;so return ACCEPT</li>
		</ul>
	</li>
	<li>The output of $D_{EMPTY} $ is NOT actually answering if its input has an empty language... it is secretly answering the question : "Does $M$ accept $w$?"</li>
</ul>

  
  
For any $M, w$ pair that gets passed into $D_{ATM} $, we can construct a hardcoded helper machine and trick $D_{EMPTY} $ into telling us the answer,  
in other words...<b>deciding ATM</b>.  
  
However, This can't be true!!,  
<b>we know ATM is undecidable, so EMPTY must also be undecidable</b>.
      </p>
    </details>
  </span>
</div> 

<br><br>


  


* * *

  

More Reductions: The $\overline{EMPTY}$ Language
-----------------------------------------------------

  
  
  
Is $\overline{EMPTY}$ Decidable?  
  
$\overline{EMPTY}$ is the complement language of $EMPTY$.  
  
Its definition, should be:  
$$ \overline{EMPTY} = \{ < M > | \text{TM $M$ accepts at least one string} \} $$  
  
There is a first simple step: We can say, for sure that $\overline{EMPTY}$ must be undecidable... Why?  
  
 <br><br>
  
  
![](../../../assets/images/csc250/lecture18/Reduc-28.png){: width="80%"} 
  

Can we come up with a simple Recognizer? 

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
<b>Recognizer by construction</b>:  

$$ \begin{align*} &R_{\overline{EMPTY}}:\\ & \text{ On input $ < M > $ }:\\ & \text{ Simulate M on all possible w's one at a time}\\ & \text{ If any accepts, accept. }\\ \end{align*} $$  
  
Is there a problem here?
      </p>
    </details>
  </span>
</div> 

<br><br> 


  
  
![](../../../assets/images/csc250/lecture18/Reduc-30.png){: width="80%"} 

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
The computation is FINITE! 
      </p>
    </details>
  </span>
</div> 

<br><br> 
  
 
  
![](../../../assets/images/csc250/lecture18/Reduc-31.png){: width="80%"} 
  
  
  
![](../../../assets/images/csc250/lecture18/Reduc-31b.png){: width="80%"} 
  

Attempt 2 at a Recognizer for $\overline{EMPTY}$ 

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
<b>Recognizer by construction</b>:  

$$ \begin{align*} &R_{\overline{EMPTY}}:\\ & \text{ On input $ < M > $ }:\\ & \text{ Simulate M on all possible w's DOVETAILED}\\ & \text{ If any accepts, accept. }\\ \end{align*} $$  
  
Is there a problem here?
      </p>
    </details>
  </span>
</div> 

<br><br> 


  

* * *

  

More Reductions: The $\overline{EQ}$ Language
--------------------------------------------------

  
  
![](../../../assets/images/csc250/lecture18/Reduc-33.png){: width="80%"} 
  

A proof:  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
Reducing EMPTY to EQ.  
$$ \begin{align*} &D_{EMPTY}:\\ & \text{ On input $ < M > $ }:\\ & \text{ Build a helper $TM_{\emptyset}$ such that $L(TM_{\emptyset}) = \emptyset$ }:\\ & \text{ Run $D_{EQ}$ on input $ < M, TM_{\emptyset} >$ ADWID}\\ \end{align*} $$  
  
Note that $D_{EQ}$ tells whether $\; < M, TM_{\emptyset} > \; \in \; EQ \;$ , that is, whether $L(M) = L(TM_{\emptyset}) = \emptyset$... Which is the question that $D_{EMPTY}$ is supposed to answer.
      </p>
    </details>
  </span>
</div> 

<br><br>
  




