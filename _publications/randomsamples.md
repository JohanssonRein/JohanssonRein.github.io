---
title: "Random Samples"
collection: publications
category: statistics
permalink: /publication/randomsamples
order: 1
excerpt: 'We will investigate some basic theories of random samples'
date: 2025-01-10
venue: 'Winter'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Random Samples'
---

# Random Samples

Suppose we seek information about certain characteristic of a group or a collection of elements or units, called population. Due to cost, we may not be able to study every unit of a population, and we restrict to a random sample from a population. Then the purpose of statistics is to make ``inference" or educated guess about the characteristics of interest. 

In general, there are two types of statistical inference, namely parametric inference and non-parametric inference. In a parametric inference, we assume that we already know the functional form of the distribution of the random sample $X$ up to some unknown parameter $\vec \theta$, for example we may know $X$ is normal with parameters $\vec \theta = (\mu,\sigma^2)^T$, or $X \sim Exp(\theta)$ with $\theta >0$. In this case, we would make inference about $\theta$ based on our random sample. In a non-parametric inference, we basically know nothing about the function form of the distribution.


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $X_1,X_2,\cdots,X_n$ be independent and identically distributed random variables with a common distribution $F$, written as $X_1,X_2,\cdots,X_n \overset{i.i.d}{\sim} F$. This collection $X_1,X_2,\cdots,X_n$ is called a random sample from the population of interest.
</div>



And our goal is to use $X_1,\cdots,X_n$ to make inference of $F$. Here are some examples:

**Example 1: (Parametric Inference)**

Assume we have $X \sim N(\mu,\sigma^2)$, then we would like to find $\vec \theta = \begin{pmatrix} \mu \\ \sigma^2 \end{pmatrix}$ such that it fits the sample best. We already know that

$$
F_{\vec \theta}(x) = \mathbb{P}_{\theta}(X \leq x) = \int_{-\infty}^{x} \frac{1}{\sqrt{2\pi} \sigma}\exp\left( -\frac{1}{2\sigma^2}(x-\mu)^2 \right)dx
$$

And now if we have a random sample $X_1,\cdots X_n$, by WLLN (Weak Law of Large Numbers) and CMT (Continuous Mapping Theorem), we have

$$
\hat{\mu}_n = \overline{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \overset{P}{\to} \mu,
$$

$$
\hat{\sigma}_n^2 = S_n^2 =  \frac{1}{n} \sum_{i=1}^n (X_i - \hat{\mu}_n)^2 \overset{P}{\to} \sigma^2.
$$

So our inference is successful, and the guess is

$$
\vec \theta = \begin{pmatrix} \hat{\mu}_n \\ \\\hat{\sigma}_n^2 \end{pmatrix} = \begin{pmatrix} \overline{X}_n \\ \\S_n^2 \end{pmatrix}.
$$

**Example 2: (Non-parametric Inference)**

We may not assume any parametric form for $F$, suppose all we know is $X \sim F, F(x) = \mathbb{P}(X \leq x), \forall x \in \mathbb{R}$. Now in this random sample $X_1, X_2,\cdots,X_n \overset{i.i.d}{\sim} F$, we may define our Empirical CDF (ECDF) as

$$
F_n(x) = \frac{1}{n} \sum_{i=1}^n \chi(X_i \leq x), \hspace{1cm} \chi(X_i \leq x) = \begin{cases} 1 & X_i \leq x \\ \\ 0 & \text{otherwise} \end{cases}
$$


Again, according to WLLN, we have $F_n(x) \overset{P}{\to} F(x), \forall x \in \mathbb{R}, n \to \infty$, and we actually have a stronger statement, by Glivenlco-Cantelli Theorem:

$$
\sup_{x \in \mathbb{R}} \Big\vert F_n(x) - F(x) \Big\vert \overset{a.s}{\to} 0, n \to \infty.
$$



<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $X_1,\cdots,X_n \overset{i.i.d}{\sim} F$ and let
  
$$
T: \mathbb{R}^d \times \mathbb{R}^d \times \cdots \times \mathbb{R}^d \to \mathbb{R}^k
$$

be a Borel measurable function. Then $T(X_1,X_2,\dots,X_n)$ is called a statistic provided that it does not depend on any unknown, i.e $T$ only depends on $X_1,X_2,\cdots,X_n$.
</div>





For example, if $X_1,\cdots,X_n \overset{i.i.d}{\sim} F$, then

$$
\overline{X}_n = \frac{1}{n} \sum_{i=1}^n X_i; S_n^2 = \frac{1}{n-1} \sum_{i=1}^n (X_i - \overline{X})^2; F_n(x) = \frac{1}{n} \sum_{i=1}^n \chi(X_i \leq x)
$$

are all statistics. But note that $\overline{X}_n - \mu$ is not a statistic, since it is also a function of $\mu$, but it is still a random variable. We call $T(x_1,x_2,\cdots,x_n)$ an observed value of the statistic $T(X-1,X_2,\cdots,X_n)$.

We would like to discuss some general results:

<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $X_1,X_2,\cdots,X_n \overset{i.i.d}{\sim} F$ and $g: \mathbb{R} \to \mathbb{R}$ be a Borel measurable function with $\Var(g(X_i)) < +\infty$, then
$$
\mathbb{E}\left\{ \sum_{i=1}^n g(X_i) \right\} = n \mathbb{E}(g(X_i)) \hspace{0.2cm} \text{and} \hspace{0.2cm} \Var\left\{ \sum_{i=1}^n g(X_i) \right\} = n \mathbb{E}\{ ( g(X_i) - \mathbb{E}(g(X_i)) )^2\}
$$
</div>



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $X_1,\cdots,X_n \overset{i.i.d}{\sim} F$, and $\mu = \mathbb{E} X_i, \sigma^2 = \Var(X_i) < +\infty$, then:

* $\mathbb{E}(\overline{X}_n) = \mu$;

* $\displaystyle{\Var(\overline{X}_n) = \frac{\sigma^2}{n}}$

* $\mathbb{E}(S_n^2) = \sigma^2$, here $\displaystyle{S_n^2 = \frac{1}{n-1} \sum_{i=1}^n (X_i - \overline{X})^2}$

* $\displaystyle{M_{\overline{X}_n}(t) = \left[ M_{X_i} \left( \frac{t}{n} \right) \right]^n}$
</div>



An example is that if we have $X_1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu,\sigma^2)$, then $\overline{X}_n \sim \displaystyle{N\left( \mu, \frac{\sigma^2}{n} \right)}$.


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $X_1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu,\sigma^2)$, then

