---
title: "Theory of Sufficiency"
collection: publications
category: statistics
permalink: /publication/sufficiency
order: 4
excerpt: 'We will investigate some basic theories of sufficiency'
date: 2025-01-20
venue: 'Winter'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Sufficiency'
---

Often times, our raw data can be very large and long, and it would be inefficient to work with them directly. We may think of some kind of data reduction to compress our large data into a short and manageable way without losing any information. A statistic $T(\vec X)$ is a form of data reduction or summary, thus we are interested in those statistics that do not discard important information about an unknown parameter $\theta$. That's why we introduced the sufficiency principle.

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Suppose the random sample $X_1,\cdots,X_n$ has a joint pdf (pmf) $p_\theta(\vec x)$, $\theta \in \Theta$, a statistic $T(\vec X)$ is sufficient of $\theta$, if the conditional distribution of $X_1,\cdots,X_n$ given $T(\vec X) = t$ for any $\theta \in \Theta$, $t \in S_T$ such that $f_{\vec X| T(\vec X) = t} (x_1,\cdots,x_n)$ does not depend on $\theta$.
</div>


In general, the distribution $p_\theta(\vec x \in \mathcal{X} \vert T(\vec X) = t)$ does not depend on $\theta$.

**Example:** Let $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(\theta)$, we claim that $T(\vec X) = \displaystyle{\sum_{i=1}^n X_i}$ is a sufficient statistic of $\theta$, this is because

$$
\begin{align*}
f_\theta(x_1,\cdots,x_n | T(\vec X) = t) &= \frac{p_\theta(X_1=x_1,\cdots,X_n = x_n , \sum X_i = t)}{p_\theta (\sum X_i = t)}\\
&= \frac{\prod_{i=1}^n \theta^{x_i} (1-\theta)^{n-x_i}}{\binom{n}{t} \theta^t (1-\theta)^{n-t}}\\
&=\begin{cases} \frac{1}{\binom{n}{t}} & \sum_{i=1}^n X_i = t \\ 0 & \text{elsewhere} \end{cases}
\end{align*}
$$

we see that the conditional distribution does not depend on $\theta$.

Note that a sufficient statistic can also be a vector. For example, later we will see if $X_1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu,\sigma^2)$, a sufficient statistic of $(\mu,\sigma^2)$ is

$$
\left( \sum_{i=1}^n X_i , \sum_{i=1}^n (X_i - \bar{X}_n)^2 \right).
$$


<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Let $T(\vec X)$ be a sufficient statistic of $\theta$, $g$ be a one-to-one transformation, then $g(T(\vec X))$ is a sufficient statistic of $\theta$.
</div>



So in the previous Bernoulli example, $T(\vec X) =  \displaystyle{\frac{1}{n}\sum_{i=1}^n X_i}$ is also a sufficient statistic of $\theta$.


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Neyman-Fisher Factorization Theorem) Let a random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} f$ with a joint pdf (pmf) $p_\theta(\vec x) = p_\theta(x_1,\cdots,x_n)$, a statistic $T(\vec X)$ is sufficient of $\theta$ if and only if
$$
p_\theta(x_1,\cdots,x_n) = g( T(\vec x), \theta) \cdot h(x_1,\cdots,x_n)
$$

for all $\theta \in \Theta$, and function $g$ depends on $T(\vec x), \theta$ while $h(\vec x)$ does not depend on $\theta$.
</div>



The proof of this theorem is omitted.

**Example:** Find a sufficient statistic of the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(\theta)$.

**Solution:** We derive

$$
\begin{align*}
p_\theta(x_1,\cdots,x_n) &= \prod_{i=1}^n \theta^{x_i} (1-\theta)^{1-x_i}, x_i \in \{0,1\}\\
&= \theta^{\sum X_i} \cdot (1-\theta)^{n - \sum x_i} \cdot \prod_{i=1}^n \mathbf{1}\{ X_i\}
\end{align*}
$$

we let the first term to be $g(T(\vec x),\theta)$ and the second term to be $h(\vec x)$, and we apply Neyman-Fisher theorem, $\displaystyle{T(\vec X) = \sum_{i=1}^n X_i}$ is a sufficient statistic of $\theta$.

*Note: A sufficient statistic doesn't mean a good (unbiased) estimator!*

