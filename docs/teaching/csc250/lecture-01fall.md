---
layout: default
title: Lecture01
parent: CSC250
grand_parent: Teaching
nav_order: 3
#permalink: /docs/teaching/csc110/
---  
  

Lecture Notes 01: Intro to Logic and Proofs
===========================================



Outline
-------

This class we'll discuss:

* Why logic?
* Crash course in logic
* What makes a good proof?
* Three kinds of proofs:
   * Direct
   * Contradiction
   * Contrapositive
* What makes a good proof?
* Three kinds of proofs:
* Direct
   * Contradiction
   * Contrapositive
   * Intro to Overleaf

  

* * *


A Slideshow:
---------------


<iframe src="https://docs.google.com/presentation/d/15RB25vz6XsIRk2KIRDjPxfYeqf-br7xUDlTWKH6yCeQ/embed?start=false&loop=false&delayms=60000" frameborder="0" width="480" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>


* * *


GUIDED NOTES (Optional)
=======================



Bird's eye view
---------------

**Remember**: we will have to convert real-life problems to language (symbols, operators, delimiters, quantifiers,...) so we can talk about them, and hopefully solve them, in the abstract.  
  
So... we must agree on some rules about symbol manipulation and drawing conclussions. That is why we'll discuss how to argue a point in such a way that it leaves no room for "comebacks" / "clapbacks" / "retaliation", etc ... in short: in such a way it does not leave the door open for a counter argument.

  

* * *

  

Logic and Logical Thinking
--------------------------

  
  
**Activity 1** \[2 minutes\]: What is Logic and logical thinking?


   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <i>The process of obtaining a conclusion from a set of propositions taken to be true.</i><br>
        </p>
      </details>
    </span>
  </div>
  

#### Two Examples

1.  Easy one:
    
    * Dogs are better than Cats (Proposition or Premise A)
    * Cats are better than Parrots (Proposition or Premise B)
    * Therefore: Dogs are better than Parrots (Proposition or Conclusion C)
    
      
    Note that since we've determined that "All Dogs are better than Parrots"  
    we can now use this as another proposition.
  
  
4.  A Difficult one:
    * If Yak barks, I can't work
    * If I can't work, students are assigned no homework
    * If students have no homework, students are happy
    * Students are happy
    * Therefore: \\( ??? \\)

we'll analyze these and more examples using some structure.  
  
**Activity 2** \[2 minutes\]: if we just use English to analyze the material, **what could go wrong?**

One possible answer: (Wait; then Click)


   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <i>Ambiguity!.</i><br>
        </p>
      </details>
    </span>
  </div>
  
Example:  
  
If a waiter asks: "Would you like a burger or a hotdog?"  
You could answer: "Yes".  
  
Where is the _linguistic issue_ in this exchange?  
  