* $\overline{X}_n \sim \displaystyle{N\left( \mu, \frac{\sigma^2}{n} \right)}$

* $\overline{X}_n$ and $S_n^2$ are independent

* $\displaystyle{\frac{(n-1)S_n^2}{\sigma^2} \sim \chi_{n-1}^2}$.
</div>


<div style="background-color: #fff9cc; padding: 1em; border-left: 6px solid #ffeb3b; border-radius: 8px; margin: 1em 0;">
  <strong>Proof.</strong> The first one is easy, we will prove the rest two. For the second one, note that we have

$$
\begin{align*}
S_n^2 = \frac{1}{n-1} \sum_{i=1}^n(X_i - \overline{X}_n)^2 &= \frac{1}{n-1} \left\{ \sum_{i=2}^{n} (X_i - \overline{X}_n)^2 + (X_1 -\overline{X}_n)^2 \right\}\\
&= \frac{1}{n-1} \left\{ \sum_{i=2}^n (X_i - \overline{X}_n)^2 + \left[ \sum_{i=2}^n (X_i - \overline{X}_n ) \right]^2 \right\}
\end{align*}
$$

So $S_n^2$ is a function of $(X_2 - \overline{X}_n, \cdots,X_n - \overline{X}_n)$, and hence it is equivalent to show that $\overline{X}_n$ and 
$(X_2 - \overline{X}_n, \cdots,X_n - \overline{X}_n)$ are independent. We will include a transformation technique, let

$$
\begin{cases}
Y_1 &= \overline{X}_n \\
Y_2 &= X_2 - \overline{X}_n\\
&\vdots\\
Y_n &= X_n - \overline{X}_n
\end{cases}
\implies
\begin{cases}
X_1 &= Y_1 - \sum_{i=1}^n Y_i\\
X_2 &= Y_2+Y_1\\
&\vdots\\
X_n &= Y_n+Y_1
\end{cases}
$$

The Jacobian is given by

$$
\vert J \vert=\det
\begin{pmatrix}
1 & -1 & -1 & \cdots & -1 \\
1 & 1 & 0 & \cdots & 0\\
\vdots &\ddots & \ddots & \ddots & 0\\
1 & 0 & 0 & \cdots & 1
\end{pmatrix} = n
$$

Thus we have

$$
\begin{align*}
f_{Y_1,Y_2,\cdots,Y_n}(y_1,y_2,\cdots,y_n) &= \vert J \vert \cdot f_{X_1,X_2,\cdots,X_n}(x_1(y_1,\cdots,y_n),\cdots,x_n(y_1\cdots,y_n))\\
&= n \cdot \prod_{i=1}^n \frac{1}{\sqrt{2\pi} \sigma} \exp\left\{ -\frac{1}{2\sigma^2} \left[ x_i(y_1,\cdots,y_n) - \mu \right]^2 \right\}\\
& = K\cdot \exp\left( \frac{-n(y_1-\mu)^2}{2\sigma^2} \right) \cdot \exp\left\{ -\frac{1}{2\sigma^2} \left[ \left( \sum_{i=2}^n y_i \right)^2 +\sum_{i=2}^n y_i^2 \right] \right\},
\end{align*}
$$