**Example:** Find a sufficient statistic of the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Uniform(0,\theta)$, $\theta>0$.

**Solution:** The pdf of a uniform distribution is given by

$$
f(x) = \begin{cases} \frac{1}{\theta} & x \in (0,\theta) \\ 0 & \text{otherwise} \end{cases}
$$


then we derive

$$
\begin{align*}
p_\theta(\vec x) &= \prod_{i=1}^n \frac{1}{\theta} \cdot \chi\{ 0 < x_i < \theta\}\\
&=\left( \frac{1}{\theta} \right)^n \cdot \mathbf{1}\{ 0 < X_{(n)} < \theta \} \cdot \mathbf{1}\{ 0 < X_{(1)}\}
\end{align*}
$$

where $X_{(n)} = \max\{ X_1,\cdots,X_n\}, X_{(1)} = \min\{ X_1,\cdots,X_n\}$, and let the first two terms to be $g(T(\vec X),\theta)$ and the last term to be $h(\vec x)$, then by Neyman-Fisher theorem, $T(\vec X) = X_{(n)}$ is a sufficient statistic of $\theta$.


<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> If $X_1,\cdots,X_n \overset{i.i.d}{\sim} f(\theta,x)$ where $f$ belongs to exponential family, then a sufficient statistic of $\theta$ is $T(\vec X) = \displaystyle{\sum_{i=1}^n X_i}$.
</div>

Verify it yourself.


**Example:** Find a sufficient statistic of the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu,\sigma^2)$.

**Solution:** Note that the joint pdf can be derived as

$$
\begin{align*}
p_\theta(\vec x) &= \prod_{i=1}^n \frac{1}{\sqrt{2\pi} \sigma} \exp \left( -\frac{(x_i - \mu)^2}{2\sigma^2} \right)\\
&= \left( \frac{1}{\sqrt{2\pi} \sigma} \right)^n \cdot \exp \left( -\frac{1}{2\sigma^2} \sum_{i=1}^n\left[ x_i^2 - 2x_i \mu + \mu^2 \right] \right)\\
&= \left( \frac{1}{\sqrt{2\pi} \sigma} \right)^n \cdot \exp \left( -\frac{1}{2\sigma^2} \left[ \sum_{i=1}^n x_i^2 - 2\mu \sum_{i=1}^n x_i + n\mu^2 \right] \right)
\end{align*}
$$

here, the sufficient statistic takes a vector form, since we have 2 parameters so it makes sense that we have two terms in our sufficient statistic. We let 

$$
T(\vec X) = \left( \sum_{I=1}^n X_i , \sum_{i=1}^n X_i^2 \right)
$$

to be the sufficient statistic of $\vec\theta = (\mu,\sigma^2)$.

*Note that we cannot separate them, we can't say $\sum X_i$ is a sufficient statistic of $\mu$ because in this case Neyman-Fisher won't work.*

In fact there are many ways to describe a sufficient statistic, for example recall the Bernoulli example, we can make

$$
T(\vec X) = \left( \sum_{i=1}^m X_i , \sum_{j=m+1}^n X_i \right), 1 \leq m \leq n-1
$$

as our sufficient statistic. So although sufficient statistic is a form of data reduction, but it matters how far we can make our reduction. We would want to make as much reductions as possible, and hence we shall introduce minimum sufficient statistic.


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> A statistic $T(\vec X)$ is a minimal sufficient statistic of $\theta$ if and only if:

(1) $T(\vec X)$ is sufficient;

(2) For any other sufficient statistic $T^*(\vec X)$ of $\theta$, $T(\vec X)$ is a function of $T^*(\vec X)$, i.e. $T(\vec X) = \varphi(T^*(\vec X))$ where $\varphi$ is some measurable function.
</div>




The following theorem can verify minimal sufficient statistic easily:


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Lehmann-Scheffe) For a random sample $X_1,\cdots,X_n$ with joint density $p_\theta(\vec x)$, suppose a statistic $T(\vec X)$ is such that $\forall \vec x, \vec y \in \mathcal{X} \subset \mathbb{R}^n$, $T(\vec x) = T(\vec y) $ if and only if $\displaystyle{\frac{p_\theta(\vec x)}{p_\theta(\vec y)}}$ does not depend on $\theta$, then $T(\vec X)$ is a minimum sufficient statistic of $\theta$.
</div>




