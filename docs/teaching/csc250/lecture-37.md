---
layout: default
title: Lecture37
parent: CSC250
grand_parent: Teaching
nav_order: 37
#permalink: /docs/teaching/csc110/
---  

Lecture Notes 37: even Even More Poly-Time Reductions in NP-C
===================================================

  

Outline
-------

This class we'll discuss:

* Poly-time reductions in NP-Complete
* Work on PS06 - PS08

  

* * *

  

More reductions
---------------

  
  
![](../../../assets/images/csc250/lecture34/PolyRed-33.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture34/PolyRed-34.png){: width="80%"}  
  
  
  
  

**Activity** \[2 minutes\] How would you Prove this?:  
<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-34b.png" alt="CLIQUE proof" style="width:80%"><br>

<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-35a.png" alt="CLIQUE proof" style="width:80%"><br>

<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-35b.png" alt="CLIQUE proof" style="width:80%"><br>

<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-35c.png" alt="CLIQUE proof" style="width:80%"><br>

<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-35d.png" alt="CLIQUE proof" style="width:80%"><br>

<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-36.png" alt="CLIQUE proof" style="width:80%"><br>

<b>Upshot</b>:  
  
If you find k vertices connected in the graph, then they MUST be between vertices in different clauses, which means there is a combination that could be simultaneously TRUE in each clause... making $\Phi$ == True!

  

<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-37.png" alt="CLIQUE proof" style="width:80%"><br>  	
      </p>
    </details>
  </span>
</div> 

<br><br>
  
  
  

  



![](../../../assets/images/csc250/lecture34/PolyRed-38.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture34/PolyRed-39.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture34/PolyRed-40.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture34/PolyRed-41.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture34/PolyRed-42.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture34/PolyRed-43.png){: width="80%"}  
  
**TIP**:  
  
What is the most obvious vertex-cover of a graph $G$?  
  
What is the most obvious independent-set of a graph $G$?  
  
  
  
As you make the I-Set greater... what happens to the vertex-cover?  
  
Is there a maximum I-Set in a graph $G$?  
  
What is the relation with the vertex-cover of a graph $G$?  
  
  

**Activity** \[2 minutes\] How would you Prove this?:  
<div class="container mx-lg-5">
  <span style='color:#6f439a'>answer: 
    <details><summary>(Wait; then Click)</summary>
      <p>
<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-44.png" alt="CLIQUE proof" style="width:80%"><br> 	
<img class="img-fluid" src="../../../assets/images/csc250/lecture34/PolyRed-45.png" alt="CLIQUE proof" style="width:80%"><br>

  
<b>Upshot</b>:  
  
The largest I-Set must have, as its complement, the smallest vertex-cover!      
      </p>
    </details>
  </span>
</div> 

<br><br>
  

  
![](../../../assets/images/csc250/lecture34/PolyRed-46.png){: width="80%"}  
  
  
  
![](../../../assets/images/csc250/lecture34/PolyRed-47.png){: width="80%"}