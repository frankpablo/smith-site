---
layout: default
title: LectureMidterm01
parent: CSC250
grand_parent: Teaching
nav_order: 233
#permalink: /docs/teaching/csc110/
---  

Lecture Notes : Midterm Study
=============================================================

## Outline ##


This class we'll discuss:


* Prep for the Midterm
 

* * *

A Slideshow:
---------------

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRCYI_ZMDXnE7v6udVGCSNb7eFjUFEpoH5d5fp3GASef8bcGj7KxNBtEa0l0Y-WgNYXIqffn03YvlAW/embed?start=false&loop=false&delayms=60000" frameborder="0" width="800" height="629" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>


---




GUIDED NOTES (Optional)
=======================



* * *

Prep For Midterm
-------------------------------------
<!-- 
  * The midterm is Self-Scheduled starting today
  * The link with the info: [SS-Exams](https://www.science.smith.edu/self-scheduled-exam-printing/#students)
  * The exam is individual, and will contain multiple-choice as well as free-answer questions.
  * It will be designed for 1.5 hours and you'll have 3 hours to complete it.
  * A single (double sided) aid-sheet will be allowed and you must turn it in.
  * The subjects covered are:
 -->

### Topics  
  

1.  **Regular Languages**  
    * Regular Expressions: from set description to RE
    * Regular Expressions: from RE to set description
    * Finite Automata: Interpreting an FA (parts, equivalent RE, and accepted Language)
    * Finite Automata: Building a FA given a language set description
  
2.  **Regular vs Non-Regular Languages**  
    * Short Proofs: using definitions
    * Short Proofs: using closure
    * Short Proofs: finding a simple RE or FA
  
3.  **Non-Regular Languages (NRLs)**  
    * Understand the difference/relation between regular and non-regular languages
    * Prove a given Language is NOT regular (Pumping Lemma is useful here)
  
4.  **Context-Free Languages (CFLs)**  
    * Understand the definition of CFGs and Push-Down Automata
    * Understand the difference/relation between regular and CFG-languages
    * Understand the relation between Push-Down Automata and CFG-languages
    * Prove a given Language IS context free
    * Understand how one WOULD Prove a given Language is NOT context free
    * Short Proofs: using definitions
    * Short Proofs: using closure
    * Short Proofs: finding a simple CFG or PDA

 
5. **Turing-Decidable Languages (TDLs)**  
    * Understand the definition of Turing Machines
    * Understand the difference/relation between regular, CFG-languages, and TDLs
    * Prove a given Language IS Decidable
    * Short Proofs: using definitions
    * Short Proofs: using closure
    * Short Proofs: finding a simple TM


* * *

  

### Exam Info  
  

* **Where/How to take the exam**:  
    Please read the full instructions in [self-scheduled-exams](https://www.science.smith.edu/self-scheduled-exam-printing/#students)
  
* **Cheat-Sheet**  
    
    * A single approved cheatsheet will be distributed. You can ONLY bring that single page *AND* you must submit it with your exam at the end!
    
    Note that the exam is designed so that you must use your reasoning rather than memory or copied notes.
  
* **Exam Structure and Requirements**  
    * The exam will have 7 questions covering the topics mentioned above
    * it is graded on 50 points but there are 60 points available to you (you keep any extra points you earn towards HW grades)
    * It is designed to be completed in 1 hour and 30 minutes but you'll have up to 3 hours to complete it
    * You may scribble notes and practice answers anywhere in the exam but MUST indicate your final reply clearly, otherwise the whole scribbling will be taken as your reply
    * You MUST use clear sentences and logic. Rambling answers do not grant partial credit so be concise and precise (think before you answer)


* * *

  
### General tips  
  

* See the examples solved in class and those solved in the Problem Sets. Any questions that come in the exam will be VERY similar to those.
  
* You will be asked to do proofs, but they will be rather straightforward.  
    Examples:  
    - show an example of an RE that disprooves a statement that there can be none  
    - use a Pumping Lemma proof on a question that is VERY similar to one seein in class (HALF)  
    - show a CFG to generate a certain Language

  

* * *

  

### Tips on Proofs  
  
If you want to prove a statement like “This $ something $ is NOT in the category $ category $” (Like this Language L is NOT a Regular Language), you can use the following approaches:  

* by contradiction (assume it IS and ﬁnd a contradiction. . . for example, using the Pumping Lemma)
* by construction (show all elements follow some structure that precludes them from falling inside the $ category $)

  
  
If you want to disprove a statement like 

“There is NO $something$ that has the property $\text{some property}$” 

<b>Example</b>: there is no Regular Expression that can describe language 

$$L = {w \vert w \text{ has alternating 1s and 0s} }$$

* you only need to ﬁnd an example.

  
  
If you want to prove that a set of elements follows some property (like saying “these two languages are equivalent” or “This language L is Context-Free”), you might want to use one of the following approaches:

* using closure properties
* by construction (show how you can generate the rules that produce the set)
* by induction

  

* * *