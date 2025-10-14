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


* I have sorted many good exercises into different topics.

* Exercises are taken from past assignments, midterm and final exams.

* This site will be updated periodically. A pdf version can be found [here](/files/350_exercises.pdf).

<br>

# Part One: Graph Basics: Connectivity

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Exercise 1.</strong>  The compliment of a graph $G$, denote by $G^c$, is defined by the following: If $u,v \in V(G)$ are adjacent in $G$, then they are not adjacent in $G^c$; If $u,v \in V(G)$ are not adjacent in $G$, then they are adjacent in $G^c$. Show either $G$ or $G^c$ is connected.
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    If $E(G) = \varnothing$ or $G$ is connected, then there is nothing to show and the result is immediate. It suffices to show that $G$ is not connected but $E(G) \neq \varnothing$ will imply $G^c$ is connected. Take any $u,v \in V(G)$, then:

Case 1: If $u,v$ are not adjacent, then by definition $u,v$ is adjacent in $G^c$ and hence $u,v$ are connected;

Case 2: If $u,v$ are adjacent, then they belong to the same connected component $C$. Since we assume $G$ is not connected, so $\exists w \in V(G \setminus C)$, hence neither $u$ nor $v$ is adjacent to $w$, and hence in $G^c$, $u,w$ are adjacent, $v,w$ are adjacent. So there is a path $u \to w \to v$ and hence $u,v$ are connected.

Hence $G^c$ is connected.
  </div>
</details>
</div>

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Exercise 2.</strong>  Let $T$ be a tree with $n$ vertices, if there exists $v \in V(T)$ with $\deg_T(v)=k$, show $T$ has at least $k$ leaves.
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>

   If $n=0$ then there is nothing to show. We assume $T$ has at most $k-1$ leaves, and we can even let $k$ be the largest degree. Then by handshaking lemma we have

   $$
\begin{align}
2|E(T)| &= \sum_{v \in V(T)} \deg(v)\\
&\leq k-1+\sum_{v \in V(T),\deg(v)>1} \deg(v)\\
&\leq k-1+(n-k+1)k
\end{align}
$$

also we know $T$ is a tree so $|E(T)|+1=|V(T)|$ and we indeed have $2n-2 \leq k-1+(n-k+1)k$. Fix $n$ and we have

$$
2n-2 \leq -k^2+(n+2)k-1
$$

as a function of $k$ where $k \in\mathbb{N}$. Let $f(k) = -k^2+(n+2)k-1$, it is a parabola which obtains its maximum at $k=n+2$. However $f(2n+2) = -(n+2)^2 +(n+2)(n+2)-1=-1$ and $2n-2 \leq -1$ iff $n=0$, a contradiction.
  </div>
</details>
</div>

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Exercise 3.</strong>  Let $G$ be a simple graph such that each vertex has degree at least $k$. Show that $G$ has a cycle with length at least $k$.
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>

   Let $P$ denote the longest path in $G$ and $v$ to be one end. We claim that all neighbors of $v$ must be on $P$ otherwise we can make the path longer. Then denote $u$ to be the furthest neighbor of $u$ on the path $P$, then along the path $P$ the distance from $u$ to $v$ is $k-1$, plus $u$ is connected to $v$ by an edge $e$, then $P$ along with $e$ is the path of desired length (shortest).
  </div>
</details>
</div>

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Exercise 4.</strong>  Denote $g(G)$ to be the length of the shortest cycle in $G$. Show that if $G$ contains a cycle then $g(G) \leq 2diam(G)+1$.
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>

  Assume such a shortest cycle has length at least $2diam(G)+2$, then $\exists u,v \in V(C)$ such that their distance on $C$ is at least $\diam(G)+1$. Then use the definition in $G$ any path $P$ with ends $u,v$ has length at most $diam(G)$ and hence it follows that $P \subsetneq C$ and hence $P$ along with the shorter $x-y$ path in $C$ will form a shorter circle and that's a contradiction (overlapping of vertices are possible but that will make our cycle even shorter).
  </div>
</details>
</div>








