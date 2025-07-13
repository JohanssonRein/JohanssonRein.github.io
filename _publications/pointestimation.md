---
title: "Three Methods for Point Estimation: Mathods of Moments; Bayesian Estimation and MLE"
collection: publications
category: statistics
permalink: /publication/pointestimation
order: 6
excerpt: 'We will investigate three methods for point estimation: methods of moments, Bayesian estimation, MLE'
date: 2025-01-30
venue: 'Winter'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Three Methods for Point Estimation: Mathods of Moments; Bayesian Estimation and MLE'
---



# Methods of Moments

In methods of moments, we simply match the $k$th moment with the $k$th sample moment. Let $X_1,\cdots,X_n \overset{i.i.d}{\sim} f(\theta,x)$ where $\theta \in \Theta \subset \mathbb{R}^d$, so our parameter of interest is $\vec\theta = (\theta_1,\cdots,\theta_d)^T$. With the assumption that $\mathbb{E}\vertX_i\vert^d$ exists, we denote the $j$th population moments as

$$
\mu_j(\vec\theta) = \mathbb{E} X_i^j
$$

and the $j$th sample moments as

$$
m_j(\vec X) = \frac{1}{n} \sum_{i=1}^n X_i^j.
$$


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> In methods of moment estimator, we will match each population moment and sample moment and solve the corresponding systems of equations. That is, we set
  
$$
m_j(\vec X) = \frac{1}{n} \sum_{i=1}^n X_i^j \overset{\text{set}}{=} \mu_j(\vec\theta) = \mathbb{E} X_i^j
$$

where $j=1,\cdots,d$ and solve the corresponding system of equations.
</div>



We need to note that in general $m_j(\vec X) \neq \mu_j(\vec\theta)$, it is only an estimate. Hence by solving the system of equations, we will have the estimate of $\theta_j$ as a function of $m_1,\cdots,m_d$:

$$
\hat{\theta}_j = g_j(m_1,\cdots,m_d)
$$


**Example:** Find the methods of moments estimator of a normal random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} N(\mu,\sigma^2)$.

**Solution:** Here we have two parameters so we have $\vec\theta = (\mu,\sigma^2)^T$ and we match each sample moment with population moment up to $d=2$:

$$
m_1(\vec X) = \frac{1}{n} \sum_{i=1}^n X_i = \mu_1(\vec\theta) = \mathbb{E} X_i = \mu;
$$

$$
m_2(\vec X) = \frac{1}{n} \sum_{i=1}^n X_i^2 = \mu_2(\vec\theta) = \mathbb{E} X_i^2 = \sigma^2 + \mu^2.
$$

So if we solve the above system of equations, we will get

$$
\begin{cases} 
\hat{\mu} &= \displaystyle{\overline{X}_n}\\
\\
\hat{\sigma}^2 &=\displaystyle{ \frac{1}{n} \sum_{i=1}^n \left(X_i - \overline{X}_n\right)^2}
\end{cases}
$$

as the methods of moments estimator. Notice here the estimate of $\sigma^2$ us biased, since we previously shown that $\displaystyle{\frac{1}{n-1} \sum_{i=1}^n (X_i - \overline{X}_n)^2 }$ is unbiased. But asymptotically, using weak law of large numbers and continuous mapping theorem, our methods of moments estimate will converge to real $\sigma^2$ in probability, that is $\hat{\sigma}^2 \overset{P}{\to} \sigma^2$.

Methods of moments estimator may not always exist, since we need to assume the existence of $\mathbb{E}\vert X_i\vert^d$.


# Bayesian Estimation


The idea of Bayesian estimation is to work with conditional probability, and we treat the parameter $\theta$ as another random variable having its owning distribution, called the *prior distribution* of $\theta$, so in this case $p_\theta(\vec x)$ is the conditional distribution given $\theta$, usually denote as $p(\vec x \vert \theta)$.


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} f(x,\theta)$ with joint density $p_\theta(\vec x)$, assume the prior distribution of $\theta$ is given by $\pi(\theta)$, then the posterior distribution of $\theta$ given data $\vec x$ is defined by
  
