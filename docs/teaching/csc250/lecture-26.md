---
layout: default
title: Lecture26
parent: CSC250
grand_parent: Teaching
nav_order: 360
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 26: Computational Complexity
==========================================

  

Outline
-------

This class we'll discuss:

* Recap: Can we do it?
* Computational Complexity

  
* * *

A Slideshow:
---------------

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRE3qiRuWkorQH9jGSHvNb2uS9jcn1UMbrz5y34fhDiK0vx5Zbm843IJgV4bEhrofGPWhSOitH-dnQE/embed?start=false&loop=false&delayms=60000" frameborder="0" width="800" height="629" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

---



GUIDED NOTES (Optional)
=======================

  

Recap: Is this problem doable?
------------------------------

  
  
![](../../../assets/images/csc250/lecture29/Complex-09.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-10.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-11.png){: width="80%"}    
  
The problem: Is there some way to set these boolean values so the whole thing evaluates to TRUE?  
  
![](../../../assets/images/csc250/lecture29/Complex-12.png){: width="80%"}    
  
The problem: Pattern matching  
  
![](../../../assets/images/csc250/lecture29/Complex-13.png){: width="80%"}    
  
The problem: More powerful pattern matching  
  
![](../../../assets/images/csc250/lecture29/Complex-14.png){: width="80%"}    
  
Restricted notion of “computation”

* no memory
* only get to read once
* exactly the same class of languages as REs

  
  
![](../../../assets/images/csc250/lecture29/Complex-15.png){: width="80%"}    
  
Very general notion of computation

1.  unlimited storage
2.  multiple passes over the input
3.  can compute for as long as you like (doesn’t even have to be guaranteed to stop)
4.  Large, sweeping language classes: turing decidable, turing recognizable = enumerable

  
  
![](../../../assets/images/csc250/lecture29/Complex-16.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-17.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-18.png){: width="80%"}    
  
Here’s the thing: just knowing that it is POSSIBLE to compute a solution to a problem doesn’t give us any information about how difficult that problem is. The only information we have is… it is not impossible.  
  
That level of **resolution** is not great.  
  
  
  
What else would be useful to know (in addition to the fact that a problem is solvable)?

  
  
  

* * *

  
  
  
  
Complexity

  
  
![](../../../assets/images/csc250/lecture29/Complex-19.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-20.png){: width="80%"}    
  


<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
$HALF = \{w | w = 0^i1^i, i \leq 0\}$
      </p>
    </details>
  </span>
</div> 

<br><br> 
  


  
  
![](../../../assets/images/csc250/lecture29/Complex-21.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-22.png){: width="80%"}    
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
Depends on the particular input.
      </p>
    </details>
  </span>
</div> 

<br><br> 


  
  
![](../../../assets/images/csc250/lecture29/Complex-23.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-24.png){: width="80%"}    
  
How long will it take for this input?  
  
How about for "01", "0011", "00001111" ... ?  
  
![](../../../assets/images/csc250/lecture29/Complex-25.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-26.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-27.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-28.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-29.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-30.png){: width="80%"}    
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
Initial check (steps 1 and 2) takes 2n steps (n to read, and n to get back)  
We could have at most n/2 passes over step 3 (because we mark off two letters each time)  
And to make things easier, let’s say we read the whole string each pass  
$2n + (n/2)*2n = 2n + n^2$ steps to accept
      </p>
    </details>
  </span>
</div> 

<br><br>  


  
  
![](../../../assets/images/csc250/lecture29/Complex-31.png){: width="80%"}    
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
$\mathcal{O}( n^2 )$
      </p>
    </details>
  </span>
</div> 

<br><br>  
  


  
  
![](../../../assets/images/csc250/lecture29/Complex-32.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-33.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-34.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-35.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-36.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-37.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-38.png){: width="80%"}    
  
Try modifying the algorithm with a more **efficient** one  
  
![](../../../assets/images/csc250/lecture29/Complex-39.png){: width="80%"}    
  

<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
  3. Copy all the 0s to a second tape  
  4. Move the two heads together, counting off a 1 and a 0 each step  
  5. If you hit the end of both tapes at the same time ACCEPT, otherwise REJECT”  
  
2n steps for lines 1 and 2  
n steps for line 3  
n steps for line 4  
$= 4n = \mathcal{O}(n)$    
      </p>
    </details>
  </span>
</div> 

<br><br>

  

  
![](../../../assets/images/csc250/lecture29/Complex-40.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-41.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-42.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-43.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-44.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-45.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-46.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-47.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-48.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-49.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-50.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-51.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-52.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-53.png){: width="80%"}    
  
  
  
![](../../../assets/images/csc250/lecture29/Complex-54.png){: width="80%"}  



