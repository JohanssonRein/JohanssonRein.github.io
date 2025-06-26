---
title: "Harmonic Functions"
collection: publications
category: differentialequations
permalink: /publication/harmonicfunctions
excerpt: 'In this article we will investigate some properties of harmonic functions and fundamental solutions to the Laplace equations.'
date: 2025-06-25
venue: 'Summer'
#slidesurl: 'http://academicpages.github.io/files/slides2.pdf'
#paperurl: 'http://academicpages.github.io/files/paper2.pdf'
citation: 'Jiajun Zhang, (2025). Harmonic Functions'
---

# Laplace's Equations and Harmonic Functions

## Fundamental Solutions of Harmonic Functions

**Definition**
Let $u(x_1,\cdots,x_n): U \subset \mathbb{R}^n \to \mathbb{R}$ be a unknown function, the Laplacian of the function is defined by
$$
\Delta u = \sum_{i=1}^n \frac{\partial^2 u}{\partial x_i^2}.
$$
Laplace equation is of the form
$$
\Delta u = 0
$$
for all $x \in U$, any function satisfying the above is also called harmonic.


**Lemma**
Laplace's equation is invariant under rotation, i.e if $P$ is an orthogonal matrix with entries $p_{ij}$, then $\Delta u(Px) = 0$ for all $x\in U$.


**Proof**
By Chain rule, we have

$$
D_{x_i} (u(Px)) = \sum_{k=1}^n D_{x_k}(u(Px) p_{ik})
$$

and similarly

$$
D_{x_i x_j} (u(Px)) = \sum_{l=1}^n \sum_{k=1}^n D_{x_k x_l} (u(Px) p_{ik} p_{il}).
$$

Since $P$ is orthogonal, thus $p_{ik} p_{il} = 1$ iff $k=l$ and hence

$$
\Delta u(Px) = \sum_{i=1}^n\sum_{l=1}^n \sum_{k=1}^n D_{x_k x_l} (u(Px) p_{ik} p_{il} ) = \Delta u = 0.
$$

QED.

Given this, we seek for radial solutions which takes the form $u(x) = v(r)$ where $r = |x|$. Denote $r = (x_1^2+\cdots+x_n^2)^{1/2}$, let $x\neq 0$, then we see that

$$
\frac{\partial r}{\partial x_i} = (x_1^2+\cdots+x_n^2)^{-1/2} x_i = \frac{x_i}{r}
$$

and by Chain rule we have

$$
u_{x_i} = v'(r) \frac{x_i}{r}
$$

$$
u_{x_i x_i} = v''(r) \frac{x_i^2}{r^2} + v'(r) \frac{r-x_i \frac{x_i}{r}}{r^2} = v''(r) \frac{x_i^2}{r^2} + v'(r) \left( \frac{1}{r} - \frac{x_i^2}{r^3} \right)
$$

using the fact that $x_1^2+\cdots+x_n^2 = r^2$, we would have

