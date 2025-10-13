---
title: "Graph Theory Exercise Bank"
collection: publications
category: discrete
permalink: /discrete/graphtheory
excerpt: 'I have listed many nice exercises in Graph Theory. Most of them are taken from past midterm exams and assignments'
date: 2025-10-12
order: 2
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Graph Theory Exercise Bank'
---

# Note: This site will be updated periodically. A paf version can be found here

# Graph Basics: Connectivity

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Exercise.</strong>  The compliment of a graph $G$, denote by $G^c$, is defined by the following: If $u,v \in V(G)$ are adjacent in $G$, then they are not adjacent in $G^c$; If $u,v \in V(G)$ are not adjacent in $G$, then they are adjacent in $G^c$. Show either $G$ or $G^c$ is connected.
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    If $E(G) = \varnothing$ or $G$ is connected, then we win. It suffices to show that $G$ is not connected but $E(G) \neq \varnothing$ will imply $G^c$ is connected. Take any $u,v \in V(G)$, then:

Case 1: If $u,v$ are not adjacent, then by definition $u,v$ is adjacent in $G^c$ and hence $u,v$ are connected;

Case 2: If $u,v$ are adjacent, then they belong to the same connected component $C$. Since we assume $G$ is not connected, so $\exists w \in V(G \setminus C)$, hence neither $u$ nor $v$ is adjacent to $w$, and hence in $G^c$, $u,w$ are adjacent, $v,w$ are adjacent. So there is a path $u \to w \to v$ and hence $u,v$ are connected.

Hence $G^c$ is connected.
  </div>
</details>
</div>





