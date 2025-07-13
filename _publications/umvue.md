---
title: "Uniformly Minimum Variance Unbiased Estimator (UMVUE)"
collection: publications
category: statistics
permalink: /publication/umvue
order: 3
excerpt: 'We will investigate some basic theories of Uniformly Minimum Variance Unbiased Estimator (UMVUE)'
date: 2025-01-15
venue: 'Winter'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Uniformly Minimum Variance Unbiased Estimator (UMVUE)'
---


Now we would like to focus on the class of unbiased estimators of a real valued parameter $\tau(\theta)$, $\tau : \Theta \to \mathbb{R}$. We would like to introduce the method of Uniformly Minimum Variance Unbiased Estimator (UMVUE):

Let $\vec X = \begin{pmatrix} X_1 \\ X_2 \\ \vdots \\ X_n \end{pmatrix}$ be a random vector with a joint pdf (pmf) given by $p_{\theta}(x_1,\cdots,x_n) = p_{\theta}(\vec x)$, and the vectoer $\vec x$ given by $\vec x = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix}$.

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> An estimator $T(\vec X)$ of a real valued parameter $\theta \in \Theta \subset \mathbb{R}^d$ where $\tau(\theta) : \Theta \to \mathbb{R}$ is said to be a UMVUE of $\tau(\theta)$ if:

(1) $\mathbb{E}_{\theta}\{ T(\vec X)\} = \tau(\theta), \forall \theta \in \Theta$;

(2) For any other unbiased estimator of $\tau(\theta)$, call it $T^*(\vec X)$, where $\mathbb{E}_{\theta}\{ T^*(\vec X)\} = \tau(\theta),\forall \theta \in \Theta$, and

$$
\mathbf{Var}_{\theta}\{T(\vec X)\} \leq \mathbf{Var}_{\theta}\{ T^*(\vec X)\}, \forall \theta \in \Theta.
$$
</div>



How do we actually find a UMVUE? There are two ways, one is by Cramér-Rao Lower Bound, one is by Rao-Blackwell \& Lehmann-Scheffé theorem. We first introduce the Cramér-Rao Lower Bound (CRLB). Assume $d=1$, $\Theta \subset \mathbb{R}$, $\vec X \sim p_{\theta}$ (joint pdf / pmf).

* Assume that the family $\{ p_{\theta} : \theta \in \Theta \subset \mathbb{R} \}$ has a common support, i.e
* 
$$
\mathcal{S} := \left\{ \vec x = \begin{pmatrix} x_1 \\ \vdots \\ x_n \end{pmatrix} : p_{\theta}(\vec x) > 0 \right\}

$$
and does not depend on $\theta$. (In this case $Uniform(0,\theta)$ is excluded);

* Furthermore, assume for $\vec x \in \mathcal{S}$, $\theta \in \Theta \subset \mathbb{R}$, $\displaystyle{\frac{d}{d\theta}\log p_{\theta}(\vec x)}$ exists;

* Also, assume for any statistics $h(\vec X)$ with $\mathbb{E}\{ | h(\vec X) | \} < +\infty, \forall \theta \in \Theta$ we have
* 
$$
\frac{d}{d\theta} \int_{\mathcal{S}} h(\vec x) p_{\theta}(\vec x) d\vec x = \int_{\mathcal{S}} h(\vec x) \frac{d}{d\theta} p_{\theta}(\vec x)d\vec x

$$
whenever the $R.H.S$ is finite.


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Cramér-Rao Lower Bound)

Assume the above conditions hold, let $T(\vec X)$ be such that 

$$
\mathbf{Var}_{\theta}(T(\vec X))<+\infty, \mathbb{E}_{\theta}\{ T(\vec X)\} = \tau(\theta),\forall \theta \in \Theta,
$$

then if $\displaystyle{0<\mathbb{E}_{\theta}\left\{ \left[ \frac{d}{d\theta} \log p_{\theta}(\vec x) \right]^2 \right\}<+\infty,\forall \theta \in \Theta}$, then

