---
title: "Two More Methods for UMVUE: Rao-Blackwell and Lehmann-Scheffe"
collection: publications
category: statistics
permalink: /publication/umvue2
order: 5
excerpt: 'We will investigate two more methods for UMVUE: Rao-Blackwell and Lehmann-Scheffe'
date: 2025-01-25
venue: 'Winter'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Two More Methods for UMVUE: Rao-Blackwell and Lehmann-Scheffe'
---

In this section we propose two more methods to compute the UMVUE.

<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Rao-Blackwell) Let $U(\vec X)$ be an unbiased estimator of $\tau(\theta)$ if exists, let $T(\vec X)$ be a sufficient statistic of the parameter family, set
  
$$
\delta(t) = \mathbb{E}\{ U(\vec X) \vert T(\vec X) = t\}
$$

then we claim that:

(1) $\delta(T(\vec X))$ is a statistic, also an unbiased estimator of $\tau(\theta)$;

(2) $\mathbf{Var}\{ \delta(T(\vec X)) \leq \mathbf{Var}(U(\vec X))\}$.

Furthermore, if $T(\vec X)$ is complete, then the resulting $\delta(T(\vec X))$ is the UMVUE of the parameter family.
</div>


**Proof:**

Firstly since $T(\vec X)$ is sufficient, so it is easy to verify $\mathbb{E}\{ U(\vec X \vert \vec T(\vec X))\}$ does not depend on $\theta$ and is hence a statistic, then

$$
\mathbb{E}\{ \delta(\vec X)\} = \mathbb{E}\{\mathbb{E}\{U(\vec X|T(\vec X))\}\} = \mathbb{E}\{ U(\vec X)\} = \tau(\theta)
$$

which means $\delta(\vec X)$ is unbiased. Finally

$$
\begin{align*}
\mathbf{Var}\{ U(\vec X)\} &= \mathbf{Var}\{ \mathbb{E}\{ U(\vec X) | T(\vec X)\}\} + \mathbb{E}\{\mathbf{Var}\{ U(\vec X) | T(\vec X)\}\}\\
&= \mathbf{Var}\{ \delta(T(\vec X))\} + \mathbb{E}\{ \mathbf{Var}(U(\vec X| T(\vec X)))\}\\
& \geq \mathbf{Var}\{ \delta(T(\vec X))\}.
\end{align*}
$$


**Q.E.D**


Rao-Blackwell theorem says that, by conditioning ant unbiased estimator on a sufficient statistic will result in a uniform improvement in terms of variance, and if we condition on a complete sufficient statistic, we would result in UMVUE.

<!-- Example Block -->
<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Consider a random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(p)$, $0<p<1$. For $n \geq 4$, find the UMVUE of $\tau(p) = p^4$.


  <!-- Collapsible Solution -->
  <details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide solution</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Solution.</strong><br>
     Firstly, since $\mathbb{E} X_i = p$, so $T^*(\vec X) = X_i$ is simply an unbiased estimator of $p$, and by independence, we can easily see that $X_1X_2X_3X_4$ is an unbiased estimator for $p^4$. Now since the joint pdf of the random sample is given by
      
$$
f(\vec x,p) = p^{n\overline{x}_n}(1-p)^{n-n\overline{x}_n} = \left( \frac{p}{1-p} \right)^{n\overline{x}_n} \cdot(1-p)^n
$$


so by Neyman-Fisher theorem, $T(\vec X)$ is a sufficient statistics, and furthermore it is complete (because it belongs to exponential family and we have established some properties before). So by Rao-Blackwell theorem, the UMVUE for $p^4$ is given by

$$
\begin{align*}
\delta(\vec X) &= \mathbb{E}\left[ X_1X_2X_3X_4 \Bigg| \sum_{i=1}^n X_i = t \right]\\
&=1\times \mathbb{P}\left( X_1X_2X_3X_4 = 1 \Bigg| \sum_{i=1}^n X_i = t \right) + 0 \times \mathbb{P}\left( X_1X_2X_3X_4 = 0 \Bigg| \sum_{i=1}^n X_i = t \right)\\
&=\frac{\displaystyle{\mathbb{P}\left( X_1X_2X_3X_4 = 1 , \sum_{i=1}^n X_i = t \right)}}{\displaystyle{\mathbb{P}\left(\sum_{i=1}^n X_i = t \right)}}\\
&=\frac{\displaystyle{p^4 \cdot \binom{n-4}{t-4}p^{t-4}(1-p)^{n-t}}}{\displaystyle{\binom{n}{t}p^t(1-p)^{n-t}}}\\
&=\frac{\displaystyle{\binom{n-4}{t-4}}}{\displaystyle{\binom{n}{t}}}
\end{align*}
$$