for some constant $K$. Since their joint pdf splits, so $\overline{X}_n$ and $S_n^2$ are independent.

For the last one, note that

$$
\begin{align*}
\sum_{i=1}^n \left( \frac{X_i - \mu}{\sigma} \right)^2 &= \frac{\sum_{i=1}^n (X_i - \overline{X}_n + \overline{X}_n - \mu )^2}{\sigma^2} \\
& = \frac{\sum_{i=1}^n (X_i - \overline{X}_n)^2 + \sum_{i=1}^n (\overline{X}_n - \mu)^2 +2\sum_{i=1}^n(X_i - \overline{X}_n)(\overline{X}_n - \mu)}{\sigma^2}\\
& = \frac{\sum_{i=1}^n(X_i - \overline{X}_n)^2}{\sigma^2} + \frac{n(\overline{X}_n - \mu)^2}{\sigma^2}.
\end{align*}
$$

Here we use the fact that if $X \sim N(0,1)$ then $X^2 \sim \chi_1^2$. So

$$
\frac{\sum_{i=1}^n (X_i -\mu)^2}{\sigma^2} \sim \chi_n^2; \frac{n(\overline{X}_n - \mu)^2}{\sigma^2}\sim \chi_1^2
$$

and thus

$$
\frac{\sum_{i=1}^n (X_i - \overline{X}_n)^2}{\sigma^2} \sim \chi_{n-1}^2 \implies \frac{(n-1)S_n^2}{\sigma^2} \sim \chi_{n-1}^2.
$$
</div>



# $t$ Distribution and $F$ distribution

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $X$ be a continuous random variable, we say $X$ forms a $t$ distribution (student distribution), denote as $X \sim t(\nu)$ where $\nu$ is a parameter, if its pdf is given by
  
$$
f_X(x) = \frac{\Gamma(\frac{\nu+1}{2})}{\Gamma(\frac{\nu}{2}) \sqrt{\pi \nu}} \left( 1+\frac{x^2}{\nu}\right)^{-\frac{\nu+1}{2}}
$$
</div>



Here are some remarks:

* If $\nu = 1$, it is called a Cauchy distribution, in this case $\mathbb{E} X$ does not exist. In general if $\nu >2$, we have $\mathbb{E} X = 0,\Var(X) = \displaystyle{\frac{\nu}{\nu-2}}$;\\

* If $Z \sim N(0,1)$, $V = \chi^2_v$ and $Z,V$ are independent, then
* 
$$
T = \frac{Z}{\displaystyle{\sqrt{\frac{V}{\nu}}}} \sim t(\nu)
$$



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $X-1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu,\sigma^2)$, then
  
$$
T = \frac{\overline{X}_n - \mu}{\sqrt{S_n^2/n}} \sim t(n-1).
$$

</div>


<div style="background-color: #fff9cc; padding: 1em; border-left: 6px solid #ffeb3b; border-radius: 8px; margin: 1em 0;">
  <strong>Proof.</strong> By
  
$$
\frac{\sqrt{n}(\overline{X}_n - \mu)}{\sigma} \sim N(0,1) \hspace{0.2cm}\text{and} \hspace{0.2cm} \frac{(n-1)S_n^2}{\sigma^2} \sim \chi_{n-1}^2
$$

it is easy to see that theorem $4$ holds.
</div>



Suppose $U \sim \chi_m^2, V = \chi_n^2$ and $U,V$ are independent, then

$$
F = \frac{\chi_m^2/m}{\chi_n^2/n} \sim F(m,n).
$$


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $X_1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu_1,\sigma_1^2)$ and $Y_1,\cdots,Y_n \overset{i.i.d}{\to} N(\mu_2,\sigma_2^2)$ be two independent random samples, then
$$
F = \frac{S_m^2/\sigma_1^2}{S_n^2/\sigma_2^2} \sim F(m-1,n-1).
$$
</div>


# Asymptotic Theories

What happens to a statistic" or its distributio when $n \to \infty$? We will first state some theorems that are useful:


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $\{X_n : n\geq 1\}$ be a sequence of random variables, and define $T(X_1,\cdots,X_n) = T_n$, we say $T_n$ convergent to $\theta$ in probability, denote as $T_n \overset{P}{\to} \theta$, if
  
$$
\forall \epsilon >0, \lim_{n \to \infty} \mathbb{P}\{ | T_n - \theta | > \epsilon\} = 0.
$$
</div>



From this definition, we may state the weak law of large numbers (WLLN):



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Weak Law of Large Numbers)\\

