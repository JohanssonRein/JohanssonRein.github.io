---
title: "Unbiased Estimators"
collection: publications
category: statistics
permalink: /publication/randomsamples
order: 2
excerpt: 'We will investigate some basic theories of unbiased estimators'
date: 2025-01-15
venue: 'Winter'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Unbiased Estimators'
---

In what follows we mainly focus on parametric inference, $X \sim F_{\theta}$ given by

$$
\mathcal{F} := \{ F_{\theta} : \vec \theta \in \Theta \subset \mathbb{R}^d\} \hspace{0.2cm} \vec \theta = \begin{pmatrix} \theta_1 \\ \theta_2 \\ \vdots \\ \theta_n \end{pmatrix}
$$

where $\Theta$ is the parameter space and $X_1,\cdots,X_n \overset{i.i.d}{\sim} F$ to be the random sample.

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> We define $\hat{\theta}(X_1,\cdots,X_n) \equiv \hat{\theta}_n$ is an estimator of a parameter $\theta$ if it is a statistic, that is it does not depend on any unknown parameter.
</div>



Thus an estimator $\hat{\theta}$ is also a random variable.

**Remark:** Here our key assumption is that $n>>d$, that is, the sample size is really large compared to the known data. We define $\hat{\theta}(x_1,\cdots,x_n)$ (post experimental data) to be an estimate of $\theta$, and $\hat{\theta}(X_1,\cdots,X_n)$ to be an estimator of $\theta$.

**Example:** Let $X$ be a random selected chip from a large sample and denote

$$
X = \begin{cases} 1 &\text{if the chip is operational} \\ 0 & \text{otherwise} \end{cases}
$$

We may assume $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(\theta)$ and $\theta$ is the probability that the randomly selected chip is operational. In this case we have the following possible estimators of $\theta$, as long as it is a function of $X_1,\cdots,X_n$:

$$
\overline{X}_n ; \frac{X_1+X_2}{2};X_5
$$

But $X_1+\theta$ is not an estimator! Since it is also a function of $\theta$.

We may come up with many possible estimators for a parameter $\theta$, but how do we choose the good estimators? In general, we would like to choose estimators that work well on average.



<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> An estimator $\hat{\theta}_n = \hat{\theta}_n(X_1,\cdots,X_n)$ is an ``unbiased'' estimator of $\theta$ if $\forall \theta \in \Theta$, $\E_{\theta}\{ \hat{\theta}_n \} = \theta$.
</div>



We also define the biased estimator to be

$$
Bias(\hat{\theta}_n) = \E_{\theta} \{ \hat{\theta}_n \} - \theta.
$$

Recall from the previous example where we have $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(\theta)$, and the estimators we introduced before, i.e $\overline{X}_n ; \displaystyle{\frac{X_1+X_2}{2}}, X_5$ are all unbiased indeed!


**Example:** Suppose we have $X_1,\cdots,X_n \overset{i.i.d}{\sim} F_{\theta}$ where $\theta = \begin{pmatrix} \mu \\ \sigma^2 \end{pmatrix}, \mu = \E X_i, \sigma^2 = \Var(X_i)$, then

$\bullet$ $\displaystyle{\hat{\mu}_n = \overline{X}_n = \frac{1}{n} \sum_{i=1}^n X_i}$ is an unbiased estimator of $\mu$.

$\bullet$ $\displaystyle{\hat{\sigma}_n^2 = S_n^2 = \frac{1}{n-1} \sum_{i=1}^n (X_i - \overline{X}_n)^2}$ is  an unbiased estimator of $\sigma^2$. To see this, we have

$$
\begin{align*}
S_n^2 = \frac{1}{n} \sum_{i=1}^n (X_i - \overline{X}_n)^2
\end{align*}
$$

Thus

$$
\begin{align*}
\E_{\theta}\{ \hat{\sigma}_n^2\} &= \frac{1}{n-1} \E_{\theta} \left\{ \sum_{i=1}^n X_i^2 - n\overline{X}_n^2 \right\}\\
&= \frac{1}{n-1} \left\{ \sum_{i=1}^n \E_{\theta}(X_i^2) - n \E_{\theta}(\overline{X}_n^2) \right\}\\
&= \frac{1}{n-1} \left\{ \sum_{i=1}^n (\sigma^2+\mu^2) - n \left[ \frac{\sigma^2}{n} + \mu^2 \right] \right\}\\
&= \frac{n-1}{n-1}\sigma^2 = \sigma^2.
\end{align*}
$$


**Remark:** $\displaystyle{\frac{1}{n}\sum_{i=1}^n} (X_i - \overline{X}_n)^2$ is also a good estimator for the variance, but this estimator is biased!

**Example:** Suppose we have $X_1,\cdots,X_n \overset{i.i.d}{\sim} Uniform(0,\theta)$, $\theta>0$ is out target parameter, then the estimator $\hat{\theta}_{n,1} = 2X_3, \hat{\theta}_{n,2} = 2\overline{X}_n$ are all unbiased, but $\hat{\theta}_{n,3} = X_{(n)} := \max_{1 \leq i \leq n}(X_1,\cdots,X_n)$ is biased, since $\E\{\hat{\theta}_{n,3}\} = \frac{n}{n+1}\theta$. A way to correct the bias of $\hat{\theta}_{n,3}$ would be $\hat{\theta}_{n,4} = \frac{n+1}{n} X_{(n)}$.

As we see from the previous examples, for a parameter $\theta \in \Theta \subset \mathbb{R}^d$ we could come up with unbiased estimators. Another criterion that we could bring into our assessment of an estimator is its variance $\Var_{\theta}\{ \hat{\theta}_n \}$, if exists.

In the class of unbiased estimator, we could choose the one that has the smallest variance.

Another criterion is MSE (Mean Square Error), namely

$$
MSE_{\theta}(\hat{\theta}_n) = \E_{\theta}[(\hat{\theta}_n^2 - \theta)^2].
$$

Note that

$$
MSE_{\theta}(\hat{\theta}_n) = \E_{\theta}[(\hat{\theta}_n - \E_{\theta}(\hat{\theta}_n) + \E_{\theta}(\hat{\theta}_n)-\theta)^2] = \Var_{\theta}(\hat{\theta}_n) + [Bias(\hat{\theta}_n)]^2.
$$


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> An estimator $\hat{\theta}_n$ of $\theta$ is called consistent if $\hat{\theta} \overset{P}{\to} \theta$ as $n \to \infty$.
</div>

