where $\displaystyle{t = \sum_{i=1}^n X_i}$. This is the UMVUE of $\tau(\theta) = p^4$.


**Remark:** *It is completely doable if I make $\tau(\theta) = p^{2025}$!*
    </div>
  </details>
</div>


Let's see a harder problem:

<!-- Example Block -->
<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Consider a random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(p)$, then define
  
$$
h(p) = \mathbb{P}\left( \sum_{i=1}^{n-1} X_i > X_n \right),
$$

find the UMVUE of $h(p)$.

  <!-- Collapsible Solution -->
  <details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide solution</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Solution.</strong><br>
       First we define the estimator as the indicator function
      
$$
T(\vec X) = \mathbf{1}\left\{ \sum_{I=1}^{n} X_i > X_{n+1} \right\} = \begin{cases} 1 & X_1+\cdots+X_{n} > X_{n+1} \\ 0 & \text{otherwise} \end{cases}
$$

It is easy to show $T(\vec X)$ is unbiased, since 

$$
\mathbb{E}[T(\vec X)] = 1\times \mathbb{P}(T(\vec X) = 1) +0\times \mathbb{P}(T(\vec X) = 0)) = h(p).
$$

Then from the previous example we already showed that $\displaystyle{\sum_{i=1}^{n} X_i}$ is a complete sufficient statistics of $p$, then by Rao-Blackwell theorem, the UMVUE s given by

$$
\begin{align*}
\delta(\vec X) &= \mathbb{E}\left[ h(p) \Bigg| \sum_{i=1}^n X_i = t \right]\\
&= \mathbb{P}\left( \sum_{i=1}^n X_i > X_{n+1} \bigg| \sum_{i=1}^n X_i = t \right)\\
&= \frac{\mathbb{P}\left(\displaystyle{\sum_{i=1}^n X_i > X_{n+1},\sum_{i=1}^n X_i = t}\right)}{\mathbb{P}\left(\displaystyle{\sum_{i=1}^n X_i = t}\right)}\\
&=\frac{\displaystyle{\mathbb{P}\left(\displaystyle{\sum_{i=1}^n X_i > X_{n+1},\sum_{i=1}^n X_i = t}\right)}}{\displaystyle{\binom{n}{t}p^t(1-p)^{n-t}}}
\end{align*}
$$


We will now investigate the numerator, denote the numerator to be $N$

If $t=0$, then $N=0$;

If $t=1$, then

$$
N = \binom{n}{1}p(1-p)^{n-1} \times(1-p)
$$

If $t \geq 2$, then

$$
N = \binom{n}{t} p^t(1-p)^{n-t} \times (1-p) + \binom{n}{t}p^t(1-p)^{n-t}\times p
$$

So in all, we have

$$
\delta(\vec X) = 
\begin{cases}
0 & t=0\\
\\
\displaystyle{\frac{\binom{n}{1}p(1-p)^{n-1} \times(1-p)}{\binom{n}{t}p^t(1-p)^{n-t}} = \frac{\binom{n}{1}}{\binom{n}{t}}} & t=1\\
\\
\displaystyle{\frac{\binom{n}{t} p^t(1-p)^{n-t} \times (1-p) + \binom{n}{t}p^t(1-p)^{n-t}\times p}{\binom{n}{t}p^t(1-p)^{n-t}}} = 1 & t\geq 2
\end{cases}
$$

where $\displaystyle{t= \sum_{i=1}^n X_i}$, and this is the UMVUE.
    </div>
  </details>
</div>




Another way to find UMVUE is proposed as follows:


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Lehmann-Scheffe) Let $U(\vec X)$ be an unbiased estimator of the parameter family, if $U(\vec X)  = g(T(\vec X))$ for some measurable function $g$ and a complete sufficient statistic $T(\vec X)$, then $U(\vec X)$ is the UMVUE of the parameter family.
</div>



That is, as long as we could write the unbiased estimator as a function of complete sufficient statistic, then the unbiased estimator is the UMVUE.

**Example:** Again let's consider the Bernoulli random sample, we have shown that $\displaystyle{T(\vec X) = \sum_{i=1}^n X_i}$ is a complete and sufficient statistic, also we have