$$
\Delta u = \sum_{i=1}^n \left( v''(r) \frac{x_i^2}{r^2} + v'(r) \left( \frac{1}{r} - \frac{x_i^2}{r^3} \right) \right) = v''(r) + \frac{n-1}{r} v'(r).
$$

by letting $\Delta u = 0$, we obtain the following ODE:

$$
v''(r)+\frac{n-1}{r} v'(r) = 0.
$$

Now if $v'(r) \neq 0$, we see that

$$
 \log(v'(r)) ' = \frac{v''(r)}{v'(r)} = \frac{1-n}{r}
$$

and we integrate with respect to $r$, we have

$$
\log (v'(r)) = (1-n)\log r + C
$$

which simplifies to $v'(r) = C_0 / r^{n-1}$ for some constant $C_0$, hence the general solution $v(r)$ takes the form

$$
v(r) = \begin{cases} A\log r + B & n =2 \\ \frac{C}{r^{n-2}} + D & n \geq 3 \end{cases}
$$

where $A,B,C,D$ are all constants. This motivates the fundamental solution to Laplace's equation:

**Definition**
The function defined by

$$
\Phi(x) = \begin{cases} -\frac{1}{2\pi} \log |x| & n=2 \\ \frac{1}{n(n-2)\alpha(n)} \cdot \frac{1}{|x|^{n-2}} & n\geq 3 \end{cases}

$$
is the fundamental solution to Laplace's equation $\Delta u = 0$ for all $x \in \mathbb{R}^n / \{ 0 \}$ where $\alpha(n)$ denotes the volume of the unit ball in $\mathbb{R}^n$.


Laplace's equation is a special class of Poisson's equations, we define Poisson's equation as

**Definition**
For a given $f: \mathbb{R}^n \to \mathbb{R}$, and the unknown $u(x_1,\cdots,x_n) : U \subset \mathbb{R}^n \to \mathbb{R}$, the Poisson's equation takes the form

$$
-\Delta u = f.
$$


By construction, we know $\Phi(x)$ is harmonic since it solves $\Delta u = 0$. We shift the origin to a new point $y$, and under invariant we still have $\Delta u = 0$ and now $\Phi(x-y)$ is harmonic in $x$. Consider a given function $f: \mathbb{R}^n \to \mathbb{R}$ and that $\Phi(x-y) f(y)$ is also harmonic when $x\neq y$, by taking all possible $y$, it suggests the following convolution integral:

$$
u(x) = \int_{\mathbb{R}^n} \Phi(x-y) f(y) dy.
$$

We may want to compute $\Delta u$ in this case but we see that it is hard to deal with at when $x=y$, the next theorem will formally prove $u(x)$ is indeed the fundamental solution to the Poisson's equation:

**Theorem**
Define $\displaystyle{u(x) = \int_{\mathbb{R}^n} \Phi(x-y) f(y) dy}$ and assume that $f \in C_C^2(\mathbb{R}^n)$, then:

1. $ u \in C^2(\mathbb{R}^n)$;\\

2. $-\Delta u = f$ in $\mathbb{R}^n$.



We will prove both results separately:

For 1:

**Proof**:

Use the property of a convolution, we have
$$
u(x) = \int_{\mathbb{R}^n} \Phi(y) f(x-y) dy
$$

then denote $e_i$ as the unit vector in $i$th position of $x = (x_1,\cdots,x_n)$, and abusing the notion of interchanging limits and integrals (we actually could do that), we have

$$
\begin{align*}
\frac{\partial u}{\partial x_i}(x) = \lim_{h \to 0} \frac{u(x+he_i) - u(x)}{h} &=  \int_{\mathbb{R}^n} \Phi(y) \cdot \lim_{h \to 0}\left[ \frac{f(x+he_i - y) - f(x-y)}{h} \right] dy
&=\int_{\mathbb{R}^n} \Phi(y)\cdot \frac{\partial f}{\partial x_i}(x-y)dy.
\end{align*}
$$

Similarly one can show

$$
\frac{\partial u}{\partial x_i \partial x_j}(x) = \int_{\mathbb{R}^n} \Phi(y) \cdot \frac{\partial^2 f}{\partial x_i \partial x_j}(x-y)dy.
$$

Since $f \in C_C^2(\mathbb{R}^n)$, the second partial derivative is continuous w.r.t $x$, hence $u \in C^2(\mathbb{R}^n)$.

QED.

For 2:

**Proof**

We split the integral into two parts to avoid the blow-up of $\Phi$ near $0$, $\forall \epsilon>0$ fixed, denote $B(0,\epsilon)$ as the ball centerted at $0$ with radius $\epsilon$, write

$$
u(x) = \int_{B(0,\epsilon)} \Phi(y) f(x-y) dy + \int_{\mathbb{R}^n / B(0,\epsilon)} \Phi(y) f(x-y) dy
$$

hence

$$
\Delta u(x) = \int_{B(0,\epsilon)} \Phi(y) \Delta_x f(x-y) dy + \int_{\mathbb{R}^n/B(0,\epsilon)} \Phi(y) \Delta_xf(x-y) dy.
$$

Denote the first term as $I_{\epsilon}$, second term as $J_{\epsilon}$. Our first goal is to bound $I_{\epsilon}$, proceed as follows:

When $n=2$, we have

$$
\begin{align*}
|I_{\epsilon}| = \Bigg|-\int_{B(0,\epsilon)} \frac{1}{2\pi} \log|y| \cdot \Delta_x f(x-y) dy \Bigg|\leq C||Df||_{L^\infty(\mathbb{R}^n)} \cdot \Bigg|\int_{B(0,\epsilon)} \log|y|dy\Bigg|
\end{align*}
$$

for some constant $C$, and we further have

$$
\int_{B(0,\epsilon)} \log |y| dy = \int_0^\epsilon \int_0^{2\pi} \log|r| rd\theta dr = \epsilon^2\log |\epsilon|
$$

so we have $|I_\epsilon| < C\epsilon^2 |\log \epsilon|$ for some constant $C$. When $n\geq3$, similarly we can show that $|I_{\epsilon}| < C\epsilon$, hence the term $I_{\epsilon}$ is bounded in terms of arbitrary $\epsilon$. Now for $J_\epsilon$, first note that $\Delta_x f(x-y) = \Delta_yf(x-y)$, we have

$$
J_\epsilon = \int_{\mathbb{R}^n/B(0,\epsilon)} \Phi(y) \Delta_y f(x-y)dy.
$$

To compute this integral, we need some technical lemmas:

**Lemma**
(Gauss-Green Theorem)
Let $u(x_1,\cdots,x_n) \in C^1(\overline{U})$, let $\nu = (\nu_1,\cdots,\nu_n)$ be the outward pointing unit normal vector field of $U$ defined on $\partial U$ then

$$
\int_U u_{x_i} dx = \int_{\partial U} u \nu_i dS.
$$


We can use this lemma to further derive an integration by parts formula:

**Lemma**
(Integration by Parts)
Let $u,v \in C^1(\overline{U})$, then

$$
\int_U u_{x_i} v dx = -\int_U u v_{x_i} dx + \int_{\partial U} uv \nu^i d S.
$$



Then we may rewrite $J_\epsilon$ as

$$
J_{\epsilon} = -\int_{\mathbb{R}^n / B(0,\epsilon)} D\Phi(y) \cdot D_y f(x-y) dy + \int_{\partial B(0,\epsilon)} \Phi(y) \nu Df(x-y) dS(y)
$$

where $\nu$ is the inward pointing unit normal vector field. We now denote the first term by $K_\epsilon$ and the second term by $L_\epsilon$, then using the same technique as we did for $I_\epsilon$, we can check that

$$
|L_\epsilon| \leq C||D f||_{L^\infty(\mathbb{R}^n)} \int_{\partial B(0,\epsilon)} |\Phi(y)| dS(y) \leq \begin{cases} C\epsilon|\log \epsilon| & n=2 \\ C\epsilon & n\geq 3 \end{cases}
$$

hence $L_{\epsilon}$ is also bounded in terms of $\epsilon$. We again perform integration by parts in $K_{\epsilon}$, and we have

$$
\begin{align*}
K_\epsilon &= \int_{\mathbb{R}^n/B(0,\epsilon)} \Delta \Phi(y) f(x-y)dy - \int_{\partial B(0,\epsilon)} \nu D\Phi(y) f(x-y) dS(y)\\
&=-\int_{\partial B(0,\epsilon)} \nu D\Phi(y) f(x-y)dS(y).
\end{align*}
$$

Since $D\Phi(y) = \frac{-1}{n\alpha(n)} \frac{y}{|y|^n}$ when $y\neq 0$ and $\nu = -y/|y| = -y/\epsilon$ on $\partial B(0,\epsilon)$, so we will have

$$
\nu D\Phi(y) = \frac{1}{n\alpha(n)\epsilon^{n-1}}
$$

also $n\alpha(n)\epsilon^{n-1}$ is the surface area of the ball $\partial B(0,\epsilon)$, so

$$
K_{\epsilon} = -\frac{1}{n\alpha(n)\epsilon^{n-1}} \int_{\partial B(0,\epsilon)} f(x-y) dS(y) = -⨍_{\partial B(0,\epsilon)} f(y) dS(y) \to -f(x)
$$

as $\epsilon \to 0$. Since we have shown that $I_\epsilon, L_\epsilon$ are all bounded by terms of $\epsilon$ so by setting $\epsilon \to 0$ they will vanish as well. Hence we have

$$
-\Delta u(x) = f(x).
$$

QED.


## Properties of Harmonic Functions

### Mean Value Property

For a harmonic function $u$, its value $u(x)$ is equal to the average $u$ over both the boundary $\partial B(x,r)$ and the ball $B(x,r)$ as long as $B(x,r) \in U$.


**Theorem**
Let $U \in \mathbb{R}^n$ open, if $u(x_1,\cdots,x_n) \in C^2(U)$ is harmonic then for each ball $B(x,r) \in U$, 

$$
u(x) = ⨍_{\partial B(x,r)} u(y) dS(y) = ⨍_{B(x,r)} u(y)dy
$$

where

$$
⨍_{\partial B(x,r)} u(y) dS(y) = \frac{1}{n\alpha(n) r^{n-1}} \int_{\partial B(x,r)} u(y) dS(y),
$$

$$
⨍_{B(x,r)} u(y) dy = \frac{1}{\alpha(n) r^n} \int_{B(x,r)}u(y) dy
$$

$\alpha(n)$ is the volume of the unit ball in $\mathbb{R}^n$ and $n\alpha(n)$ is the surface area of the unit ball in $\mathbb{R}^n$.


**Proof**
Let $u(x_1,\cdots,x_n) \in C^2(U)$ be harmonic, and define

$$
\phi(r) = \begin{cases} \displaystyle{⨍_{\partial B(x,r)} u(y) dS(y)} & r>0 \\\\u(x) & r = 0\end{cases}.
$$

If $u$ is a smooth function (we later will show all harmonic functions are smooth), then $\lim_{r \to 0} \phi(r) = u(x)$ and hence $\phi$ is continuous. Note that by change of variables, we have

$$
\phi(r) = ⨍_{\partial B(0,1)} u(x+rz)dS(z)
$$

and we take the derivative of $\phi(r)$:

$$
\begin{align*}
\phi'(r) &= ⨍_{\partial B(0,1)} \nabla u(x+rz) \cdot zdS(z)\\
&=⨍_{\partial B(x,r)} \nabla u(y) \cdot \frac{y-x}{r} dS(y)\\
&= ⨍_{\partial B(x,r)} \frac{\partial u}{\partial \nu}(y) dS(y)\\
&=\frac{1}{n\alpha(n)r^{n-1}} \int_{\partial B(x,r)} \frac{\partial u}{\partial \nu}(y)dS(y)\\
&= \frac{1}{n\alpha(n)r^{n-1}} \int_{B(x,r)} \nabla (\nabla u) dy\\
&= \frac{1}{n\alpha(n) r^{n-1}} \int_{B(x,r)} \Delta u(y) dy \equiv 0.
\end{align*}
$$

which means $\phi$ is a constant function, and hence we have 

$$
u(x) = ⨍_{\partial B(x,r)} u(y)dS(y).
$$

Furthermore we have

$$
\begin{align*}
\int_{B(x,r)} u(y) dy &= \int_0^r\left( \int_{\partial B(x,s)} u dS \right)ds\\
&=u(x) \int_0^r n\alpha(n) s^{n-1} ds\\
&=\alpha(n) r^n u(x).
\end{align*}
$$

QED.

Another result is the converse to mean-value property:

**Theorem**
If $u \in C^2(U)$ satisfies

$$
u(x) = ⨍_{\partial B(x,r)} u dS
$$

for each ball $B(x,r) \in U$, then $u$ is harmonic.

**Proof**
Suppose $\Delta u \neq 0$, then $\exists B(x,r) \in U$ such that $\Delta u > 0$ say, but then

$$
\phi'(r) = \frac{1}{n\alpha(n)r^{n-1}} \int_{\partial B(x,r)}\Delta u dS = \frac{r}{n}⨍_{B(x,r)} \Delta u(y) dy >0
$$
which contradicts the fact that $\phi$ is a constant function.

QED.


### Maximum Principle

A nice property of harmonic functions is that if $u$ is harmonic on a bounded domain $\Omega$, then $u$ attains its maximum value on the boundary of $\Omega$.

**Theorem**
(Strong Maximum Principle) Suppose $u \in C^2(U) \cap C(\overline{U})$ is harmonic within $U$, then

1. $\max_{\overline{U}} u = \max_{\partial U} u$;\\

2. Furthermore, if $U$ is connected and there exists a point $x_0 \in U$ such that $u(x_0) = \max_{\overline{U}} u$, then $u$ is constant within $U$.


**Proof**
We will prove the second statement since the first followed from the second. Suppose $\exists x_0 \in U$ such that $u(x_0) = \max_{\bar{U}} u(x) \equiv M$. Then $\forall r \in (0,\text{dist}(x_0,\partial U))$, the mean-value property states that

$$
M = u(x_0) = ⨍_{B(x_0,r)} u(y) dy
$$

by taking the ''average'' around the maximum $x_0$, we would except

$$
⨍_{B(x_0,r)} u(y) dy \leq M
$$

and such will hold only if $u \equiv M$ within $B(x_0,r)$, and $u(y) = M$.

QED.

An important application of maximum principle is establishing the uniqueness of solutions to certain boundary value problems for Poisson's equation.

**Theorem**
Let $g \in C(\partial U), f\in C(U)$, then there exists at most one solution $u \in C^2(U) \cap C(\bar{U})$ of the boundary value problem

$$
\begin{cases} -\Delta u = f & \text{ in $U$} \\ u =g & \text{ on $\partial U$} \end{cases}
$$


**Proof**
Assume $u_1, u_2$ both solves the boundary value problem, then let $w = u_1 - u_2$, then we have
$$
\begin{cases} -\Delta w = 0 &\text{ in $U$} \\ w = 0 &\text{ in $\partial U$} \end{cases}
$$

then by maximum principle, $\max_{\partial U} w = \max_{\partial \bar{U}} w = 0$, i.e $u_1=u_2$.

QED.


### Smoothness

A nice thing about harmonic functions is that they are smooth!

**Theorem**
If $u \in C(U)$ satisfies the mean-value property for each ball $B(x,r) \in U$, then $u \in C^\infty(U)$.



The proof of this theorem requires some knowledge on mollifiers, so before the proof we shall spend some time on mollifiers.

**Definition**
Define a smooth function $\eta \in C^\infty(\mathbb{R}^n)$ by

$$
\eta(x) = \begin{cases} C\exp\Big( \frac{1}{|x|^2-1} \Big) & |x|<1 \\ 0 & |x| \geq 1 \end{cases}
$$

for some constant $C>0$ so that $\int_{\mathbb{R}^n} \eta dx=1$. Then for each $\epsilon>0$, set

$$
\eta_\epsilon(x) = \frac{1}{\epsilon^n} \eta\Big( \frac{x}{\epsilon} \Big).
$$

We call $\eta$ the standard mollifier, the functions $\eta_\epsilon$ are $C^\infty$ as well.


**Definition**
Denote $U_\epsilon = \{ x \in U | \text{ dist}(x,\partial U) > \epsilon \}$, if a function $f: U \to \mathbb{R}$ is locally integrable, its mollification is defined by

$$
f^\epsilon = \int_U \eta_\epsilon(x-y) f(y) dy
$$

for $x\in U_\epsilon$.


Now we prove the theorem:

**Proof**
Let $\eta$ be the standard mollifier, set $u^\epsilon = \eta_\epsilon * u $ in $U_\epsilon$, we first show $u^\epsilon \in C^\infty$, which is left as an exercise to the reader. Then to show $u$ is smooth, we will show in fact $u \equiv u^\epsilon$ on $U_\epsilon$ for each $\epsilon>0$. Let $x \in U_\epsilon$, then we know the support of $\eta_\epsilon(x-y)$ as a function of $y$ is given by $\{ y: |x-y| < \epsilon \}$, and trhus we have

$$
\begin{align*}
u^\epsilon(x) 
&= \frac{1}{\epsilon^n} \int_{B(x,\epsilon)} \eta\left( \frac{|x-y|}{\epsilon} \right) u(y)dy\\
&=\frac{1}{\epsilon^n} \int_0^\epsilon \eta\left( \frac{r}{\epsilon} \right) \left( \int_{\partial B(x,r)} u dS \right) dr\\
&=\frac{1}{\epsilon^n} u(x) \int_0^\epsilon \eta\left( \frac{r}{\epsilon} \right) n\alpha(n) r^{n-1} dr\\
&= u(x) \int_{B(0,\epsilon)} \eta_\epsilon dy\\
&= u(x).
\end{align*}
$$
so $u \in C^\infty(U_\epsilon)$ for all $\epsilon>0$.

QED.

### Liouville's Theorem

**Theorem**
If $u : \mathbb{R}^n \to \mathbb{R}$ is harmonic and bounded (either from above or below), then $u$ is constant.


To prove Liouville's theorem, we first introduce a technical lemma for estimating the derivatives of harmonic functions:

**Lemma**
Assume $u$ is harmonic in $U$, then for multi-index $\alpha = 1$,

$$
| D^\alpha u(x_0) | \leq \frac{n}{\alpha(n)} \cdot\left( \frac{2}{r} \right)^{n+1} \cdot||u||_{L^1(B(x_0,r))}.
$$
for each ball $B(x_0,r) \in U$.


**Proof**
Let $x_0 \in U$ and $B(x,r) \subset U$. Since $u_{x_i}$ is also harmonic, then use mean-value property we have

$$
\begin{align*}
|u_{x_i}(x_0) | &= \Bigg| \frac{2^n}{\alpha(n) r^n}\int_{B(x_0,\frac{r}{2})} u_{x_i}(y) dy \Bigg|\\
&= \Bigg| \frac{2^n}{\alpha(n)r^n} \int_{\partial B(x_0,\frac{r}{2})} u(y) \nu^i dS(y) \Bigg|\\
&= \Bigg|\frac{2n}{r} ⨍_{\partial B(x_0,\frac{r}{2})} u(y) \nu^i dS(y) \Bigg|\\
&\leq \frac{2n}{r} ||u||_{L^\infty(\partial B(x_0,r/2))}.
\end{align*}
$$

Now for $u(x_0)$, note that

$$
|u(x_0)| = \Bigg|\frac{2^n}{\alpha(n) r^n} \int_{B(x_0,\frac{r}{2})} u(y) dy \Bigg|\leq \frac{2^n}{\alpha(n) r^n} ||u||_{L^1(B(x_0,r))}.
$$

Hence we have

$$
|D^\alpha u(x_0)| \leq \frac{2n}{r} ||u||_{{L^\infty(\partial B(x_0,r/2))}} \leq \left( \frac{2}{r} \right)^{n+1} \cdot\frac{n}{\alpha(n)} ||u||_{L^1(B(x_0,r))}.
$$

QED.

We now prove Liouville's theorem:

**Proof**
Fix $x_0 \in \mathbb{R}^n$ and $r>0$, we have
$$
|Du(x_0)| \leq \frac{n}{\alpha(n)} \left( \frac{2}{r} \right)^{n+1} \cdot || u || \leq \frac{n}{\alpha(n)} \left( \frac{2}{r} \right)^{n+1} \cdot ||u||_{L^\infty(\mathbb{R}^n)} \overset{r \to \infty}{\to} 0.
$$
which means $u$ is a constant.

QED.

**Theorem**
Let $f \in C_C^2(\mathbb{R}^n)$ and $n \geq 3$, then any bounded solution of $-\Delta u  =f$ in $\mathbb{R}^n$ has the form
$$
u(x) = \int_{\mathbb{R}^n} \Phi(x-y) f(y) dy + C
$$
for some constant $C$.


**Proof**
If $u'$ is another solution, then $u - u'$ is a constant by Liouville's theorem.

QED.


### Harnack's Inequality

We write $V\subset\subset U$ to denote $V \subset \bar{V} \subset U$ and $\bar{V}$ is compact, we say $V$ is compactly contained in $U$.

**Theorem**
For each connected open set $V \subset\subset U$, there exists a positive constant $C$ depending only on $V$ such that

$$
\sup_V u \leq C \inf_V u
$$

for all non-negative harmonic functions $u$ in $U$. In particular

$$
\frac{1}{C} u(y) \leq u(x) \leq Cu(y)
$$

for all $x,y \in V$.


**Proof**
Consider a ball $B(a,r) \subset U$, and let $x,y \in B(a,\frac{1}{4}r)$, we first claim that $B(x,\frac{1}{4}r) \subset B(y,\frac{3}{4}r) \subset B(a,r)$. Then we use mean value property and we have

$$
u(x) = ⨍_{B(x,\frac{1}{4}r)} u(z) dz \leq ⨍_{B(\frac{3}{4}r,y)} u(z)dz = 3^n u(y).
$$

Now since $V$ is compact so there exists a finite cover of balls $\{ B_i \}, i = 1,\cdots, M$ where $B_i \equiv B(a_i,r_i) \subset U$. Then for any $x,y \in V$, we may find an ordered subcover $B_{i1},\cdots B_{i\ell}$ such that $x \in B_{i1}$, $y \in B_{i\ell}$ and $B_{ij} \cap B_{ij+1} \neq \varnothing$, and the previous conclusion holds. Then we have a chain of inequalities:

$$
u(x) \leq 3^n u(x_1) \leq \cdots \leq 3^{n\ell} u(y) \leq 3^{nM} u(y)
$$
for all $x,y \in V$, and hence we have
$$
\sup_V u \leq C \inf_V u
$$
where $C$ is a constant only depend on $V$.

QED.

### Convergence Theorems

In this section we shall discuss some convergence theorems for harmonic functions:

**Theorem**
(Weierstrass Convergence Theorem) If a sequence of harmonic functions $\{ h_n \}$ converges locally uniformly on $U$, then the limit $h = \lim_{n\to\infty} h_n$ is also harmonic on $U$, furthermore the derivatives converge locally uniformly as well, i.e $\lim_{n\to\infty} D_{x_i} h_n = D_{x_i} h$.


**Proof**
Let $K \subset U$ be compact, we choose a larger compact set $\tilde{K}$ and $r:= \text{dist}(K,\mathbb{R}^n/\tilde{K}) >0$, we use the derivative estimate to get

$$
| D^\alpha h_{l}(a) - D^\alpha h_k(a) | \leq \frac{C}{r^{|\alpha|}} \sup_{\tilde{K}} |h_l - h_k |
$$

and from the uniform convergence of $\{ h_n \}$ on $\tilde{K}$, and we see that $ \{D^\alpha h_n \}$ is a Cauchy sequence on $K$, thus uniformly convergent on $K$, and locally uniformly convergent on $U$. We can also show that $\lim_{n\to\infty} D^\alpha h_n = D^\alpha h$ locally uniformly on $U$ for all index $\alpha$. In particular we have $\Delta h = \lim_{n \to \infty} \Delta h_n$ and hence $h$ is harmonic.

QED.


**Theorem**
(Harnack Convergence Theorem) Consider an increasing sequence of harmonic functions $\{ h_n \}$ on $U \subset \mathbb{R}^n$, then either $\lim_{n\to\infty} h_n = \infty$ or it converge locally uniformaly to a harmonic function. In particular, if $\exists x_0 \in U$ such that $\lim_{n\to\infty} h_n(x_0) \neq \infty$, then we may conclude locally uniform convergence.



**Proof**
Assume $x_0 \in U$ such that $\lim_{n\to\infty} h(x_0) \neq \infty$. For all $k \leq l$, $K$ compact, and $x_0 \in K \in U$, we have $h_l - h_k$ as a non-negative harmonic function, and hence by Harnack's inequality,
$$
\max_K (h_l - h_k) \leq C \min_{K} (h_l - h_k) \leq C(h_l(x_0) - h_k(x_0))
$$
which implies the uniform Cauchy property of $\{ h_n \}$ on $K$, and hence locally uniform convergence is achieved. We now let $\lim_{n \to \infty} h_n = h$ and it remains to show $h$ is harmonic, which follows from Weierstrass convergence theorem.


QED.