$$
\pi(\theta\vert\vec x) = \frac{p_\theta(\vec x) \cdot \pi(\theta)}{\displaystyle{\int_{\Theta} p_\theta(\vec x) \cdot\pi(\theta)d\theta}}.
$$
</div>



The prior distribution $\pi(\theta)$ reflects our original belief about $\theta$, it is pre-determined. Then the posterior distribution $\pi(\theta\vert\vec x)$ can be viewed as an update of our belief about $\theta$ given the observed sample using conditional probability.


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Given data $\vec X = (X_1,\cdots,X_n)$, the loss function $L(\delta(\vec X), \theta)$ measures the loss when $\theta$ is estimated by $\delta(\vec X)$. The Bayes' risk of $\delta(\vec X)$ is defined by
  
$$
R(\delta(\vec X)) = \mathbb{E}_{\pi} \{ \mathbb{E}_{x\vert\theta} [L(\delta(\vec X),\theta)]\}.
$$

The Bayes estimator is given by $\hat{\delta(\vec X)}_{\text{Bayes}} = \arg \min_{\delta(\vec X)} R(\delta)$.
</div>




By definition, we may compute $R(\delta(\vec X))$:

$$
\begin{align*}
R(\delta(\vec X)) &= \int_{\Theta} \int_X L(\delta(\vec X), \theta) p_\theta(\vec x)d\vec x\pi(\theta) d\theta\\
&=\int_X \int_{\Theta} L(\delta(\vec X),\theta) \pi(\theta \vert \vec x) d\theta p_\theta(\vec x) dx\\
&=\int_\Theta L(\delta(\vec X),\theta) \pi(\theta\vert\vec x)d\theta
\end{align*}
$$


One common loss function is squared-error loss: $L(\delta(\vec X) - \theta) = (\delta(\vec X) - \theta)^2$, using this loss function, we have

$$
\begin{align*}
\hat{\delta(\vec X)}_{\text{Bayes}} &= \arg\min_{\delta(\vec X)} \left\{ \int_\Theta (\delta(\vec X) - \theta)^2 \pi(\theta\vert\vec x) d\theta\right\}
\end{align*}
$$

now in order to find the $\delta(\vec X)$ that minimizes the term above, we differentiate with respect to $\delta(\vec X)$ and we have

$$
\frac{df}{d\delta(\vec X)} =  \int_\Theta 2(\delta(\vec X) - \theta) \pi(\theta\vert\vec x)d\theta
$$


set the derivative equal to $0$ and we solve for $\delta(\vec X)$:

$$
\delta(\vec X)\int_\Theta \pi(\theta\vert\vec x)d\theta = \int_\Theta \theta \pi(\theta\vert\vec x)d\theta
$$

while the integral on the left hand side is equal to $1$, and hence we have

$$
\delta(\vec X) = \int_\Theta \theta \pi(\theta\vert\vec x) d\theta = \mathbb{E}[\theta\vert\vec X = \vec x].
$$


Hence under square error loss, the Bayesian estimator of $\theta$ is simply the mean of the posterior function.

**Example:** Consider the random sample $X_1,\cdots,X_n \sim Uniform(0,\theta)$, and the prior distribution for $\theta$ is given by

$$
\pi(\theta) = \frac{\alpha \beta^\alpha}{\theta^{\alpha+1}}, \alpha,\beta>0;\theta>1
$$

Find the Bayes estimator of $\theta$ under the squared error loss.

**Solutions:** Recall that the posterior distribution takes the form

$$
\pi(\theta\vert x) = \frac{p(x\vert\theta)\pi(\theta)}{\displaystyle{\int_\Theta p(x\vert\theta)\pi(\theta)d\theta}}
$$

where

$$
\begin{align*}
p(x\vert\theta)\pi(\theta) &= \left(\frac{1}{\theta}\right)^n \cdot \chi\{ X_{(1)} >0\} \chi\{ X_{(n)} <\theta\} \cdot \frac{\alpha\beta^\alpha}{\theta^{\alpha+1}} \cdot \chi\{ \theta>1\}\\
&=\theta^{-(n+\alpha+1)} \cdot \alpha \beta^\alpha \cdot \chi\{ \theta > \max\{1, X_{(n)}\}\} \cdot \chi\{ X_{(1)}>0\}.
\end{align*}
$$