$$
\mathbb{E}\left[ \frac{X_1+\cdots+X_n}{n} \right] = p
$$

which is unbiased. Note that inside the expected value is a function of the complete and sufficient statistic, so by using Lehmann-Scheffe directly, the UMVUE of $p$ is just $\displaystyle{U(\vec X) = \frac{1}{n} \sum_{i=1}^n X_i }$.


**Example:** Again onsider the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(\theta)$, find the UMVUE of $\tau(\theta) = \theta(1-\theta)$.

**Solution:** By the properties of Bernoulli random variables, we know that $\mathbf{Var}(X_i) = \theta(1-\theta)$. Furthermore it can be estimated by the sample variance (unbiased):

$$
S_n^2 = \frac{1}{n-1} \sum_{i=1}^n (X_i - \overline{X}_n)^2
$$

we may simplify the sample variance:

$$
S_n^2 = \frac{1}{n-1} \left( \sum_{i=1}^n X_i^2 + n \overline{X}_n^2 \right) = \frac{1}{n-1} \left( \sum_{I=1}^n X_i + n \left( \frac{X_1+\cdots+X_n}{n} \right)^2 \right)
$$

and this is because $X_i$ takes only $0,1$. Also we have shown that in a Bernoulli random sample, $\displaystyle{T(\vec X) = \sum_{i=1}^n X_i}$ is a complete sufficient statistic, then by Lehmann-Scheffe, the sample variance is the UMVUE of $\theta(1-\theta)$, and by some computation, we have

$$
U(\vec X) = \frac{n}{n-1} \overline{X}_n (1-\overline{X}_n)
$$

as the UMVUE of $\theta(1-\theta)$.



<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> An estimator $\delta(\vec X)$ is called an unbiased estimator of zero of $\mathbb{E}\{ \delta(\vec X)\} = 0$.
</div>




Here we propose a theorem that can be used to investigate the existence of a UMVUE or to determine that an estimator is not a UMVUE:



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> An unbiased estimator $U(\vec X)$ of $\tau(\theta)$ is the UMVUE if and only if $U(\vec X)$ is uncorrelated with all unbiased estimators $\delta(\vec X)$ of zero. That is,
  
$$
\mathbf{Cov}\left( U(\vec X) , \delta(\vec X) \right) = 0.
$$
</div>

<!-- Example Block -->
<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Let $\displaystyle{X\sim Uniform\left( \theta-\frac{1}{2},\theta+\frac{1}{2}\right)}, \theta\in\mathbb{R}$. Then show that if $\tau(\theta)$ is not a constant function then the UMVUE of $\tau(\theta)$ doesn't exist.

  <!-- Collapsible Solution -->
  <details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide solution</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Solution.</strong><br>
       Assume $\delta(X)$ is an unbiased estimator of zero, hence $\mathbb{E}[\delta(X)] = 0$. So we have
      
$$
\int_{\theta-1/2}^{\theta+1/2} \delta(X) = 0
$$

and by Fundamental Theorem of Calculus we have we have

$$
\delta\left(\theta+\frac{1}{2}\right) -\delta\left( \theta-\frac{1}{2}\right) = \frac{d}{d\theta} \int_{\theta-1/2}^{\theta+1/2} \delta(X) = 0
$$

Hence we have $\delta(x) = \delta(x+1)$. Now let $U(X)$ be the UMVUE of $\tau(\theta)$, then it is easy to see that $U(X)\delta(X)$ is also an unbiased estimator of zero, and by the previous theorem, we have

$$
\mathbf{Cov}(U(X),\delta(X)) = \mathbb{E}\{ U(X)\delta(X)\} = 0
$$

So now we actually have $U(x)\delta(x) = U(x+1)\delta(x+1)$. Hence $U(x) = U(x+1)$, and by definition,

$$
\mathbb{E}[U(X)] = \int_{\theta-1/2}^{\theta+1/2} U(X) dx = \tau(\theta)
$$

and we use Fundamental Theorem of calculus to get

$$
U\left(\theta+\frac{1}{2}\right) - U\left( \theta-\frac{1}{2} \right) = \tau'(\theta)
$$

and we know that $\tau'(\theta) = 0$, meaning $\tau(\theta) = C$ where it is a constant! So there is no UMVUE of $\tau(\theta)$ for any non-constant function $\tau(\theta)$.
    </div>
  </details>
</div>



 