Let $X_1,\cdots,X_n \overset{i.i.d}{\sim} F$ with $\mathbb{E} X_i = \mu$, and $\Var(X_i) <+\infty$, then $\overline{X}_n \overset{P}{\to} \mu$ as $n \to \infty$.
</div>


<div style="background-color: #fff9cc; padding: 1em; border-left: 6px solid #ffeb3b; border-radius: 8px; margin: 1em 0;">
  <strong>Proof.</strong> We will show that $\forall \epsilon >0$, we have
  
$$
\lim_{n \to \infty} \mathbb{P}\left\{ \Bigg\vert\frac{1}{n}(X_1+\cdots+X_n) - \mu \Bigg\vert > \epsilon \right\}.
$$

Since $\mathbb{E} \overline{X}_n = \mu, \Var(\overline{X}_n) = \frac{\sigma^2}{n}$, by Chebyshev's inequality, we have

$$
\mathbb{P}\{ |\overline{X}_n - \mu| > \epsilon\} \leq \frac{\Var{\overline{X}_n}}{\epsilon^2} = \frac{\sigma^2}{\epsilon} \frac{1}{n} \to 0, \text{as $n \to \infty$}.
$$
</div>


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $\{ X_n : n\geq 1\}$ be a sequence of random variables, and $X_i$ has a distribution $F_{X_i}$. We say the sequence $\{ F_{X_i} : n\geq 1\}$ convergent to $F$ in distribution, denote by $F_{X_n} \overset{d}{\to} F$ or $X_n \overset{d}{\to} X$, if 
  
$$
\lim_{n \to \infty} F_{X_i}(x) = F(x), \forall x
$$
</div>




The most used application of convergence in distribution is central limit theorem, which states that if we have $X_1,\cdots,X_n \overset{i.i.d}{\sim} F$ and $\mu = \mathbb{E} X_i, \sigma^2 = \Var(X_i) <+ \infty$, then

$$
\frac{\sqrt{n}(\overline{X}_n - \mu)}{\sigma} \overset{d}{\to} N(0,1)
$$
as $n \to \infty$.

Then we introduce a very useful theorem:

**Slutsky's Theorem**

Assume that $X_n \overset{d}{\to} X$ and $Y_n \overset{P}{\to} a \in \mathbb{R}$ as $n \to \infty$, then we have:

* $X_n + Y_n \overset{d}{\to} X+A$;

* $X_n \cdot Y_n \overset{d}{\to} aX$;

* $\displaystyle{\frac{X_n}{Y_n} \overset{d}{\to} \frac{X_n}{a}}, a \neq 0$,

as $n \to \infty$.

**Continuous Mapping Theorem**

Suppose $X_n \overset{P}{\to} X$ and $g$ is a continuous function on the set $C$ such that $\mathbb{P}(X \in C) = 1$, then

$$
g(X_n) \overset{P}
{\to} g(X), \text{ as $n \to \infty$}.
$$




Let $X-1,\cdots,X_n \overset{i.i.d}{\to} F$, $\mu = \mathbb{E} X_i, \sigma^2 = \Var(X_i) < +\infty$, then

$$
\frac{\sqrt{n}(\overline{X}_n - \mu)}{S_n} \overset{d}{\to} N(0,1), \text{ as $n \to \infty$}.
$$



To see this, first, we have
$$
\frac{\sqrt{n}(\overline{X}_n - \mu)}{S_n} = \frac{\sqrt{n}(\overline{X}_n - \mu)/\sigma}{S_n/\sigma}
$$

where the numerator $\overset{d}{\to} N(0,1)$ by central limit theorem, and in the denominator, since $S_n^2 \overset{P}{\to} \sigma^2$, then by continuous mapping theorem $S_n \overset{P}{\to} \sigma$, so the denominator $\overset{P}{\to} \sigma$, finally using Slutsky's theorem we finished the proof.



**First Order Delta Method**

Let $\sqrt{n}(X_n - \mu) \overset{d}{\to} V$ as $n \to \infty$, and let $g$ be a real valued function such that $g'$ exists at $x = \mu$, $g'(\mu) \neq 0$, then

$$
\sqrt{n} (g(X_n) - g(\mu)) \overset{d}{\to}g'(\mu)\cdot V
$$

as $n \to \infty$.


In particular, if $V \sim N(0,\sigma^2)$, then

$$
\sqrt{n}(g(X_n) - g(\mu)) \overset{d}{\to} N(0,(g'(\mu))^2\sigma^2).
$$


**Second Order Delta Method**

Let $\sqrt{n}(X_n - \mu) \overset{d}{\to} N(0,\sigma^2)$ as $n \to \infty$, $g'(\mu) = 0$, $g''(\mu) \neq0$. Then

$$
n\{ g(x_n) - g(\mu) \} \overset{d}{\to} \frac{\sigma^2 g''(\mu)}{2}\chi_1^2
$$





