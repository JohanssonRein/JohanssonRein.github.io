---
title: "Testing Series"
collection: publications
category: calculus
permalink: /publication/series
excerpt: 'In this article we will investigate different ways to test the convergence of series'
date: 2024-04-10
venue: 'Summer'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024). Testing Series'
---


**1. Limit Test**


**Theorem** Let $(a_n)$ be an infinite series, if $\displaystyle{\sum_{n = 1}^{\infty} a_n}$ converges, then
$\displaystyle{\lim_{n \rightarrow \infty} a_n= 0}$.

It is important to know that the reverse is not true.

**Theorem** Let $(a_n)$ be an infinite series, if $\displaystyle{\lim_{n \rightarrow \infty} a_n \neq 0}$ or doesn't exist, then $\displaystyle{\sum_{n=1}^{\infty} a_n}$ diverges.


**Exercises:**

Justify if the following series converge or diverge. 


1. $$\sum_{n=1}^{\infty}\frac{n^2}{5n^2 + 4}$$

3. $$\sum_{n=1}^{\infty} (\frac{1}{\sqrt{n}} - \frac{1}{\sqrt{n+1}})$$

4. $$\sum_{n=2}^{\infty} \frac{1}{n^3 - n}$$


**2. Integral Test**

**Theorem** Let $(a_n)$ be an infinite series, and $f(x)$ is a continuous function defined on $(0,\infty)$.
If for all positive integer $n$, we have $a_n = f(n)$, then by integral test, we say 
$\displaystyle{\sum_{n = 1}^{\infty} a_n}$ converges if the followings hold:

1. $f(x) \geq 0$ for all $n \geq 1.$

2. $f(x)$ is decreasing on $(a,\infty)$ for some $a \geq 1$, and $\lim_{n \rightarrow \infty}
f(x) = 0$.

3. $\displaystyle{\int_1^{\infty} f(x) dx}$ converges.


**Exercises :**
Justify if the following series converge or diverge.


1. $\sum_{n=1}^{\infty} \frac{1}{n^2 + 1}$


2. $\sum_{n=1}^{\infty} \frac{\ln (n)}{n}$


3. $\sum_{n=1}^{\infty} ne^{-n^2}$

4. Find the values of $p$, such that the series $\displaystyle{\sum_{n=1}^{\infty} n(1+n^2)^p}$
is convergent.



**3. Comparison Test**

**Theorem** Let $(a_n), (b_n)$ be \textbf{positive}, infinite series with the property that $a_n \leq b_n$, then

1. If $\displaystyle{\sum_{n=1}^{\infty} b_n}$ is convergent, then $\displaystyle{\sum_{n=1}^{\infty} a_n}$ is convergent.


2. If $\displaystyle{\sum_{n=1}^{\infty} a_n}$ is divergent, then $\displaystyle{\sum_{n=1}^{\infty} b_n}$ is divergent.


**Exercises:** Justify if the following series converge or diverge. 


1. $\displaystyle{\sum_{n=1}^{\infty} \frac{5}{2n^2 + 4n + 3}}$

2. $\displaystyle{\sum_{n=1}^{\infty} \frac{\ln (n)}{n}}$


**Theorem** Let $(a_n), (b_n)$ be positive, infinite series, if $\displaystyle{\lim_{n \rightarrow \infty}\frac{a_n}{b_n}}$ exists, then both $\displaystyle{\sum_{n=1}^{\infty} a_n}$ and $\displaystyle{\sum_{n=1}^{\infty} b_n}$ converges or diverges.


**Exercises :** Justify if the following series converge or diverge.


1. $\displaystyle{\sum_{n=1}^{\infty} \frac{1}{2^n - 3}}$

2. $\displaystyle{\sum_{n=1}^{\infty} \sin(\frac{1}{n^2})}$


**4. Alternating Series Test**

**Theorem**
Let $(b_n)$ be an infinite series where $b_n \geq 0$ for all $n$, if $b_{n+1} \leq b_n$ and 
$\lim_{n \rightarrow \infty} b_n = 0$, then $\displaystyle{\sum_{i=1}^{\infty} (-1)^{n} b_n}$ and
$\displaystyle{\sum_{i=1}^{\infty} (-1)^{n+1} b_n}$ converge.



**Exercises :** Justify if the following series converge or diverge.


1. $\displaystyle{\sum_{n=1}^{\infty}(-1)^n \frac{1}{n}}$

2. $\displaystyle{\sum_{n=1}^{\infty}(-1)^{n+1} \frac{n^2}{n^3+1}}$


**Definition :** Let $(a_n)$ be an infinite series, the sum $\displaystyle{\sum_{n=1}^{\infty} a_n}$ is called **absolutely convergent** if $\displaystyle{\sum_{n=1}^{\infty} \vert a_n \vert}$ converges.
Series that converge but not absolutely converge are called **conditionally convergent**.


**Exercise :**
Test the sum $\displaystyle{\sum_{n=1}^{\infty} \frac{\cos(n)}{n^2}}$. 




**5. Ratio Test and Root Test**