So it follows that 

$$
\begin{align*}
\int_{\Theta} p(x\vert\theta) \pi(\theta)d\theta &= \int_{T(\vec X)}^\infty \theta^{-(n+\alpha+1)} \alpha \beta^\alpha \chi\{ X_{(1)} >0\}d\theta \hspace{0.2cm} \text{where $T(\vec X) = \max\{ 1, X_{(n)}\}$}\\
&= \chi\{ X_{(1)}>0\} \alpha\beta^\alpha \left[ -\frac{1}{n+\alpha} \theta^{-(n+\alpha)} \right]\Bigg\vert_{\theta = T(\vec X)}^{\infty}\\
&= \chi\{ X_{(1)} >0\} \alpha\beta^\alpha \left[ \frac{1}{n+\alpha} (T(\vec X))^{-(n+\alpha)} \right]
\end{align*}
$$

so now the posterior distribution is the ratio of what we get, and we can simplify to

$$
\pi(\theta\vert x) = (n+\alpha) \cdot\left( \frac{1}{\theta}\right)^{n+\alpha+1} \cdot [T(\vec X)]^{-(n+\alpha)}; \theta>T(\vec X).
$$

Now, under the squared error loss, the Bayes estimator of $\theta$ is given by the expected value of the posterior distribution, hence

$$
\begin{align*}
\hat\theta_{\text{Bayes}} = \mathbb{E}[\pi(\theta\vert x)] &= \int_{T(\vec X)}^\infty \theta \cdot (n+\alpha)\cdot \theta^{-(n+\alpha+1)} \cdot [T(\vec X)]^{-(n+\alpha)} d\theta\\
&= (n+\alpha) \cdot [T(\vec X)]^{-(n+\alpha)} \int_{T(\vec X)}^\infty \theta^{-(n+\alpha)} d\theta\\
&= \frac{n+\alpha}{-(n+\alpha)+1} [T(\vec X)]^{-(n+\alpha)} [ \theta^{-(n+\alpha)+1}]\Bigg\vert_{\theta = T(\vec X)}^\infty\\
&= \frac{n+\alpha}{n+\alpha-1}T(\vec X).
\end{align*}
$$

where $T(\vec X) = \max\{ 1, X_{(n)}\}$.

**Example:** Consider the random sample $X_1,\cdots,X_n \overset{i.i.d}{\sim} Bernoulli(\theta)$, and the prior distribution of $\theta$ is $\pi(\theta) \sim Beta(\alpha,\beta), \alpha,\beta>0$. Under square error loss, find the Bayesian estimator of $\theta$. The Beta distribution has density

$$
\pi(\theta) \sim Beta(\alpha,\beta) = \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)} \theta^{\alpha-1} (1-\theta)^{\beta-1}.
$$


**Solution:** Note that in the formula

$$
\pi(\theta\vert x) = \frac{p(x\vert\theta)\pi(\theta)}{\displaystyle{\int_\Theta p(x\vert\theta)\pi(\theta)d\theta}},
$$

the denominator is independent of $\theta$, hence we have

$$
\begin{align*}
\pi(\theta\vert\vec x) &\propto p_\theta(\vec x) \cdot \pi(\theta)\\
&= \theta^{\sum x_i} (1-\theta)^{n-\sum x_i} \cdot \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)} \theta^{\alpha-1} (1-\theta)^{\beta-1}\\
&= \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)} \theta^{n \overline{x}_n + \alpha-1} \cdot (1-\theta)^{n-n\overline{x}_n + \beta-1}
\end{align*}
$$


which we see it takes the form of another Beta distribution, and if we match the coefficients, we would have the posterior distribution given by

$$
\pi(\theta\vert\vec x) \sim Beta(n\overline{x}_n+\alpha, n - n\overline{x}_n + \beta).
$$

Then under square error loss, the Bayes estimator is just the mean of the posterior distribution, given by

$$
\hat{\delta}(\vec X)_{\text{Bayes}} = \mathbb{E}[\pi(\theta\vert\vec x)] = \frac{n\overline{X}_n+\alpha}{n+\alpha+\beta}.
$$
