$$
\mathbf{Var}_{\theta}(T(\vec X)) \geq \frac{[\tau'(\theta)]^2}{\displaystyle{\mathbb{E}_{\theta}\left\{ \left[ \frac{d}{d\theta} \log p_{\theta}(\vec x) \right]^2 \right\}}}.
$$
</div>



Here, we denote $I(\theta) = \displaystyle{\mathbb{E}_{\theta}\left\{ \left[ \frac{d}{d\theta} \log p_{\theta}(\vec x) \right]^2 \right\}}$, it is called the Fisher Information.



<div style="background-color: #fff9cc; padding: 1em; border-left: 6px solid #ffeb3b; border-radius: 8px; margin: 1em 0;">
  <strong>Proof.</strong> $W.L.O.G$, we will only prove the continuous case. Note $\tau(\theta) = \mathbb{E}_{\theta}\{ T(\vec X)\}, \forall \theta \in \Theta$, so

  $$
\begin{align*}
\frac{d}{d\theta} \tau(\theta) &= \frac{d}{d\theta} \left\{ \mathbb{E}_{\theta}[T(\vec X)] \right\}\\
&=\frac{d}{d\theta} \left\{ \int_{\mathcal{S}} T{(\vec x)} p_{\theta}(\vec x) d\vec x \right\}\\
&= \int_{\mathcal{S}} T(\vec x) \cdot \frac{d}{d\theta} p_{\theta}(\vec x) d \vec x\\
&= \int_{\mathcal{S}} T(\vec x) \frac{d}{d\theta} [ \log p_{\theta}(\vec x) ]p_{\theta}(\vec x) d\vec x.
\end{align*}
$$

Therefore, 

$$
\tau'(\theta) = \mathbb{E}_{\theta}\left\{ T(\vec X) \frac{d}{d\theta} [\log p_{\theta}(\vec x)] \right\}, \forall \theta \in \Theta.
$$

On the other hand, by (\romannumeral 3), if $h(\vec x) \equiv 1$, then

$$
0 = \int_{\mathcal{S}} \frac{d}{d\theta} p_{\theta}(\vec x) d\vec x= \int_{\mathcal{S}} \left[ \frac{d}{d\theta} \log p_{\theta}(\vec x) \right] p_{\theta}(\vec x) d\vec x, \forall \theta \in \Theta.
$$

Thus we have

$$
\mathbb{E}_{\theta} \left\{ \frac{d}{d\theta} \log p_{\theta}(\vec x) \right\}=0, \forall \theta \in \Theta.
$$

The equation above is also known as the Bartlett Identity.

So now we have

$$
\tau'(\theta) = \mathbf{Cov}\left( T(\vec X), \frac{d}{d\theta} \log p_{\theta}(\vec x) \right), \forall \theta \in \Theta
$$

and hence by Cauchy-Schwarz inequality, we have

$$
\begin{align*}
[\tau'(\theta)]^2 & = \Cov^2\left( T(\vec X), \frac{d}{d\theta} \log p_\theta (\vec x) \right)\\
& \leq \mathbf{Var}_\theta (T(\vec X)) \cdot \mathbf{Var}_\theta \left( \frac{d}{d\theta} \log p_\theta (\vec x) \right).
\end{align*}
$$

Now using Bartlett's identity, we have

$$
[\tau'(\theta)]^2 \leq \mathbf{Var}_\theta(T(\vec X)) \cdot \mathbb{E}_\theta \left\{ \left[ \frac{d}{d\theta} \log p_\theta(\vec x)\right]^2 \right\}.
$$
</div>




Note that if we have $X_1,\cdots,X_n \overset{i.i.d}{\sim} f(x,\theta)$, then by definition

$$
p_\theta(\vec x) = \prod_{i=1}^n f(\theta,x_i)
$$


hence in this case

$$
\mathbb{E}\left\{ \left[ \frac{d}{d\theta} \log p_\theta(\vec x) \right]^2\right\} = n \mathbb{E}\left\{ \left[ \frac{d}{d\theta} \log f(\theta,x_i) \right]^2\right\}.
$$

and now

$$
\mathbf{Var}_\theta(T(\vec X)) \geq \frac{[\tau'(\theta)]^2}{n I_i(\theta)}
$$


sometimes it is easier to compute the Fisher information for one sample, we may do so and multiply by $n$ in the end, with the assumption that we are working with random sample (i.i.d).



<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> (Second Bartlett's Identity) We have
  
$$
\mathbb{E}\left\{ \left[ \frac{d}{d\theta} \log p_\theta (\vec x) \right]^2\right\} = -\mathbb{E}\left\{ \frac{d^2}{d\theta^2} \log p_\theta (\vec x) \right\}.
$$
</div>

<div style="background-color: #fff9cc; padding: 1em; border-left: 6px solid #ffeb3b; border-radius: 8px; margin: 1em 0;">
  <strong>Proof.</strong> Using Chain rule, we have
  
$$
\frac{d^2}{d\theta^2} \log p_\theta(\vec x) = \frac{p^{''}_\theta (\vec x)}{p_\theta (\vec x)} - \left[ \frac{d}{d\theta} \log p_\theta(\vec x) \right]^2
$$

and taking expectation on both sides, we have

$$
\mathbb{E}\left\{ \frac{d^2}{d\theta^2} \log p_\theta (\vec x)\right\} = \mathbb{E}\left\{ \frac{p^{''}_\theta(\vec x)}{p_\theta(\vec x)} \right\} - \mathbb{E}\left\{ \left[ \frac{d}{d\theta} \log p_\theta (\vec x) \right]^2\right\}
$$

where the first term on the right hand side of the equation equals $0$, because

$$
\frac{d}{d\theta} \mathbb{E}\left\{ \frac{d}{d\theta} \log p_\theta(\vec x) \right\} = \int_\mathcal{S} \frac{d}{d\theta} \left\{ \frac{d}{d\theta} \log p_\theta (\vec x)\right\} p_\theta(\vec x) dx.
$$
</div>



**Example:** Suppose we have a random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(\theta)$, its probability mass function is given by $f(x,\theta) = \theta^x (1-\theta)^{1-x}, x \in \{0,1\}$ and $\theta \in (0,1)$. Find the CRLB of all unbiased estimator of $\tau(\theta) = \theta$.

**Solution:** We first find the Fisher information. We investigate the function

$$
\log f(\theta,x_i) = x_i \log\theta + (1-x_i) \log(1-\theta)
$$

and

$$
\frac{d}{d\theta} \log f (\theta,x_i) = \frac{x_i}{\theta} - \frac{1-x_i}{1-\theta}, \hspace{0.3cm}\frac{d^2}{d\theta^2} \log f(\theta,x_i) = -\frac{x_i}{\theta^2} + \frac{1-x_i}{(1-\theta)^2}
$$


by Bartlett's identity, we have

$$
I_i(\theta) = -\mathbb{E}\left\{ -\frac{X_i}{\theta^2} + \frac{1-X_i}{(1-\theta)^2}\right\} = \frac{1}{\theta(1-\theta)}.
$$


Now $\tau(\theta) = \theta$ so $[\tau'(\theta)]^2 = 1$ hence the CRLB is given by

$$
\mathbf{Var}_\theta(T(\vec X)) \geq \frac{1}{n I_i(\theta)} = \frac{\theta(1-\theta)}{n}.
$$


An unbiased estimator of $\tau(\theta)$ might be the UMVUE, but its variance could be larger than the CRLB. That is, CRLB is not a sharp lower bound.

<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Suppose that $\vec X =(X_1,\cdots,X_n)$ and we have a joint pdf $p_\theta(\vec x)$, and $T(\vec X)$ be unbiased for $\tau(\theta)$, then $T(\vec X)$ attains the CRLB if and only if
  
$$
a(\theta) \cdot \{ T(\vec X) - \tau(\theta)\} = \frac{d}{d\theta} \log p_\theta(\vec x)
$$

for some function $a(\theta)$ and for all $\theta \in \Theta$.
</div>



**Example:** We say $f_\theta(x)$ belongs to  exponential family \textit{(note that you may find me use $f_\theta(x), f(x,\theta), f(x|\theta)$, they are all the same notation, meaning $\theta$ is our parameter, but the density function is a function of $x$)}, if its density function takes the form

$$
f_\theta(x) = h(x) \cdot c(\theta) \cdot \exp\{ \omega(\theta) \cdot T(x)\}
$$

for some non-negative function $h(x)$ of $x$ and $c(\theta)$ of $\theta$, and $T(x)$ is a function of $x$, also its support does not depend on $\theta$. Then show that if a random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} f_\theta(x)$ where $f_\theta(x)$ belongs to exponential family, then

$$
T(\vec x) = \frac{1}{n} \sum_{i=1}^n T(x_i)
$$

is the UMVUE of $\tau(\theta) = -c'(\theta) / (c(\theta) \omega'(\theta))$.


**Solution:** Fist of all, the joint pdf of the sample takes the form

$$
p_\theta(\vec x) = \left( \prod_{i=1}^n h(x_i) \right) c(\theta)^n \cdot \exp\left\{ \omega(\theta) \cdot \sum_{i=1}^n T(x_i) \right\}
$$

so we have

$$
\frac{d}{d\theta} \log p_\theta(\vec x) = n \cdot \frac{c'(\theta)}{c(\theta)} + \omega'(\theta) \cdot \sum_{i=1}^n T(x_i) = \omega'(\theta) \cdot \left\{ \sum_{i=1}^n T(x_i) - \frac{-n c'(\theta)}{c(\theta) \omega'(\theta)}\right\}.
$$

By the previous theorem, it suffies to check $T(\vec X)$ is unbiased. Using Bartlett's identity, we know that $\displaystyle{\mathbb{E}\left\{ \frac{d}{d\theta} \log p_\theta(\vec x)\right\} = 0}$, which means

$$
\mathbb{E}\left\{ \sum_{i=1}^n T(\vec X_i)\right\} = n \tau(\theta)
$$


hence $T(\vec X) = \displaystyle{\frac{1}{n} \sum_{i=1}^n T(X_i)}$ is unbiased, and by the previous theorem, it is the UMVUE.

**Example:** Let a random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Poisson(\theta)$ with density $\displaystyle{f(x,\theta) = e^{-\theta} \frac{\theta^x}{x!}}$, $x \in \mathbb{N}_0$.

* find the UMVUE of $\theta$.

* Find the CRLB of all estimates of $\theta$.

**Solution:**

1. We rewrite the density of Poisson distribution as
   
$$
f(x,\theta) = \frac{e^{-\theta}}{x!} e^{x \log\theta}
$$

let $h(x) = 1/x! , c(\theta) = e^{-\theta}, \omega(\theta) = \log(\theta), T(x) = x$, and its support $x \in \mathbb{N}_0$ does not depend on $\theta$, so it belongs to exponential family, then we use the result from the previous example, now $\tau(\theta) = \theta$, so the UMVUE is just the sample mean, given by

$$
UMVUE(\theta) = \frac{1}{n} \sum_{i=1}^n X_i.
$$


2. By direct computation, we have
   
$$
\frac{d}{d\theta} \log f(x,\theta) = -1 + \frac{x}{\theta}, \frac{d^2}{d\theta^2} \log f(x,\theta) = -\frac{x}{\theta^2}
$$

so using Bartlett's identity, the Fisher information of one sample is given by

$$
I(\theta) = -\mathbb{E}\left\{ \frac{d^2}{d\theta^2} \log f(X,\theta)\right\} = \mathbb{E}\left\{ -\frac{X}{\theta^2}\right\} = \frac{1}{\theta}
$$

since $X \sim Poisson(\theta)$, hence the CRLB can be computed by

$$
CRLB = \frac{[\tau'(\theta)]^2}{nI(\theta)} = \frac{\theta}{n}.
$$













