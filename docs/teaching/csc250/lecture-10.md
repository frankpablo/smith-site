---
layout: default
title: Lecture10
parent: CSC250
grand_parent: Teaching
nav_order: 10
#permalink: /docs/teaching/csc110/
---  


Lecture Notes 10: Practice with PLs and Homework02 Grading
=============================================================

  

## Outline ##


This class we'll discuss:

* Grading on HW02
* Catch-Up: REs, FAs, and PL


* * *

A Slideshow:
---------------


<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTm7TxUJ1CkB4f8CULtg3mMPgnGj4VdpmGk9d0gBz1LMs2a28iYWql1KmnjafFv5a5RSBXd1x4j02DE/embed?start=false&loop=false&delayms=60000" frameborder="0" width="800" height="629" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

---


GUIDED NOTES (Optional)
=======================

  

Recap: RE, FA, and their equivalence
------------------------------------

A **Regular Expression** is a succint way to indicate a pattern that is used to filter out strings so that only certain strings are accepted into a set of words called a **Regular Language**  
  
They look like this:  
  
**\\[(00(10)^\*11) + (11(01)^\*00) \\]**  
  
**Activity 1** \[2 minutes\]:  

What is the Language accepted by this RE? (Use an English sentence to summarize it)

(Wait; then Click)  
  

It is the Language that consists of words that start with $00$, and with $11$ and have zero or more $10$ pairs in between, **OR** the words that start with $11$, and with $00$ and have zero or more $01$ pairs in between.  
  
Examples are: \\[0011, 1100, 001011, 110100, 00101011, 11010100, \dots \\]

  
  
A **Finite Automaton** is a state machine described by a 5-tuple: $ (Q, \Sigma, \delta, q_0, F) $ that represents a process that examines a string of symbols, one at a time, and accepts or rejects the string depending on the sequence of visited states.  
  
**Activity 2** \[2 minutes\]:  

What is the FA that does the exact same thing as the RE shown above?

Answer below, so don;t peek if you wanna do it yourself.

  
  
![RE to FA and back](../../../assets/images/csc250/lecture09/RE-to-FA-to-RE.gif){: width="80%"}  
  

  
  

### Relation between REs and FAs

  
  
![RE to FA and beyond?](../../../assets/images/csc250/lecture09/Langs-past-RE-FA.png){: width="50%"}  
  

  

* * *

  

Non Regular Languages
---------------------


## Step-by-Step explanation:

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSMr1r0hrl9s6oZCxQe3FERLOIzz1P5n-CXhj30ShwCzpLLp5S5eloCll79CMHk4axyCSjp-VJH_TmD/embed?start=false&loop=false&delayms=60000" frameborder="0" width="480" height="299" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

What are the limits of the REs and FAs we've seen?  
  
In other words, are there are some languages that cannot be described with them?  
  
The answer is **YES**.  
  
**Can you suggest a couple examples?**

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            An example: 
            $$\text{Language B }= \{ 0^n1^n \mid n\geq 0\}$$
            Notice that we would need states that capture the fact that there were no 0z and no 1s ; one 0 and one 1; two 0s and teo 1s; etc... up to $ n \rightarrow \inf$
        </p>
      </details>
    </span>
  </div> 
  

  
  
  
How do we find out if a language is regular or not? WHat properties must a NON-regular language have? 
  
* First thing first: **It MUST BE INFINITE**... why?
  
* But, is an infinite language non-regular? ... NO, because (1*) is a RE that generatea an infinit RL!
  
* What else distinguishes a RL from a NRL?
  

  
Proving that a whole language is not regular because you can't find the RE or FA to generate it is not a valid argument.  
  
But also, using a proof by construction to show that something does NOT have a property is not the right path.  
  
We would like to have a proof that finds a <b>contradiction</b> but that would require showing that a language does not have some property! (That is the right way).  
  

### Proof Idea

1.  We will define a special property that all regular languages have.
2.  If we can show that a language does not have this property, we are guaranteed that it is not regular.

  

* * *

  

Defining a property all Regular Languages have
----------------------------------------------


### Intuition First :

* In an FA, we MUST have a FINITE number of states
* However, we CAN get an infinite list of words!!!
* How do we get infinite words from a finite set of states?

  
  
**Example:**  
Imagine a language L that has the following words:  
$ L = \{ a, \; ak,\; afgh,\; afghk,\; afghfgh,\; afghfghk,\; afghfghfgh,\; afghfghfghk,\; \dots \} $  
  
**Activity 4** \[4 minutes\]:  