The proof of this theorem is omitted.

**Example:** Find a minimal sufficient statistic of the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Uniform(0,\theta)$.

**Solution:** Previously, we had shown that a sufficient statistic is given by $T(\vec X) = X_{(n)}$, and the joint distribution is given by

$$
p_\theta(\vec x) = \left( \frac{1}{\theta} \right)^n \cdot \mathbf{1}\{ X_{(n)} < \theta\}\cdot \mathbf{1}\{ X_{(1)} > 0\}.
$$

Now $\forall \vec x, \vec y$ in our sample space, we compute the ratio

$$
\frac{p_\theta(\vec x)}{p_\theta(\vec y)} = \frac{\mathbf{1}\{ X_{(n)} < \theta\}\cdot \mathbf{1}\{ X_{(1)} > 0\}}{\mathbf{1}\{ Y_{(n)} < \theta\}\cdot \mathbf{1}\{ Y_{(1)} > 0\}}
$$

which we see will not depend on $\theta$ if and only if $X_{(n)} = Y_{(n)}$, which means $T(\vec X) = T(\vec Y)$ and $T(\vec X)$ is the sufficient statistic, hence $T(\vec X) = X_{(n)}$ is a minimal sufficient statistic.


**Exercise:** Try to use similar method to verify that

$$
T(\vec X) = \left( \sum_{i=1}^n X_i , \sum_{i=1}^n X_i^2\right)
$$

is a minimal sufficient statistic of the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu,\sigma^2)$.



<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> If $T(\vec X)$ is a minimal sufficient statistic of $\theta$, then for any one-to-one function $g$, $g(T(\vec X))$ is also a minimal sufficient statistic of $\theta$.
</div>


This proof is trivial.


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $X$ be a random variable with pdf (pmf) belonging to a parametric family $\mathcal{F}:= \{ f_\theta : \theta \in \Theta\}$, this family is said to be complete, if for any measurable function $g$ with $\mathbb{E} [g(\vec X)]$ exists, we have $\mathbb{E}[g(\vec X)] = 0 \implies \mathbb{P}\{ g(X) = 0\} = 1$ almost surely. A statistic $T(\vec X)$ is complete, if the family of its distributions is complete.
</div>



**Example:** Show that the statistic $T(\vec X) = \displaystyle{\sum_{i=1}^n X_i}$ in a Bernoulli random sample is complete.

**Solution:** Set $\mathbb{E}[g(T(\vec X))] = 0$, by definition we have

$$
\begin{align*}
&\sum_{t=0}^n g(t) \binom{n}{t} \theta^t (1-\theta)^{n-t} = 0, \forall \theta \in (0,1)\\
&\implies \sum_{t=0}^n g(t) \binom{n}{t} \left( \frac{\theta}{1-\theta} \right)^t = 0, \forall \theta \in (0,1)\\
&\implies g(t) \binom{n}{t} = 0\\
&\implies g(t) = 0, \text{ almost surely}.
\end{align*}
$$

and hence $T(\vec X)$ is a complete statistic.

**Example:** Show that the statistic $T(\vec X) = X^2$ where $X \sim N(0,\theta)$, $\theta>0$ is complete.\\

**Solution:** We first claim that $\displaystyle{\frac{X^2}{\theta} \sim \chi_{(1)}^2}$, it can be shown using the transformation of functions of random variables introduced in \textbf{MATH 356}. Then let $\mathbb{E}[g(T(\vec X))] = 0$ where we have $g(x) = x^2$, and by definition it implies that

$$
\begin{align*}
&\int_0^\infty g(t) f_{T(\vec X)}(t,\theta)dt = 0\\
&\implies \int_0^\infty \frac{1}{\sqrt{2\pi} \theta} g(t) t^{-1/2} e^{-\frac{t}{2\theta}} dt = 0,
\end{align*}
$$

which further implies $g(t) \equiv 0$.

<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Let a random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} f(\theta,x)$ where $f$ belongs to exponential family, then $\displaystyle{T(\vec X) = \sum_{i=1}^n X_i }$ is a complete statistic of $\theta$.
</div>






