Other issues: language artifacts, like [contronyms](https://en.wikipedia.org/wiki/Auto-antonym){:target="_blank"} (_dust_, _clip_, _fast_), or  
[homonyms](https://en.wikipedia.org/wiki/Homonym){:target="_blank"} ( "Buffalo buffalo buffalo Buffalo buffalo").

  
  
We need to use some structure to keep track of and operate with propositions that are unambiguous.  
  
For this, we'll use some _agreed-upon_ terminology.  
  
As an _alternative mode of visualizing_ the concepts, whenever possible,  
we'll make use of **Venn Diagrams**.

  

* * *

  

Terminology
-----------

* A **proposition** is a statement that has a truth value (either true or false).  
      
    Example:  
    * The Proposition: "All prime numbers are odd", has a truth value of **false**
  
  
* A proposition has internal structure:  
    It states that all or some members of a set have a property that makes them members of another set.  
      
    Example:  
    
    * "grass is green"
    
      
      
    The **subject** ("grass") refers to the part of the proposition that is to be the focus of the statement.
  
The **predicate**("is green") indicates a property of the set of elements pointed to by the subject.  
  
  
  
* **Quantifiers** enable us to build propositions with degree:  
      
    Example:  
    * "All grass is green"
      
      
    * "No grass is green"
      
      
    * "Some grass is green"

  
  

### Propositional Logic

The process by which we can _combine_ propositions, in a **logical computation**, to obtain valid conclusions  
OR  
with which we can detect errors in the logical computation and refute a conclusion.

  
  
**Activity 3** \[2 minutes\]: how do we combine propositions?  
  
   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <i>Logical Operators!... yes. The answer was the next title :)</i><br>
        </p>
      </details>
    </span>
  </div>
  

* * *

  

Logical Operators
-----------------

In this section we'll discuss **logical operators**, which are rules that indicate the resulting effect on a proposition or a set of propositions when operated upon.

  
  

### Negation

The negation operator, symbol: \\( \\neg \\), AKA **NOT**, is a _unary_ operator and it refers to the opposite truth value of a proposition.  
  
We can show the effect of this operator using a table: 


| p   | ¬p  |
| --- | --- |
| True | False |
| False | True |

another view: 

| p   | ¬p  |
| --- | --- |
| 1   | 0   |
| 0   | 1   |

  
  
![Negation](../../../assets/images/csc250/lecture02/not.png){: width="20%"}  
  
Example: I am not Swedish.  
Note: other symbols you might see are: \\( \\neg p \\text{, } \\sim{p} \\text{, } \\bar p \\text{, } !p \\).

  
  

### Conjunction

The conjunction operator, symbol: \\( \\wedge \\), AKA **AND**, is a _binary_ operator; _it is true if and only if both of its operands are true_.  
  
We can show the effect of this operator using a table: 

| p   | q   | p∧q |
| --- | --- | --- |
| False | False | False |
| False | True | False |
| True | False | False |
| True | True | True |

 another view: 

| p   | q   | p∧q |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 1   |

  
  
![Conjunction](../../../assets/images/csc250/lecture02/and.png){: width="20%"}  
Note that we're labeling on the outside for clarity, but the label refers to the interior of each circle  
  
Example: I am walking and chewing gum.  
Note: other symbols you might see are: \\( p \\wedge q \\text{, } p\\cdot q \\text{, } p\\&q \\).

  
  

### Disjunction

The disjunction operator, symbol: \\( \\lor \\), AKA **OR** is a _binary_ operator; _it is true if any of its operands is true_.  
  
We can show the effect of this operator using a table: 

| p   | q   | p∨q |
| --- | --- | --- |
| False | False | False |
| False | True | True |
| True | False | True |
| True | True | True |

 another view: 

| p   | q   | p∨q |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 1   |

  
  
![Disjunction](../../../assets/images/csc250/lecture02/or.png){: width="20%"}   
  
Example: I want a burger or a hotdog.  
Note: other symbols you might see are: \\( p\\lor q \\text{, } p+ q \\text{, } p\\mid q \\).

  
  

### Exclusive Disjunction

The exclusive disjunction operator, symbol: \\( \\oplus\\), AKA **XOR** is a _binary_ operator; _it is true if its operands are different_.  
  
We can show the effect of this operator using a table: 

| p   | q   | p\\( \\oplus \\)q |
| --- | --- | --- |
| False | False | False |
| False | True | True |
| True | False | True |
| True | True | False |

 another view: 

| p   | q   | p\\( \\oplus \\)q |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 0   |

  
  
![Exclusive Disjunction](../../../assets/images/csc250/lecture02/xor.png){: width="20%"}  
  
Example: No equivalent in the english language... or is there? (**suspenseful music**)  
Note: other symbols you might see are: \\( p\\nleftrightarrow q \\text{, } p\\veebar q \\text{, } p\\not\\equiv q \\).

  

* * *

  

Compound Propositions
---------------------

We can combine these building blocks to make arbitrarily complicated propositions:  
  
\\\[ (p \\wedge ¬q) \\lor (\\neg p \\wedge q) \\\]  
  
**Activity 4** \[2 minutes\]: What is this saying?  
  
Hint: if you build its table, you'll realize it looks llike something...

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <i>same as XOR</i><br>
        </p>
      </details>
    </span>
  </div>
  
  

### More operators: Implication

**Implication**, symbol \\(\\rightarrow\\), AKA **IMPLIES**, is a binary operator that states that:  
_IF p is true, then q **must also be true**_  
  
We can show the effect of this operator using a table:  


| p   | q   | p\\( \\rightarrow \\)q |
| --- | --- | --- |
| False | False | True |
| False | True | True |
| True | False | False |
| True | True | True |


<!-- 6f439a -->
 
   <div class="container mx-lg-5"> 
    <span style='color:#207cb1'>      
        <p>
          Think of the whole statement as a <b>promise</b>; <br>  
          You only "tag" it as FALSE when you break the promise.  
        </p>
      </span>
  </div>
  

  
Rows 3 and 4 are the "normal" ones:

* In Row 3, The promise "IF p is True, then q is also True" has been broken! (because q is NOT True)... so the statement is False (the promise is broken)
* In Row 4, the "IF p is True, then q is also True" has been kept! so the whole statement is True!

  
**But what is happening in rows 1 and 2?**  
Rows 1 and 2 are True because they "technically" are not breaking the promise. We call the Truth value of these statements "Vacuous Truths"  

* In Row 1, The promise "IF p is True, then q is also True" is not being employed (because p is NOT True), regardless of the value of q... so the statement is True (the promise is not broken)
* In Row 2, The promise "IF p is True, then q is also True" is not being employed either (because p is NOT True), regardless of the value of q... so the statement is True (the promise is not broken)

  
  
**Examples**:

* "All my children are goats" is a vacuous truth, when spoken by someone without children
* For the implication "For any integer \\(x\\), if \\(x > 5 \\rightarrow x > 3 \\)",  
    some of its implications are _vacuously true_, like when \\(x\\) is 2, which implies the vacuous truth that  
    if \\(2 > 5 \\rightarrow 2 > 3 \\)  
      
    
* Another example would be:  
    "All living people in the world are resistant to moonlight"  
    This can be written as:  
    
    \\( \\text{if P: living person} \\quad \\text{and M: resistant to moonlight} \\), then the statement is:  
    \\(P \\rightarrow M\\)  
      
    The combination when \\( \\neg P \\text{ (not P, or P:False) and } \\neg M \\text{ (not M, or M:False) } \\)  
      
    Would be True: \\(\\neg P \\rightarrow \\neg M\\)  
    
    and since a vampire is "undead" and "not living", then...

    the sentence:  
      
    **If there are vampires in the world, they are susceptible to moonlight**"  
      
    Is (vacuously) True (I hope).  
      
    ![Science!](../../../assets/images/csc250/lecture02/scienceVsVamp.png){: width="60%"}  
      
    

The left of the \\(\\rightarrow\\) operator in an implication is called the **antecedent**, and the sentence to the right is called the **consequent**.  
  
The best way to remember the way implication works is with this statement:  
The truth value of an implication is false if and only if its antecedent is true and its consequent is false; otherwise, the truth value is true.  
  
**Activity 5** \[2 minutes\]: Can you draw the Venn Diagram for this one?



   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <img class="img-fluid" src="../../../assets/images/csc250/lecture02/implication.png" alt="Implication" style="width:60%">          
        </p>
      </details>
    </span>
  </div>



  
  

### More operators: If and only if

**If and only if**, symbol \\(\\Leftrightarrow\\), AKA **IFF**, is a binary operator that states that:  
_IF p is true, then q **must also true**, and IF q is true, then p **must also true**!_  
  
We can show the effect of this operator using a table:  


| p   | q   | p\\( \\rightarrow \\)q | p\\( \\leftarrow \\)q | p\\( \\Leftrightarrow \\)q |
| --- | --- | --- | --- | --- |
| False | False | True | True | True |
| False | True | True | False | False |
| True | False | False | True | False |
| True | True | True | True | True |

  
  
**Activity 6** \[2 minutes\]: Can you draw the Venn Diagram for this one?  
  

If you look at the p, q, and p\\( \\Leftrightarrow \\)q columns, you might see something that looks familiar

  
  
   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <img class="img-fluid" src="../../../assets/images/csc250/lecture02/iff.png" alt="if and only if" style="width:60%">          
        </p>
      </details>
    </span>
  </div>

  

* * *

  

Inference
---------

Inference is the process of obtaining logical consequences from premises.  
  
Let's use an example:

![Honk](../../../assets/images/csc250/lecture02/honk.png){: width="60%"}

  

  
**Activity 7** \[2 minutes\]: What can you infer if you do not hear a honk?  



You can assume that:  

  * we have a driver behind us;  
  * the driver saw the sign;  
  * they have a working horn  
  * people in this town take bumper stickers seriously

Hint: maybe restructure the statement as a proper implication:

\\( \text{if you love formal logic } \rightarrow  \text{ Honk} \\)

... Now, do logic    
  

### Symbolic manipulation

For some problems, holding the information in our head and making sense of it is quite hard.  
Luckily, we have been building a _symbolic language_ that can take the place of "thoughts that make sense so far" so that  
we can continue doing our logical computation.

  
  

#### Precedence

We have accumulated some symbols:

* parentheses
* \\(\\neg\\)
* \\( \\wedge \\)
* \\(\\lor\\)
* \\(\\oplus\\)
* \\(\\rightarrow\\)
* \\(\\Leftrightarrow\\)

when several of the same operator are in a row (i.e. \\(a ∧ b ∧ c\\)), evaluate from left to right.  
  
(There are a couple of cases where this is not true, but we won't look at those here)

  
  

#### Curious Constructions: Tautology

  
**Activity 8** \[4 minutes\]: What can you tell about the following proposition?  
  
\\\[ (p \\lor q) \\wedge (\\neg q) \\rightarrow p \\\]

**Answer below**


   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky">p</th>
    <th class="tg-0pky">q</th>
    <th class="tg-0pky">p ∨ q</th>
    <th class="tg-0pky">¬q</th>
    <th class="tg-0pky">(p ∨ q) ∧ (¬q)</th>
    <th class="tg-0pky">(p ∨ q) ∧ (¬q) →p</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">1</td>
  </tr>
  <tr>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">1</td>
  </tr>
  <tr>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">1</td>
  </tr>
  <tr>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">1</td>
  </tr>
</tbody>
</table>


A Tautology is an assertion that is always true.  
In its most basic form, it is: 
<br>
q &or; p
        </p>
      </details>
    </span>
  </div>



  
  

#### Curious Constructions: Contradiction

  
**Activity 9** \[1 minute\]: What can you tell about the following proposition?  
  
\\\[ q \\wedge \\neg q \\\]



   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <i>This proposition is always false!</i>          
        </p>
      </details>
    </span>
  </div>
  

* * *

  

A Convincing Argument
---------------------

In spoken English we talk of "making a point".  
  
We usually "grant" said point when the person has made a convincing argument or revealed an unforeseen truth.  
  
As we mentioned before, using English leaves you exposed to ambiguity, contradictions, or language artifacts.  
  
In propositional logic, we can create a convincing argument using propositional logic by chaining together a series of boolean statements until we get to the desired conclusion.

  
  

#### A Logic puzzle

Aleks, Benita, Chas, and Dora are quadruplets, and they’ve all been invited to a birthday party. Unfortunately the quadruplets don’t get along very well:

* If Aleks goes to the party, then Benita will not go.
* If Chas goes to the party, then Aleks will not go.
* If Dora goes to the party, then Chas will not go.

**Activity 10** \[4 minutes, if we have time\]: What is the largest possible number that will go to the party?

  

* * *

  

Proofs
------

We will see a _very high-level intro_ to three types of proofs:  

* direct proofs (deduction)
* proof by contradiction
* proof by contrapositive

  
  

#### Direct proof [](https://en.wikipedia.org/wiki/Deductive_reasoning){:target="_blank"} Deduction

To quote Wikipedia: "Deductive reasoning goes in the same direction as that of the conditionals, and links premises with conclusions. If all premises are true, the terms are clear, and the rules of deductive logic are followed, then the conclusion reached is necessarily true."  
  
Example:  

* Yak is the best dog
* half of all dogs are better than all cats
* Therefore: Yak is better than all cats

  
  

#### Proof by [](https://en.wikipedia.org/wiki/Proof_by_contradiction){:target="_blank"} Contradiction

Start by assuming (taking as a true proposition) the opposite of what you wish to prove.  
Follow the normal rules of propositional logic and if:

* You arrive at a valid conclusion: you were wrong
* You arrive at a contradiction: then the opposite of your initial assumption is true (what you wanted to prove)

  
  
Example:  
Let's say we want to prove that: "there is no smallest rational number greater than 0"  
Using proof by contradiction, we say:

* "there is a smallest rational number r greater than 0"
* however, we can make a new number s = r/2 that is >0 since r > 0
* Since s < r, and s is a rational number, then r was **not** the smallest
* Therefore: "there is no smallest rational number r greater than 0"

  
  

#### Proof by [](https://en.wikipedia.org/wiki/Proof_by_contrapositive){:target="_blank"} Contrapositive

If we take an implication proposition as true, there is another proposition we can extract from it by performing some manipulations:  
  
To obtain the contrapositive of a proposition, we:

* negate both terms
* reverse the direction of inference

So if we have have the proposition \\( p \\rightarrow q \\), then, the steps are:

* negate both terms: \\( \\neg p \\rightarrow \\neg q \\)  --->**this is not correct...yet!**
* reverse the direction of inference: \\( \\neg q \\rightarrow \\neg p \\)  --->**this is the new proposition!**

  
  
So, both \\( p \\rightarrow q \\) and \\( \\neg q \\rightarrow \\neg p \\) are true.  
  
**Example**:  
Let's say we accept that: "For any integer k, if 3k + 1 is even, then k is odd."  
  
We could represent this symbolically:

* \\(p\\) is "3k + 1 is even"
* \\(q\\) is "k is odd"
* Then the phrase is: \\(\\forall k \\in \\mathbb{Z}, \\text{ } p \\rightarrow q \\)
* Then the contrapositive of the phrase is: \\(\\forall k \\in \\mathbb{Z}, \\text{ } \\neg q \\rightarrow \\neg p \\)
* Which translates to: "For any integer k, if k is not odd, then 3k + 1 is not even"
* OR more clearly: "For any integer k, if k is even, 3k + 1 is odd."

An example of a full proof by contrapositive would be:  
  
_Proof_: We will prove the contrapositive of this claim, i.e. that **for any integer k, if k is even, 3k + 1 is odd**.  
Suppose that k is an integer and k is even. Then, k = 2m for some integer m.  
Then 3k + 1 = 3(2m) + 1 = 2(3m) + 1.  
Since m is an integer, so is 3m. If we say n = 3m, Then 2(3m) + 1 = 2n + 1, which is an odd number.  
This means 3k + 1 = 2(3m)+1 = 2n + 1 = an odd number, which is what we needed to show.  
  
Example from the University of Illinois Urbana-Champaign, CS173

  

**Activity 11** \[4 minutes, if we have time\]:  
Prove the following statement: "Theorem: For any \\(n \\in \\mathbb{Z}\\), if \\(n^2\\) is even, then \\(n\\) is even."

  

* * *

  

Logical Errors
--------------

**Activity 12** \[4 minutes, if we have time\]:  
What is wrong with this statement:

If the weather is stormy, we can’t go swimming.  
If we can’t go swimming, we won’t go to the beach.  
We aren’t at the beach.  
Therefore, the weather must be stormy.

  
  

#### Converse

The **converse** of an implication is is the result of inverting the direction of the implication, so if:  
\\( p \\rightarrow q \\)  
  
The converse would be:  
\\( q \\rightarrow p \\)  
  
The error would be in believing that just because an implication is true, its converse is too.  
  
**Example**:  
"Petting dogs makes me happy.  
"I am happy, therefore I am petting a dog"  
OR (Jordan's example!) "Being happy makes me pet dogs."

  
  

#### Inverse

The **inverse** of an implication is is the result of inverting (negating) its propositions while maintaining the direction of the implication, so if:  
\\( p \\rightarrow q \\)  
  
The inverse would be:  
\\( \\neg p \\rightarrow \\neg q \\)  
  
The error would be in believing that just because an implication is true, its inverse is too.  
  
**Example**:  
"Petting dogs makes me happy.  
"I am not petting a dog, therefore I must not be happy"

**Activity 12** \[4 minutes, if we have time\]:  
Think about the following "puzzle":

A prosecutor in Logic Court (which is totally a thing) says to the defendant:  
"If you committed the crime, then you must have had an accomplice" (this is known).  
The defendant hotly denies that the _implication_ is true.  
  
Therefore, the jury (being apt logicians) convicts the defendant.  
  
Explain what happened in this story.

  
  

  

* * *

  

<!-- #### Homework

  
**\[Due for everyone\]**: Go over any exercises we did not do in class (participation opportunity next class!)  
Bring me questions and be ready to work in groups.  

Then, read the overleaf guide and check the tutorials mentioned below.
  
   -->

### Submitting Assignments in Latex using Overleaf

[Overleaf](https://www.overleaf.com/){:target="_blank"} is an online LaTeX editor.  
  
_What is LaTeX?_ you ask.  
From [https://www.latex-project.org/](https://www.latex-project.org/){:target="_blank"}:  

> _"LaTeX is a high-quality typesetting system; it includes features designed for the production of technical and scientific documentation. LaTeX is the de facto standard for the communication and publication of scientific documents."_
> 
> a lot of geeks like me (and you, soon enough)  

  

#### How to Learn LaTeX?

I will provide templates for every Assignment where you only need to fill-in what your answer is. Whether it is text-only, text with mathematical symbols, equations, or even diagrams, there is a way to do it in overleaf.  
  
Follow this [Oveleaf guide to learn LaTeX in 30 minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes){:target="_blank"}.  
  
Overleaf has a set of quicklinks on the right side that have most (if not all) of what you'll need. Some of the most important things are the [symbols](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols){:target="_blank"}!.  
  
Later on, we'll use the [FSM designer](https://madebyevan.com/fsm/){:target="_blank"} to make nice digrams like the ones shown below.  
  

* * *

Lecture Notes 02b: More Logic, Proofs, and Overleaf
====================================================


Recap: Logic and Logical Thinking
---------------------------------

  
  

* We use propositions as logical operands
* propositions are statements that have a truth value (either true or false).
* propositional logic allows us to _combine_ propositions, in a **logical computation**, to obtain valid conclusions, OR with which we can detect errors in the logical computation and refute a conclusion.
* We can operate on the propositions with logical operators:
    * Negation: \\( \\neg p\\)
    * AND (conjunction): \\( p \\wedge q\\)
    * OR (disjunction): \\( p \\lor q\\)
    * XOR (exclusive disjunction): \\( p \\oplus q\\)
    * Implication: \\( p \\rightarrow q\\)
    * IFF: \\( p \\leftrightarrow q \\)

  
  
  
  

#### Leftover Exercises:

Referring to **Implication**:  

**Activity 1** \[2 minutes\]: Can you draw the Venn Diagram for this one?

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <img class="img-fluid" src="../../../assets/images/csc250/lecture02/implication.png" alt="Implication" style="width:60%">          
        </p>
      </details>
    </span>
  </div>
  
  
  

Referring to **IFF: IF and Only IF**:  

**Activity 2** \[2 minutes\]: Can you draw the Venn Diagram for this one?  
  

If you look at the p, q, and p\\( \\Leftrightarrow \\)q columns, you might see something that looks familiar

  
  

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <img class="img-fluid" src="../../../assets/images/csc250/lecture02/iff.png" alt="if and only if" style="width:60%">          
        </p>
      </details>
    </span>
  </div>

  

#### Curious Constructions: Tautology

  
**Activity 3** \[4 minutes\]: What can you tell about the following proposition?  
  
\\\[ (p \\lor q) \\wedge (\\neg q) \\rightarrow p \\\]

**Answer below**


| p   | q   | p ∨ q | ¬q  | (p ∨ q) ∧ (¬q) | (p ∨ q) ∧ (¬q) →p |
| --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 1   | 0   | 1   |
| 0   | 1   | 1   | 0   | 0   | 1   |
| 1   | 0   | 1   | 1   | 1   | 1   |
| 1   | 1   | 1   | 0   | 1   | 1   |
  
A Tautology is an assertion that is always true.  
In its most basic form, it is: \\\[ q \\lor \\neg q \\\]


  
  

#### Curious Constructions: Contradiction

  
**Activity 4** \[1 minute\]: What can you tell about the following proposition?  
  
\\\[ q \\wedge \\neg q \\\]

   <div class="container mx-lg-5">
    <span style='color:#6f439a'>One possible answer: 
      <details><summary>(Wait; then Click)</summary>
        <p>
          <i>This proposition is always false!</i>          
        </p>
      </details>
    </span>
  </div>
  

* * *

  

What makes a Convincing Argument?
---------------------------------

In spoken English we talk of "making a point".  
  
We usually "grant" said point when the person has made a convincing argument or revealed an unforeseen truth.  
  
As we mentioned before, using English leaves you exposed to ambiguity, contradictions, or language artifacts.  
  
In propositional logic, we can create a convincing argument using propositional logic by chaining together a series of boolean statements until we get to the desired conclusion.

  
  

#### A Logic puzzle

Aleks, Benita, Chas, and Dora are quadruplets, and they’ve all been invited to a birthday party. Unfortunately the quadruplets don’t get along very well:

* If Aleks goes to the party, then Benita will not go.
* If Chas goes to the party, then Aleks will not go.
* If Dora goes to the party, then Chas will not go.

**Activity 5** \[4 minutes, if we have time\]: What is the largest possible number that will go to the party?

  

* * *

  

Proofs
------

We will see a _very high-level intro_ to three types of proofs:  

* direct proofs (deduction)
* proof by contradiction
* proof by contrapositive

  
  

#### Direct proof: [Deduction](https://en.wikipedia.org/wiki/Deductive_reasoning){:target="_blank"}

To quote Wikipedia: "Deductive reasoning goes in the same direction as that of the conditionals, and links premises with conclusions. If all premises are true, the terms are clear, and the rules of deductive logic are followed, then the conclusion reached is necessarily true."  
  
Example:  

* Yak is the best dog
* half of all dogs are better than all cats
* Therefore: Yak is better than all cats
* Here, a simple sketch might help with the clarity of the proof:  
    ![Yak is the best](../../../assets/images/csc250/lecture03/Yak-better-than-all-cats.png)

  
  

#### Proof by [](https://en.wikipedia.org/wiki/Proof_by_contradiction){:target="_blank"} Contradiction

Start by assuming (taking as a true proposition) the opposite of what you wish to prove.  
Follow the normal rules of propositional logic and if:

* You arrive at a valid conclusion: you were wrong
* You arrive at a contradiction: then the opposite of your initial assumption is true (what you wanted to prove)

  
  
**Example**:  
  
Let's say we want to prove that: "there is no smallest rational number greater than 0"  
(in other words: given a candidate, we can always find a smaller number)  
  
Using proof by contradiction, we say:

* "there **is** a smallest rational number r greater than 0"
* however, we can make a new number s = r/2 that is >0 since r > 0
* Since s < r, and s is a rational number, then r was **not** the smallest (**a contradiction**)
* Therefore: "there is no smallest rational number r greater than 0"

  
  

#### Proof by [](https://en.wikipedia.org/wiki/Proof_by_contrapositive){:target="_blank"} Contrapositive

If we take an implication proposition as true, there is another proposition we can extract from it by performing some manipulations:  
  
To obtain the contrapositive of a proposition, we:

* negate both terms
* reverse the direction of inference

So if we have have the proposition \\( p \\rightarrow q \\), then, the steps are:

* negate both terms: \\( \\neg p \\rightarrow \\neg q \\)    --->**this is not correct...yet!**
* reverse the direction of inference: \\( \\neg q \\rightarrow \\neg p \\)    --->**this is the new proposition!**

  
  
So, both \\( p \\rightarrow q \\) and \\( \\neg q \\rightarrow \\neg p \\) are true.  
  
**Example**:  
Let's say we accept that: "For any integer k, if 3k + 1 is even, then k is odd."  
  
We could represent this symbolically:

* \\(p\\) is "3k + 1 is even"
* \\(q\\) is "k is odd"
* Then the phrase is: \\(\\forall k \\in \\mathbb{Z}, \\text{ } p \\rightarrow q \\)
* Then the contrapositive of the phrase is: \\(\\forall k \\in \\mathbb{Z}, \\text{ } \\neg q \\rightarrow \\neg p \\)
* Which translates to: "For any integer k, if k is not odd, then 3k + 1 is not even"
* OR more clearly: "For any integer k, if k is even, 3k + 1 is odd."

An example of a full proof by contrapositive would be:  
  
_Proof_: We will prove the contrapositive of this claim, i.e. that **for any integer k, if k is even, 3k + 1 is odd**.  
Suppose that k is an integer and k is even. Then, k = 2m for some integer m.  
Then 3k + 1 = 3(2m) + 1 = 2(3m) + 1.  
Since m is an integer, so is 3m. If we say n = 3m, Then 2(3m) + 1 = 2n + 1, which is an odd number.  
This means 3k + 1 = 2(3m)+1 = 2n + 1 = an odd number, which is what we needed to show.  
  
Example from the University of Illinois Urbana-Champaign, CS173

  

**Activity 6** \[4 minutes, if we have time\]:  
Prove the following statement: "Theorem: For any \\(n \\in \\mathbb{Z}\\), if \\(n^2\\) is even, then \\(n\\) is even."

  
  
  
  

#### Proofs by Induction

  
Induction is a technique where we try to prove that some rule is true by showing that the rule holds for all possible cases.  
  
We do this in a clever way (not by actually trying all cases!)  
  
It is common for these "rules" that we want to prove true have "cases" that depend on an input of different natural number... so the cases are : \\( n=0, 1, 2, 3, ...\\)  
  

* First, we prove that the rule in question is true for its **base case** (sometimes that is \\(n=0\\) and sometimes \\(n=1\\).
* Then, we want to make the **induction hypothesis** that the rule works for some intermediate input value (case), say \\(n=k\\)
* Lastly, (the **induction step**) we must show that the rule also works for the case that follows the one from the Induction hypothesis: \\(n=k+1\\). We do this by relating the rule at the case \\(n=k+1\\) to the two previous "accepted" cases.

  
  
**Example 1**: Prove \\( 1+2+...+n = \\frac{n(n+1)}{2} \\) using a proof by induction.  
  

1.  **Case n=1:** \\( 1=1(2)/2=1 \\) checks.
  
  
4.  **Assume n=k holds:** \\( 1+2+...+k= \\frac{k(k+1)}{2} \\) (Induction Hypothesis)
  
  
7.  **Show n=k+1 holds:** \\( 1+2+...+k+(k+1)= \\frac{(k+1)((k+1)+1)}{2} \\)  
      
    * I just substitute k and k+1 in the formula to get these lines. Notice that I write out what I want to prove.
      
    * Now I start with the left side of the equation I want to show and proceed using the induction hypothesis and algebra to reach the right side of the equation.  
          
        \\( 1+2+...+(k+1) = 1+2+...+k+(k+1) \\) showing k and k+1 explicitly in the summation.
      
      
    * \\( = \\frac{k(k+1)}{2} + (k+1) \\) by the Induction Hypothesis
      
    * \\( = \\frac{k(k+1)+2(k+1)}{2} \\) second factor by 2/2 and distribution of division over addition
      
    * \\( = \\frac{(k+2)(k+1)}{2} \\) by distribution of multiplication over addition (we factored out \\( (k+1) \\))
      
    * \\( = \\frac{(k+1)(k+2)}{2} \\) by commutativity of multiplication
      
    * \\( = \\frac{(k+1)((k+1)+1)}{2} \\qquad\\qquad \\blacksquare \\qquad \\leftarrow \\) that symbol means "Q.E.D." (what we wanted to prove)

  

* * *

  

Logical Errors
--------------

**Activity 7** \[4 minutes, if we have time\]:  
What is wrong with this statement:

If the weather is stormy, we can’t go swimming.  
If we can’t go swimming, we won’t go to the beach.  
We aren’t at the beach.  
Therefore, the weather must be stormy.

  
  

#### Converse

The **converse** of an implication is is the result of inverting the direction of the implication, so if:  
\\( p \\rightarrow q \\)  
  
The converse would be:  
\\( q \\rightarrow p \\)  
  
The error would be in believing that just because an implication is true, its converse is too.  
  
**Example**:  
"Petting dogs makes me happy."  
"I am happy, therefore I am petting a dog"  
OR (Jordan's example!) "Being happy makes me pet dogs."

  
  
One way to prove this is by examining the table and noticing which information has been given:  
  
"Petting a dog" is \\(P\\)  
"Being Happy" is \\(H\\)  
"If I pet a dog I am happy." is \\(P \\rightarrow H\\)  
  
And we know that "I am Happy" or \\(H = 1\\)  
  
If we assume that the implication is true ( \\(P \\rightarrow H\\) ) we can examine the table to see if we know enough to state that "I must be petting a dog":  
  

| P   | H   | \\( P \\rightarrow H \\) |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 1   |

  
  
As you can see, the second and fourth rows are valid cases, and both have a different value for \\(P\\), which means we cannot know for sure that I am petting a dog (the converse is not necessarily true).  
  
  
  
  
  

#### Inverse

The **inverse** of an implication is is the result of inverting (negating) its propositions while maintaining the direction of the implication, so if:  
\\( p \\rightarrow q \\)  
  
The inverse would be:  
\\( \\neg p \\rightarrow \\neg q \\)  
  
The error would be in believing that just because an implication is true, its inverse is too.  
  
**Example**:  
"Petting dogs makes me happy.  
"I am not petting a dog, therefore I must not be happy"

  
  
**You should check the table for this case as well!**  
  
  
  

**Activity 8** \[4 minutes, if we have time\]:  
Think about the following "puzzle":

A prosecutor in Logic Court (which is totally a thing) says to the defendant:  
"If you committed the crime, then you must have had an accomplice" (this is known).  
The defendant hotly denies that the _implication_ is true.  
  
Therefore, the jury (being apt logicians) convicts the defendant.  
  
Explain what happened in this story.

  
  

  

* * *

  

If we have time: Overleaf and Latex vs Word
-------------------------------------------

Typesetting is not required: legibly-written-and-then-Typed (Word/OpenOffice/etc) submissions are totally fine;  
Just PDF them before you submit, please!  
  
However, LaTeX (Latex henceforth) is a powerful tool that lets you tweak and customize ad nauseam, which might be desirable to some of you.  
Also, it is the defacto standard for most academic publications.  
  
If you choose Latex, you should start very simply; learn:  

* Titles and Sections
* bold and Italics
* List Environments
* Math Environment and symbols


here are some links to help you with:

* [Mathematical Expressions](https://www.overleaf.com/learn/latex/Mathematical_expressions){:target="_blank"}
* [Mathematical symbols in Latex](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols){:target="_blank"}
* [Subscripts and Superscripts](https://www.overleaf.com/learn/latex/Subscripts_and_superscripts){:target="_blank"}
* [Brackets and Parentheses](https://www.overleaf.com/learn/latex/Brackets_and_Parentheses){:target="_blank"}
* [Fractions and Binomials](https://www.overleaf.com/learn/latex/Fractions_and_Binomials){:target="_blank"}
* [Aligning equations or statements](https://www.overleaf.com/learn/latex/Aligning_equations_with_amsmath){:target="_blank"}
* [Tables](https://www.overleaf.com/learn/latex/Tables){:target="_blank"}

  
  
I am happy to help with the formatting during office hours.

  
  

  

* * *

<!--   

#### Homework

Read the folowing Primer on proofs: [Proof Techniques](https://cs.stanford.edu/~jtysu/proofs.pdf){:target="_blank"}

**\[Team Assignments and Submissions]**: 

* Problem Sets can be worked in teams of 3 students (with previous approval).
* **Every person in the team submits** a write-up (a pdf output from Overleaf) to Moodle.

* Follow these requirements for all submissions:

1.  The names of all collaborating students be listed at the top of the submission.
    * The FIRST name should be the submitting student
    * The NEXT names are those of the OTHER members of the team
2.  A “References” section, with in-line citations to any resources you used.  
    If you did not use any resources, please state:  
    “I did not use any external resources in completing this assignment.”

* * *
 -->

### Submitting Assignments in Latex using Overleaf


<a href="https://www.overleaf.com/" target="_blank" rel="noopener noreferrer">Overleaf</a> is an online LaTeX editor.  
  
_What is LaTeX?_ you ask.  
From [https://www.latex-project.org/](https://www.latex-project.org/){:target="_blank"}:  

> _"LaTeX is a high-quality typesetting system; it includes features designed for the production of technical and scientific documentation. LaTeX is the de facto standard for the communication and publication of scientific documents."_
> 
> a lot of geeks like me (and you, soon enough)  

  
  

#### How to Learn LaTeX?

I will provide templates for every Assignment where you only need to fill-in what your answer is. Whether it is text-only, text with mathematical symbols, equations, or even diagrams, there is a way to do it in overleaf.  


Follow this [Oveleaf guide to learn LTeX in 30 minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes){:target="_blank"}.  
  
Overleaf has a set of quicklinks on the right side that have most (if not all) of what you'll need. Some of the most important things are the [symbols](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols){:target="_blank"}!.  
  
Later on, we'll use the [FSM designer](https://madebyevan.com/fsm/){:target="_blank"} to make nice digrams like the ones shown below.  
  

#### How to get started with HW1?

I will give you a template in Moodle. The template is a Zip of a tex file, which holds the latex source code for HW01. What you do is 

  1) download the zip, and 
  2) without unzipping, upload it to Overleaf (additional help/tutorials will be linked in Moodle).  
  
  
Overleaf lets you add a little bit of metadata info to a document to make it look better:  

![](../../../assets/images/csc250/lecture02/latex.png)