Can you come up with more words in this Language just from the observed pattern?  
Can you think of the FA that recognizes this language?  
Can you come up with the RE that generates this language?

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
The pattern must have, as a <b>prefix</b>, the pattern a  
followed by any number of repetitions of the sequences fgh,  
and optionally terminate with a k or nothing else ($\epsilon$), which acts like a <b>suffix</b>.
  
Notice that this infinite language could be made like this:  
<br>

<img class="img-fluid" src="../../../assets/images/csc250/lecture09/afghk-DFA.png" alt="afghk-DFA" style="width:50%"><br>

Another version is:
<br>

<img class="img-fluid" src="../../../assets/images/csc250/lecture09/afghk-NFA.png" alt="afghk-NFA" style="width:60%"><br>
  
  
An RE ( with $\Sigma = \text{english alphabet} $) that works is: $a(fgh)^*(k+\epsilon)$  
  
  
  
The Important thing to note is that after a specific size (let's call it N), any new words that we generate 
<b>MUST come from a repeated pattern</b>!  
<br> <br>

As words get longer, we have to traverse loops more and more often.  
  <br>
If we wanted another word in the language, we could take any one of our existing words in the language and change the number of times we went around one of those loops.  
  <br>
Turns out that <b>there’s a precise way to articulate this property, which will be what we need to be able to prove a language is non-regular.</b>
        </p>
      </details>
    </span>
  </div>   
  


Before we do this, let's see more examples of this property:

### Predicting words based on a pattern

For each example: say some words each of these machine accepts (and rejects)...

Then, think if you can predict what other words might belong to the same language, just from the pattern you see.

As you do these, keep track of 1) the size of the word, and 2) if you employed any loops

1) \\
![example](../../../assets/images/csc250/lecture09/small1.png){: width="20%"} 

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>Note: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            The machine shown above could accept $\epsilon$ or use a loop.
        </p>
      </details>
    </span>
  </div> 

2) \\
![example](../../../assets/images/csc250/lecture09/small2.png){: width="25%"} 

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>Note: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            The machine shown above could accept $\epsilon$ or use a loop... So if it accepts a word, and that word is not $\epsilon$... what is the pattern for that word?
        </p>
      </details>
    </span>
  </div> 

3) \\
![example](../../../assets/images/csc250/lecture09/medium1.png){: width="40%"} 


   <div class="container mx-lg-5">
    <span style='color:#6f439a'>Note: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            This machine has a before-the-first-loop part ($0$) and an after-the first-loop-part (also $0$). So if we decide NOT to take the loop, the smallest word we can accept has two symbols. But if we do, what is the pattern?
        </p>
      </details>
    </span>
  </div> 

4) \\
![example](../../../assets/images/csc250/lecture09/medium2.png){: width="40%"} 


5) \\
![example](../../../assets/images/csc250/lecture09/big0.png){: width="65%"} 


6) \\
![example](../../../assets/images/csc250/lecture09/big1.png){: width="65%"} 

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>Note: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            This machine could have a single symbol (a $1$)... but if it has any more, then it MUST have at least 4 symbols! ... if it has more than 4 symbols, what is the pattern?
        </p>
      </details>
    </span>
  </div> 


7) \\
![example](../../../assets/images/csc250/lecture09/big2.png){: width="65%"} 

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>Note: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            This machine could have a single symbol (a $1$)... but if it has any more, then it MUST ALSO have at least 4 symbols! ... if it has more than 4 symbols, what is the pattern THIS TIME?
        </p>
      </details>
    </span>
  </div> 


8) \\
![example](../../../assets/images/csc250/lecture09/huge2.png){: width="75%"} 
  
   <div class="container mx-lg-5">
    <span style='color:#6f439a'>Note: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            This machine could have a single symbol (an $a$)... but if it has any more, then it MUST have at least 4 symbols! ... Note that even if we completely ignore the second loop (we never take it), the first loop is enough to build an infinite number of words in the language!
        </p>
      </details>
    </span>
  </div> 
  

* * *

  

The Pumping Lemma
-----------------

  
  
![example](../../../assets/images/csc250/lecture09/PL.png){: width="80%"} 
  
Translation: if L is a regular language, then words that are sufficiently long must have some repeatable subsequence that we could use to generate arbitrarily many more words in L  
  
![example](../../../assets/images/csc250/lecture09/intuition.png){: width="80%"}
  
  
  
Note: If proven true, the lemma, as applied to a language $ L_{short} $ whose words are all smaller than $N$, would be _vacuously_ true: Obviously the three conditions hold for all strings of length at least $N$ if there aren’t any such strings.  
  

### Proof for the Pumping Lemma

Check out our set of accepted words from our running example:

* $ \texttt{1}: A^{\prime} \vdash B \rightarrow \text{Accepted}$
* $ \texttt{010}: A^{\prime} \vdash A \vdash B \vdash B \rightarrow \text{Accepted}$
* $ \texttt{01000}: A^{\prime} \vdash A \vdash B \vdash B \vdash B \vdash B \rightarrow \text{Accepted}$

  
  
Notation:

1.  $A^{\prime}$ is just the "Start State A before consuming any symbols"
2.  The Turnsile symbol $ \vdash $ means: "yields", "proves", "satisfies" or "entails".

  
  
**Activity 5** \[2 minutes\]:  

**Count the number of symbols and the number of states involved in accepting the word.**  
  
Do you notice something? 

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
            The number of states is one more than the number of symbols (since we start at a state before consuming the first symbol).  
        </p>
      </details>
    </span>
  </div> 
  

Given this observation, the proof goes like this:  
  
  
  
![example](../../../assets/images/csc250/lecture09/PL1.png){: width="60%"}
  
  
  
![example](../../../assets/images/csc250/lecture09/PL2.png){: width="60%"} 
  
  
  
![example](../../../assets/images/csc250/lecture09/PL2b.png){: width="60%"}
  
  
  
![example](../../../assets/images/csc250/lecture09/PL3.png){: width="60%"}
  
All parts of the $xyz$ word are sequences of symbols, not necessarily a single symbol.  

1.  $ \vdash \ast $ means: After several steps ...

  
  
![example](../../../assets/images/csc250/lecture09/PL4.png){: width="60%"}
  
  
  
![example](../../../assets/images/csc250/lecture09/PL5.png){: width="60%"}
  
**Why are we doing this?**  
  

### Proving that some language $L_{\tiny{NonReg}} $ is not Regular

1.  We will define a special property that all regular languages have (The Pumping Lemma).
2.  If we can show that a language does not have this property, we are guaranteed that it is not regular.

  

* * *

  

Proving a language is not Regular
---------------------------------

* The pumping lemma tells us that **IF L is regular, then this property must hold for every single word in L (except the first few short words, which we don’t have to care about)**
* **Idea for contradiction**: assume it’s true, then find ONE WORD that breaks this rule; one, single word that can’t be pumped is enough to prove the language isn’t regular.
* Remember: it’s a lot easier to show something does exist than to prove that it doesn’t or can’t.  
      
    ![example 1!](../../../assets/images/csc250/lecture09/NonRegExample1.png){: width="60%"}  
      
    Steps:
    
    1.  Suppose this were regular.
    2.  Let $N$ be the constant selected by the pumping lemma.
    3.  Consider the string $w = 0^N 1^N $. Then $ \mid w \mid = 2 \cdot N>N $, and so we can write $w = xyz$.
    4.  Since $\mid xy \mid \leq N $ and $ \mid y \mid > 0 $, it must be that $y$ is a non-empty substring of the $0^N$ part, i.e. $y = 0^k $ for some k>0.
    5.  According to the pumping lemma, $ xyyz = 0^{N+k} 1^N $ must also belong to L for k>0
    6.  CONTRADICTION!
    
      
      
      
      
    ![example 2!](../../../assets/images/csc250/lecture09/NonRegExample2.png){: width="60%"}  
      
    **Proof sketch**  
    Since $HALF$ is a subset of $EQ$ and we proved $HALF$ is not regular, then we could pick $w \in HALF \subset EQ$ and just indicate that that is enough.  
      
    The technical part is: simply choose a way to express the fact that $HALF$ is a subset of $EQ$. Steps:
    
    1.  This proof by contradiction will use the previous example and closure properties.
    2.  Let’s assume EQ is regular.
    3.  We also know that $0^\*1^\*$ is regular.
    4.  Because regular languages are closed under intersection, this language would also have to be regular: $ EQ \cap 0^\*1^\* = \{ w \in \{0,1\}^* : w = 0^i1^i, \text{for some }i \geq 0 \} = HALF $
    5.  We just proved the non-regularity of HALF, which is a contradiction.
    6.  Therefore EQ cannot be regular.
      
    
    * * *
    
      
    
Some Perspective
----------------

Why am I asking you all of these questions about regularity of languages, etc.?  
  
REs and FAs are really simple computational machines.  
  
What does this have to do with getting your Java code to compile, or using dynamic programming, or ...  
  
Turns out that there are some surprisingly algorithmic things we can do when we start asking questions about these simple machines.  
  
Let’s take a look at some questions we might ask.  
  
  
  
![example 2!](../../../assets/images/csc250/lecture09/Questions.png){: width="60%"} 
  

  