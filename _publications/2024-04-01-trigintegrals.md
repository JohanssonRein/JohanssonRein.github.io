---
title: "Solving Trigonometric Integrals"
collection: publications
category: calculus
permalink: /publication/2024-04-01-trigintegrals
excerpt: 'In this article we will investigate different ways to solve trigonometric integrals'
date: 2024-04-01
venue: 'Summer'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024). Solving Trigonometric Integrals'
---

$\bullet$ Techniques used in this part:
u-Substitution and Integration by Parts

$\bullet$ u-Sub: $\int f(g(x)) g'(x) dx = \int f(u) du$ 
where $u = g(u)$  


$\bullet$ Integration by Parts: $\int f(x) g'(x) dx = f(x)g(x) - \int f'(x)g(x)dx$ 


$\bullet$ Trigonometric Properties:

**Derivatives and Integrals:**

$$ (\sin(x))' = \cos(x); (\cos(x))' = -\sin(x); (\tan(x))' = \sec^2(x) $$

$$ \int \sin(x) dx = -\cos(x) + C; \int \cos(x) dx = \sin(x) + C $$


**Half-Angle / Double Angle / Square and other properties:**

$$\sin(2x) = 2\sin(x)\cos(x)$$

$$\cos(2x) = 2\cos^2(x) - 1 = 1 - 2\sin^2(x)$$

$$\tan(2x) = \frac{2\tan(x)}{1 - \tan^2(x)}$$ 

$$\sin^2(x) = \frac{1}{2}(1 - \cos(2x))$$ 

$$\cos^2(x) =\frac{1}{2}(1 + \cos(2x))$$ 

$$\sin^2(x) + \cos^2(x) = 1$$

$$\sec^2(x) = 1 + \tan^2(x)$$

$$\sin{(2x)} = \frac{2\tan(x)}{1 + \tan^2(x)}$$

$$\cos{(2x)} = \frac{1 - \tan^2(x)}{1 + \tan^2(x)}$$ 

$$\sin(x)\cos(y) = \frac{1}{2}\left(\sin(x+y)+\sin(x-y)\right)$$

$$\sin(x)\sin(y) = -\frac{1}{2}(\cos(x+y)-\cos(x-y))$$

$$\cos(x)\cos(y)= \frac{1}{2}(\cos(x+y)+\cos(x-y))$$



**Integral of type 1 : $\int \sin^m(x)\cos^n(x) dx$**


Example 1 : Evaluate the integral $\int \cos^3(x) dx.$

We we may do
$\cos^3(x) = \cos^2(x) \cos(x) = (1-\sin^2(x))\cos(x)$. Then the integral we 
are evaluating will become $\int (1 - \sin^2(x))\cos(x)dx$. Now By
u-Substitution, we assume that $\sin(x) = u$, then we also know that 
$du = \cos(x)dx$, thus our integral can be written as 
$\int (1 - u^2)du$, which we can evaluate it since it's a
polynomial. Hence we have $\int (1 + u^2)du = 
u - \frac{1}{3}u^3 + C$, lastly we replace $u$ with 
$\sin(x)$, and we get $\int (1 - u^2)du = 
\sin(x) - \frac{1}{3}\sin^3(x) + C$



Exercise 1 : Evaluate the integral $\int \sin^5(x)\cos^2(x) dx.$


**General strategy for integrals like $\int \sin^m(x) \cos^n(x)dx$:**


(1) If we have $n = 2k + 1, k \in \mathbb{Z}$, rewrite as
$\int \sin^m(x)(1 - \sin^2(x))^{k}\cos(x) dx $


(2) If we have $m = 2k + 1, k \in \mathbb{Z}$, rewrite as
$-\int(1 - \cos^2(x))^{k}\cos^n(x)\sin(x) dx$


(3) Both $m,n$ are odd, then we can do for both $m,n$, by the same strategy.


(4) Both $m,n$ are even, then we use the formula (1)(2)(4)(5) to reduce the power



Exercise 2: Evaluate the integral $\int_0^{\pi}\sin^2(x)dx$



**Integral of type 2 : $\int \sec^m(x)\tan^n(x) dx$**

We may do the same, since we have $\sec^2(x) = 1 + \tan^2(x)$, and keep in mind, that

$$
\frac{d}{dx}\tan(x) = \sec^2(x); \frac{d}{dx}\sec(x) = \tan(x)\sec(x)
$$


Example 2 : Evaluate the integral $\int \tan^6(x)\sec^4(x)dx$

In this problem, we rewrite the original integral as 
$\int \tan^6(x) (1 + \tan^2(x))\sec^2 (x)dx$, and we let $u = \tan(x)$,
thus we know $du = \sec^2(x)dx$, then it becomes $\int u^6
(1+u^2)du$, which can be calculated as 
$\int u^6
(1+u^2)du} = \frac{1}{7}\tan^7(x)+\frac{1}{9}\tan^9(x)+C$



Exercise 3 : Evaluate the integral $\int \tan^5(x)\sec^7(x) dx$.


Exercise 4 : Evaluate the integral $\int \sec(x) dx.$


Exercise 5 : Evaluate the integral $\int \sec^3(x) dx.$
 

**MORE EXERCISES ON INTEGRATION**

$\bigstar \bigstar $ Evaluate the integral $\int \frac{\sin(2x)}{1+\cos^2(x)}dx$


$\bigstar \bigstar \bigstar$ Evaluate the integral $\int \frac{1}{1-\cos(x)}dx$


$\bigstar \bigstar \bigstar \bigstar \bigstar$ Evaluate the integral $\int \sqrt{(\tan(x))}dx$


**Trigonometric Substitution**


Example 3 : Evaluate the integral $\int \frac
{1}{x^2\sqrt{x^2 + 4} dx.$

In forms like this, we will perform a trig-sub to simplify the 
terms inside the square root. Usually we do $\sec(x)$ sub if inside the square 
root there is $ax^2 + b$, and we do $\sin(x)$ or $\cos(x)$ sub if inside the 
square root there is $ax^2 - b$. In this problem, we will do $\sec(x)$ sub.
If we let $x = 2\tan(y)$, then we have $x^2 + 4 = 4\tan^2(y) + 4 = 
4\sec^2(y)$, and we have $dx = 2\sec^2(y)dy$, so the integral now becomes
$\int \frac{2\sec^2(y)}{4\tan^2(y)(2\sec(y))}dy$, which is 
$\frac{1}{4}\int \frac{\sec(y)}{\tan^2(y)}dy$, if we let 
$\tan(y) = \sin(y) / \cos(y)$ and $\sec(y) = 1 / \cos(y)$, we will get 
$\frac{1}{4}\int \frac{\cos(y)}{\sin^2(y)}dy$, and we can achieve this 
by another u-sub, let $u = \sin(y)$ thus we get 
$\frac{1}{4}\int \frac{\cos(y)}{\sin^2(y)}dy = 
\frac{1}{4} \int \frac{1}{u^2}du}$, 
which we get 
$ 
\frac{1}{4} \int \frac{1}{u^2}du = -\frac{1}{4}\csc(y) + C$, then 
we perform the last step, by the equation $x = 2\tan(y)$, we solve 
$\csc(y)$ in terms of $x$, which we get $-\frac{\sqrt{x^2 + 4}}{4x} + C$



Exercise 6 : Evaluate the integral $\int \frac{x}{\sqrt{x^2 + 4}}dx.$


Exercise 7 : Evaluate the integral $\int_0^a \frac{1}{(a^2 + x^2)^{3/2}} dx.$


Exercise 8 : Evaluate the integral $\int \frac{x}{\sqrt{3-2x-x^2}} dx.$