**Theorem**
Let $(a_n)$ be an infinite series, define $L = \displaystyle{\lim_{n \rightarrow \infty} \Big| 
\frac{a_{n+1}}{a_n} \Big|}$, then:

1. If $L < 1$, then $\displaystyle{\sum_{n = 1}^{\infty} a_n}$ is absolutely convergent. 

2. If $L > 1$, then $\displaystyle{\sum_{n = 1}^{\infty} a_n}$ is divergent.

3. If $L=1$, then the ratio test is inconclusive



**Exercises :** Justify if the following series converge or diverge.


1. $\displaystyle{\sum_{n=1}^{\infty}\frac{(-10)^n}{4^{2n+1}(n+1)}}$

2. $\displaystyle{\sum_{n=1}^{\infty}\frac{n^n}{n!}}$


**Theorem**
Let $(a_n)$ be an infinite series, define $L = \displaystyle{\lim_{n \rightarrow \infty} \sqrt[n]{\vert a_n \vert}}$, then:

1. If $L < 1$, then $\displaystyle{\sum_{n = 1}^{\infty} a_n}$ is absolutely convergent. 

2. If $L > 1$, then $\displaystyle{\sum_{n = 1}^{\infty} a_n}$ is divergent.

3. If $L=1$, then the root test is inconclusive
\end{theorem}

**Exercises :** Justify if the following series converge or diverge.

1. $\displaystyle{\sum_{n=1}^{\infty}\frac{n^{n+1}}{3^{2n+1}}}$\\

More series tests like Dirichlet's test, Abel's test, Weierstrass M-test, are beyond the slope of this course and  hence will not be introduced. You can look it up if you are interested.


**6. Strategy for Testing Series**

1. If $(a_n)$ is of the form $\displaystyle{ \frac{1}{n^p}}$, then, we should know that 
$\displaystyle{\sum a_n}$ converges for $p>1$ and diverges for $p \leq 1$, also if $(a_n)$ is a geometric series, then we can use the formula to find its sum.

2. If $(a_n)$ has a form which is similar to $p$-series or geometric series, then we can try to use comparison tes

3. If $\lim_{n \rightarrow \infty} a_n \neq 0$, then $(a_n)$ is divergent.

4. If $(a_n) = (-1)^n b_n$, then we shall apply alternating series test.

5. If inside $(a_n)$ there are terms like $n!$, or some products related to $n$, then we shall consider ratio test.

6. If $a_n = (b_n)^n$. then we shall consider root test.

7. If $a_n = f(n)$ for some positive elementary function $f(x)$, if it is easy to integrate $f(x)$,
we shall consider integral test.

**Exercises :**
Justify if the following series converge or diverge.


1. $\displaystyle{\sum_{n=1}^{\infty}\frac{\sqrt{n^3+1}}{3n^3 + 4n^2 + 2}}$

2. $\displaystyle{\sum_{n=0}^{\infty} (-1)^n\frac{\pi^{2n}}{(2n)!}}$

3. $\displaystyle{\sum_{n=1}^{\infty} \frac{n \ln (n)}{(1+n)^3}}$


4. $\displaystyle{\sum_{n=1}^{\infty} \frac{\sin(2n)} {1+2^n}}$

5. $\displaystyle{\sum_{n=1}^{\infty} \frac{e^{1/n}}{n^2}}$

6. $\displaystyle{\sum_{n=1}^{\infty} \frac{1}{n + n \cos^n (n) }}$


7. $\displaystyle{\sum_{n=1}^{\infty} \frac{1} {\tan(n)}}$

8. $\displaystyle{\sum_{n=1}^{\infty} \frac{5^n}{3^n+4^n}}$
9. 
10. $\displaystyle{\sum_{n=1}^{\infty} \frac{1}{(n+1)\sqrt{n^2 + 1}}}$


**7. Power Series, Radius of Convergence and Interval of Convergence**


**Theorem**
For any given power series $a_n = \displaystyle{\sum_{n=0}^{\infty} c_n(x-a)^n}$,
there are only three possibilities:

1. The series converges only when $x=a$;

2. The series converges for all $x$;

3. There exists a positive number $R$ such that the series converges if
$\vert x - a \vert < R$ and diverges if $\vert x - a \vert > R$. In this case, $R$ is 
called the \textbf{radius of convergence}. The interval of convergence is one of 
$(a-R,a+R);(a-R,a+R];[a-R,a+R);[a-R,a+R]$, depending on the convergence of boundary points.



**Exercises :**

1. For what values of $x$ is the series $\displaystyle{\sum_{n=0}^{\infty} n!x^n}$ convergent?

2. For what values of $x$ is the series $\displaystyle{J_0(x) = \sum_{n=0}^{\infty} 
\frac{(-1)^n x^{2n}}{2^{2n}(n!)^2}}$ convergent?


3. Find the radius of convergence and the interval of convergence of the series 
$\displaystyle{\sum_{n=1}^{\infty} (-1)^n\frac{x^n}{\sqrt[3]{n}}}$







