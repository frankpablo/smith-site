---
layout: default
title: Lecture14
parent: CSC250
grand_parent: Teaching
nav_order: 14
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 14: OLD Context-Free Grammars
=======================================

  

Outline
-------

This class we'll discuss:

* Perspectives on simple machines
* Properties of Regular Languages
* Looking ahead: Context-Free Grammars
* CFG examples

  <!-- 
  

Intro: Context-Free Grammar
---------------------------

  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF01.png){: width="60%"} 
  
EQ, HALF, PAL  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF02.png)  
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF03.png)  
  
Finite automata and regular expressions are limited  
  
They both only match patterns that can be described by reaching L to R  
  
Some patterns are more interesting…  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF04.png)  
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF05.png){: width="60%"} 
  
Seems like PAL lives really close to Regular: there’s a structure to the words that’s ALMOST regular… but the pattern is in the middle.  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF06.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF07.png){: width="80%"} 
  
  
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF08.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF09.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF10.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF11.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF12.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF13.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF14.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF15.png){: width="80%"} 
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture10/CF16.png){: width="80%"} 
  

  
  
  
  

### How about EQ?

  
  
  
  
In the following map...

* Where are CFGs?
* How would we represent a finite language with a CFG?
* How would we represent a regular language with a CFG?
* Is there something outside a CFG?
* Where is EQ?

  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF17.png)  
  

### Ideas to prove all RL's are "inside" CFGs

  
  
(You suggest some:)  
  
  
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF18.png)  
  
  
  
  
  

### Tip for designing Context-Free-Languages

  
  
Many CFLs are the union of simpler CFLs. If you must construct a CFG for a CFL that you can break into simpler pieces, do so and then construct individual grammars for each piece.  
  
Example:  
  
If the objective is to design a grammar for $ \{0^n1^n \mid n>0 \} \cup \{1^n0^1 \mid n>0 \}$, start with two sub-languages using sub-"starting symbols" and then join them to get the target language starting at $S$  
  
You can build:  
$S_1 = 0S1 \mid \epsilon $  
and  
$S_2 = 1S0 \mid \epsilon$, :  
  
And then join them to obtain:  
  
$$
\begin{alignat}{2} S &= S_1 \mid S_2 \\ S_1 &= 0S_1 1 \mid \epsilon \\ S_2 &= 1S_2 0 \mid \epsilon \end{alignat}
$$
  

### So now, how would we "Build" a Regular Language using a CFG?

  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF19.png){: width="80%"} 
  

  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF20.png){: width="80%"} 
  


### Approach 2: RL's are a special case of CFLs

You can convert any DFA into an equivalent CFG as follows.

1.  Make a variable $S_i$ for each state $q_i$ of the DFA.
2.  Add the rule $S_i$ → $aS_j$ to the CFG if $\delta (q_i,a) = q_j$ is a transition in the DFA.
3.  Add the rule $S_i$ → ε if qi is an accept state of the DFA.
4.  Make $S_0$ the start variable of the grammar, where $q_0$ is the start state of the machine.

  
  
Verify on your own that the resulting CFG generates the same language that the DFA recognizes.  
  
  
  
**Activity 1** \[2 minutes\]:  

Try to build your own CFG. One that "Accepts" the language: $ L = \{ w \in \Sigma^* \vert w \ has \ an \ odd \ number \ of \ 1s \}$

  
   <div class="container mx-lg-5">
    <span style='color:#6f439a'>answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <img class="img-fluid" src="../../../assets/images/csc250/lecture12/oddOnes.png" alt="OddOnes-to-CFG" style="width:50%"><br> 
          if A is $S_0$ and B is $S_1$: 

$$
\begin{alignat}{2} S &\rightarrow_g S_0 \\ S_0 &\rightarrow_g 0S_0 \\ S_0 &\rightarrow_g 1S_1 \\ S_1 &\rightarrow_g \epsilon \\ S_1 &\rightarrow_g 0S_1 \\ S_1 &\rightarrow_g 1S_0 \\ \end{alignat}
$$
        </p>
      </details>
    </span>
  </div> 
  
<!-- ![OddOnes-to-CFG](../../../assets/images/csc250/lecture12/oddOnes.png){: width="60%"}  -->
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF21.png){: width="80%"} 
  

### How do we prove there are languages that are NOT (beyond) CFLs?

  
  
How did we do this back when we did it for RLs?  
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF22.png){: width="80%"} 
  

* the middle part is not too big
* v and y (the repeating parts) are not both simultaneously empty
* repeating v and or y we will keep us in the language

  
  
Note that RLs are a special case of Context-Free-Languages (without the $uv^i$) part.  
  
  
  
So, if we have a pumping lemma for CFGs, is there a "Machine" equivalent to the Finite Automatons as well?  
  
  
  
We'll see those next class.

  

* * *

  

Proving a language is NOT context-free
--------------------------------------

  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF23.png)  
  
  
  
  
  
**What does your intuition say?** Is it a CFL?  
  
  
  
  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF24.png)  
  
  
  
Remember:

* Given a structure of $w = uvxyz$, and $ \mid vy \mid \geq 1$
* We want to find an $i$ for which a word $uv^ixy^iz$  
    does not have a prime length ( $ \mid uv^ixy^iz \mid $ is not prime ) after being "pumped" some number of times.
* Here, we can start with a word $w$ with length $p\geq N $ ($N$ provided by the pumping Lemma)
* Now, the trick is to pump the pattern some number of times so that we can prove that the final length is NOT prime!
* Ideas?



   <div class="container mx-lg-5">
    <span style='color:#6f439a'>answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
					Steps:<br>
					<ol>
						<li>The length of a word $\mid uv^ixy^iz \mid $  
					    is the length of $ \mid w \mid $ plus any added repetitions of $v$ and $y$</li>
						<li>So, $ \mid uv^ixy^iz \mid $ is $ \mid w\mid + (i-1)\mid vy \mid $</li>
						<li>Since we said $w$ is in PRIMEAL, then $ \mid w\mid $ is some prime number $p\geq N $.</li>
						<li>Then, $ \mid uv^ixy^iz \mid = \mid w\mid + (i-1)\mid vy \mid = p + (i-1)\mid vy \mid$</li>
						<li>Now, <b>What possible choice of $i$ could we choose to cause the overall length to be provably NOT prime</b> ? </li>
					</ol>
        </p>
      </details>
    </span>
  </div> 


Answer Below:

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
If we choose $i$ so that the $i-1$ is equal to $p$ in the following expression:  

$$ \mid uv^ixy^iz \mid = \mid w\mid + (i-1)\mid vy \mid = p + (i-1)\mid vy \mid $$  
Then substituting $i-1$ for $p$ ( by making $i = p-1$), we would get: 

$$ \mid uv^ixy^iz \mid = \mid w \mid + (i-1)\mid vy \mid = p + p\mid vy \mid \\ = p (1+\mid vy \mid) $$
which means that, after pumping, the word is <b>divisible by $p$</b>! and therefore, <b>not of prime length</b>.
        </p>
      </details>
    </span>
  </div> 
 
  

* * *

  

Why are CFGs important?
-----------------------

  
  
![CFGs!!!](../../../assets/images/csc250/lecture12/CF25.png)  
  
check the article out: [https://www.nature.com/articles/nature04675](https://www.nature.com/articles/nature04675)

  

* * *

 -->