---
layout: default
#title: Lecture31
parent: CSC250
grand_parent: Teaching
nav_order: 410
published: false
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 31: Complexity and NP-Completeness
==========================================================

  

Outline
-------

This class we'll discuss:

* NP-Completeness

  

* * *


Recap: Computational Complexity
-------------------------------

  
  
![](../../../assets/images/csc250/lecture31/NPC-02.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-03.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-04.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-05.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-06.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-07.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-08.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-09.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-10.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-11.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-12.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-13.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-14.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-15.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-16.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-17.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-18.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-19.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-20.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-21.png){: width="80%"}   
  

**Activity 1** \[2 minutes\] How would you Prove this?:  
  
<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
To show a language is in NP using a verifier:  

  <ul>
      <li>Specify a certificate that can be used with a verifier to decide the language.  </li>
      <li>Give a verifier that uses that certificate to verify membership in the given language.  </li>
      <li>Prove that the language recognized by the verifier is the given language and that the verifier runs in polynomial time.</li>
  </ul>


<b>Certificate</b>: a graph and a set of k vertices we claim is a cliquebr Verifier: loop over all pairs in the set and check to make sure there’s an edge between them, and if so: ACCEPT - O(k^2) (can’t be bigger than n^2)
      </p>
    </details>
  </span>
</div> 

<br><br>
  
![](../../../assets/images/csc250/lecture31/NPC-22.png){: width="80%"}   
  

**Activity 2** \[2 minutes\] How would you Prove this?: 

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
<b>Nondeterminism</b>: we can try multiple “branches” of computation at once  
  
The trick: each branch can only take polynomial time  
  
Nondeterministically test all subsets of vertices. On each subset:  
loop over all pairs in the (sub)set and check to make sure there’s an edge between them, and if so: ACCEPT - O(n^2)  
if no branch accepts REJECT  
  
  
Guaranteed to halt? YES (there’s nowhere to get stuck)  
  
What would happen if we tried to serialize all the branches?  

  <ul>
      <li>how many possible subsets do we have to check? $2^n$ <-- not polynomial anymore  </li>
      <li>note: this just means that this particular algorithm doesn’t run in polynomial time, but it turns out we haven’t been able to find any polynomial-time deciders for this language</li>
  </ul>
      </p>
    </details>
  </span>
</div> 

<br><br>

  
![](../../../assets/images/csc250/lecture31/NPC-23.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-24.png){: width="80%"}   
  
  
  
![](../../../assets/images/csc250/lecture31/NPC-25.png){: width="80%"} 