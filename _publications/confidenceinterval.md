---
title: "Confidence Interval"
collection: publications
category: statistics
permalink: /publication/confidenceinterval
excerpt: 'In this article we will talk about confidence interval'
date: 2025-06-01
venue: 'Summer'
slidesurl: 'http://academicpages.github.io/files/slides1.pdf'
paperurl: 'http://academicpages.github.io/files/paper1.pdf'
bibtexurl: 'http://academicpages.github.io/files/bibtex1.bib'
citation: 'Jiajun Zhang, You. (2025), part of my notes in Honors Statistics taught by Prof. Abbas Khalili'
---

Let $L(\vec X), U(\vec X)$ be two statistics such that $L(\vec x) \leq U(\vec x), \forall x\in\mathcal{X}$. A random interval $(L(\vec X),U(\vec X))$ is called an interval estimator or confidence interval with confidence level $1-\alpha, \alpha \in (0,1)$ if $P(L(\vec X) \leq \theta \leq U(\vec X)) = 1-\alpha$. Note that it is wrong to say that $(L(\vec x), U(\vec x))$ (post-experimental data) captures $\theta$ with probability $1-\alpha$. The interpretation is that this interval estimator either includes $\theta$ or not, basically it captures $\theta$ with probability $0$ or $1$. if we were to repeat the experiment and compute similar confidence intervals for $\theta$, we expect that $100(1-\alpha)\%$ of those post-experimental intervals to capture $\theta$.


**Pivot Quantity** : A random function $Q(\vec x,\theta)$ is called a pivot quantity (PQ) iff its distribution does not depend on the parameter $\theta$, and $Q$ is a function of $\vec X$ and $\theta$ only.


Note that the function $Q$ might include $\theta$, but its overall distribution $Q(\vec x,\theta)$ is free of any parameters! For example if $X \sim N(0,\theta^2)$, then $Q(x,\theta) = \frac{1}{\theta} X \sim N(0,1)$, which is free of any parameter and it is a known distribution!

Once we have a PQ, and the confidence level $1-\alpha$ is given, we may find constants $c_1,c_2$ such that 

$$
P(c_1 \leq Q(\vec x,\theta) \leq c_2) = 1-\alpha
$$

then having $c_1,c_2$ we can solve in terms of $\theta$ to get

$$
P(L(\vec X) \leq \theta \leq U(\vec X)) = 1-\alpha.
$$

Mostly, the PQ is chosen based on a sufficient statistic. Below are common random samples and their corresponding PQ and  confidence intervals:

**1. Confidence Interval for $\mu$ in a normal family:**

$\bullet$ If $\sigma^2$ is known, then

$$
Q(\vec X, \mu) = \frac{\sqrt{n} (\overline{X}_n - \mu)}{\sigma} \sim N(0,1)
$$

and the $100(1-\alpha)\%$ C.I is given by

$$
\left( \overline{X}_n - z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}} , \overline{X}_n + z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}} \right)
$$

$\bullet$ If $\sigma^2$ is unknown, then

$$
Q(\vec X,\mu) = \frac{\sqrt{n}(\overline{X}_n-\mu)}{S_n} \sim t(n-1)
$$

and the $100(1-\alpha)\%$ C.I is given by

$$
\left( \overline{X}_n - t(n-1,\alpha/2) \cdot \frac{S_n}{\sqrt{n}} , \overline{X}_n + t(n-1,\alpha/2) \cdot \frac{S_n}{\sqrt{n}}\right)
$$

*Note:  $z_p$ is called the $p$-th quantile in a standard normal distribution, and $P(Z<z_p) = p$, where $Z \sim N(0,1)$. The same idea applies in $t(n-1,\alpha/2)$, where $n-1$ indicates the degrees of freedom, and $\alpha/2$ is the quantle.*

**Example:**
A manufacturer developed a new gunpowder and tested it in eight
shells. The resulting muzzle velocities, in feet per second, were:

$$
3005, 2925, 2935, 2965, 2995, 3005, 2937, 2905.
$$
Assume that the velocities are iid sample from a $N(\mu, \sigma^2)$.
Compute a $95\%$ confidence interval for $\mu$. Provide interpretation
for your interval.

**Solution:**
So in this example, we see that $\sigma^2$ is unknown. So we replace it by $S_n$. Note that the $S_n$ of this sample can be calculated by

$$
S_n = \sqrt{S_n^2} = \sqrt{\frac{1}{7} \sum_{i=1}^8(X_i - \overline{X_n})^2}\approx   39.09 
$$

From the C.I above, we construct

$$
\left( 2959 - t(7,0.025)\cdot\frac{39.09}{\sqrt{8}},2959+t(7,0.025) \cdot \frac{39.09}{\sqrt{8}}\right).
$$

From the $t$-table, $t(7,0.025) =2.365$, so for the $95\%$ confidence interval, our final answer is $(2926.38,2991.62)$. The interpretation is that, **this interval estimator either includes $\theta$ or not, basically it captures $\theta$ with probability $0$ or $1$. if we were to repeat the experiment and compute similar confidence intervals for $\mu$, we expect that $100(1-\alpha)\%$ of those post-experimental intervals to capture $\mu$.**

**2. Confidence interval for $\sigma^2$ in a normal family:**

$\bullet$ If $\mu$ is unknown, then

$$
Q(\vec X,\sigma^2) = \frac{(n-1)S_n^2}{\sigma^2} \sim \chi_{n-1}^2
$$

and the $100(1-\alpha)\%$ C.I is given by

$$
\left( \frac{(n-1)S_n^2}{\chi^2_{(n-1,\alpha/2)}} , \frac{(n-1)S_n^2}{\chi^2_{(n-1,1-\alpha/2)}}\right).
$$

$\bullet$ if $\mu$ is known, then

$$
Q(\vec X,\sigma^2) = \frac{\sum_{i=1}^n (X_i - \mu)^2}{\sigma^2} \sim \chi_n^2
$$

and the $100(1-\alpha)\%$ C.I is given by

$$
\left( \frac{(n-1)\sum(X_i-\mu)^2}{\chi^2_{(n,\alpha/2)}}, \frac{(n-1)\sum (X_i - \mu)^2}{\chi^2_{(n,1-\alpha/2)}}\right)
$$

**Example:**
Assume that the number of days needed to hatch an egg of a certain type of a rare lizard is distributed Normally. Using incubator, $13$ eggs from different nests separately hatched. The
sample mean is $18.97$ weeks and the sample standard deviation
is $\sqrt{10.7}$ weeks. Find a $90\%$ confidence interval for the population
variance. Provide interpretation for the interval.


**Solution:**
Here, it is the case that both $\mu,\sigma^2$ are unknown, so we construct the C.I based on

$$
\left( \frac{(n-1)S_n^2}{\chi^2_{(n-1,\alpha/2)}} , \frac{(n-1)S_n^2}{\chi^2_{(n-1,1-\alpha/2)}}\right) = \left( \frac{12 \cdot 10.7}{\chi^2_{(12,0.05)}}, \frac{12\cdot 10.7}{\chi^2_{(12,0.95)}}\right)=(6.107,24.569).
$$

**Note that in this example sample mean is not population mean $\mu$! It is there to confuse you :)** The interpretation is that, **this interval estimator either includes $\theta$ or not, basically it captures $\theta$ with probability $0$ or $1$. if we were to repeat the experiment and compute similar confidence intervals for $\mu$, we expect that $100(1-\alpha)\%$ of those post-experimental intervals to capture $\mu$, which is the same as above.**


**3. Confidence Interval Approximation for $\mu$ of non-normal large sample:**

We will assume that in a large random sample (\textit{usually $n>25$ is good enough}) we have $X_1,\cdots,X_n \sim f$, $E X = \mu$, and $Var X =\sigma^2$, $E X^4 <\infty$, and we consider the asymptotic approximate C.I for $\mu$, as $n \to \infty$.

$\bullet$ If $\sigma$ is known, then we have

$$
\frac{\sqrt{n}(\overline{X}_n - \mu)}{\sigma} \overset{d}{\to} N(0,1)
$$

so the $100(1-\alpha)\%$ C.I approximate is

$$
\left( \overline{X}_n - z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}} , \overline{X}_n + z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}} \right).
$$

$\bullet$ If $\sigma$ is unknown, then we have

$$
\frac{\sqrt{n}(\overline{X}_n - \mu)}{S_n} \overset{d}{\to} N(0,1)
$$

so the $100(1-\alpha)\%$ C.I approximate is

$$
\left( \bar{X}_n - z_{\alpha/2} \cdot \frac{S_n}{\sqrt{n}} , \bar{X}_n + z_{\alpha/2} \cdot \frac{S_n}{\sqrt{n}} \right).
$$

**Example:**
Shopping times of $64$ randomly selected customers in a
supermarket averaged $33$ minutes with a standard deviation of $16$
minutes. Construct an approximate $90\%$ confidence interval for
the mean shopping time per customer. Provide interpretation for
the interval.


*Note: Standard deviation is $S_n$, not the square!!!*

**Solution:**
Here, if we use large sample theory and the central limit theorem, we will have

$$
\frac{\sqrt{64} (33-\mu)}{16} \overset{d}{\to} N(0,1)
$$

Here $\alpha = 0.1$, so we look at the normal table and see that $z_{\alpha/2} = z_{0.05} \approx 1.64$, hence we have the C.I

$$
\left( 33-1.64\times\frac{16}{8} , 33+1.64\times\frac{15}{8}\right) = (29.72,36.28).
$$

**Since we are interested in $z_{0.05}$. if we can not find the exact value, i.e we know $z_{0.0495} = 1.65$ and $z_{0.505 = 1.64}$, we then may take the average to get a better approximate of $z_{0.05} \approx 1.645$.**

**4. Mean Difference in Two Mutually Independent Normal Random Samples:**

Given two mutually independent random samples $X_1,\cdots,X_m \sim N(\mu_1,\sigma^2)$ and $Y_1,\cdots,Y_n \sim N(\mu_2,\sigma^2)$, we are interested in constructing the confidence interval for $\mu_1-\mu_2$. The PQ is

$$
Q(\vec X,\vec Y,\vec\mu) = \frac{(\overline{X}_m - \overline{Y}_n) - (\mu_1-\mu_2)}{S\sqrt{\frac{1}{m}+\frac{1}{n}}} \sim t(m+n-2)
$$

where 

$$
S^2 = \frac{1}{m+n-2} \left\{ \sum_{i=1}^m (X_i -\overline{X}_m)^2 +\sum_{j=1}^n (Y_i - \overline{Y}_n)^2 \right\}
$$

so the $100(1-\alpha)\%$ C.I is given by

$$
\left( (\overline{X}_m - \overline{Y}_n) - t(m+n-2,\alpha/2) \cdot S\sqrt{\frac{1}{m} +\frac{1}{n}},(\overline{X}_m -\overline{Y}_n) + t(n+m-2,\alpha/2) \cdot S\sqrt{\frac{1}{m}+\frac{1}{n}}\right)
$$

**Example:**
In a packing plant, a machine packs cartons with jars. It is supposed that a new machine will pack faster on the average than
the machine currently used. To test that hypothesis, the times it
takes each machine to pack ten cartons are recorded. The results
in seconds are:

old : $42.7, 43.8, 42.5, 43.1, 44.0, 43.6, 43.3, 43.5, 41.7, 44.1$;

new : $42.1, 41.3, 42.4, 43.2, 41.8, 41.0, 41.8, 42.8, 42.3, 42.7$.

Construct a $95\%$ confidence interval for the difference in the
respective means. Provide interpretation for the interval. (Assume
that the timings for the old and new machines are independent $i.i.d$
samples from $N(\mu_1, \sigma_1^2)$
and $N(\mu_2,\sigma_2^2)$ respectively, and $\sigma_1 = \sigma_2$.

**Solution:**
Here, denote $X_i$ to be the old sample, and $Y_j$ to be the new sample. Then from the data provided we can compute that $\overline{X} = 43.23$ and $\overline{Y} = 42.14$, so $\overline{X} - \overline{Y} = 1.09$, and 
$$
S^2 = \frac{1}{18}\left\{ \sum_{i=1}^{10} (\overline{X}_i - 43.23)^2 + \sum_{j=1}^{10} (\overline{Y}_j -42.14)^2\right\}
$$


**5. Mean Difference in Two Mutually Independent Non-normal Random Samples:**

This set up is roughly the same as the previous one, but here we removed the normal restriction, and we use central limit theorem to get the approximate of C.I for large $n,m$. We know that the PQ is

$$
Q(\vec X,\vec Y,\vec\theta) = \frac{(\overline{X}_m - \overline{Y}_n) - (\mu_1-\mu_2)}{\sqrt{\frac{\sigma_1^2}{m} + \frac{\sigma_2^2}{n}}} \overset{d}{\to} N(0,1).
$$

and the $100(1-\alpha)\%$ C.I is given by

$$
\left( \overline{X}_m - \overline{Y}_n - z_{\alpha/2}\cdot \sqrt{\frac{S_m^2}{m} + \frac{S_n^2}{n}} , \overline{X}_m - \overline{Y}_n +z_{\alpha/2}\cdot\sqrt{\frac{S_m^2}{m} +\frac{S_n^2}{n}}\right)
$$

Note that as $n\to\infty$, $S_m^2 \overset{P}{\to} \sigma_1^2$ and $S_n^2 \overset{P}{\to} \sigma_2^2$, so we can swap to whichever is easier for us to compute.

**Example:**
We wish to compare the daily intake of selenium in two regions. In
each region, $30$ adults were tested and the results (in mg/day)
were:
$\overline{x}_n = 167.1 , s_n = 24.3 , \overline{y}_m = 140.9 , s_m = 17.6$
Find a $95\%$ approximate confidence interval for the difference in
mean daily intake of selenium in the two regions. Provide
interpretation for the interval.

**Solution:**
This is the case where we will find the C.I for the difference of mean in two non-normal random samples. So we apply the above formula, we know that $\overline{X}_m - \overline{Y}_n = 26.2$, also

$\sqrt{\frac{s_m^2}{m}+\frac{s_n^2}{n}} \approx 5.477986$ and here $\alpha = 0.05$, so $z_{\alpha/2} = z_{0.025}$, and hence we have the $95\%$ C.I to be $26.2 \pm z_{0.025} \cdot 5.477986$. From the normal table, $z_{0.025} = 1.96$, so finally we have $(15.46315,36.93685)$.


**6. Population Proportion:**

Now consider we have a random sample $X_1,\cdots,X_n \sim Bernoulli(\theta)$, then we know that by central limit theorem, a PQ is

$$
Q(\vec X,\theta) = \frac{\overline{X}_n - \theta}{\sqrt{\theta(1-\theta)/n}} \overset{d}{\to} N(0,1)
$$

also for large sample, we have $\overline{X}_n \overset{P}{\to} \theta$, denote $\hat\theta_n = \overline{X}_n$, we also have an alternative PQ

$$
Q(\vec X,\theta) = \frac{\hat\theta_n - \theta}{\sqrt{\hat\theta_n(1-\hat\theta_n)}} \overset{d}{\to} N(0,1).
$$

The advantage for this PQ is that we can easily separate $\theta$ and get the $100(1-\alpha)\%$ C.I:

$$
\left( \hat\theta_n - z_{\alpha/2} \cdot \sqrt{\frac{\hat\theta_n(1-\hat\theta_n)}{n}}, \hat\theta_n +z_{\alpha/2} \cdot \sqrt{\frac{\hat\theta_n(1-\hat\theta_n)}{n}}\right)
$$

**Example:**
A sample of $n = 1000$ voters, randomly selected from a city,
showed $560$ in favour of candidate Jones. Find an approximate
$99\%$ confidence interval for the population proportion in favour of
candidate Jones. Provide interpretation for the interval.

**Solution:**
Here we can easily see that in this Bernoulli random sample, we have $\hat\theta_n = \overline{X}_n = 0.56$, hence we construct the C.I by

$$
\left( 0.56 - z_{0.005}\cdot \sqrt{\frac{0.56\cdot0.44}{1000}},0.56+z_{0.005}\cdot\sqrt{\frac{0.56\cdot0.44}{1000}}\right) = 0.56\pm z_{0.005} \cdot 0.0157
$$

From the normal table, we see that $z_{0.005} \approx 2.575$.

**7. Difference in Two Population Proportion:**

Here, we have two mutually independent random samples $X_1,\cdots,X_m \sim Bernoulli(\theta_1)$ and $Y_1,\cdots,Y_n \sim Bernoulli(\theta_2)$. We are interested in the C.I of $\theta_1-\theta_2$. Similarly, denote $\hat\theta_1 = \overline{X}_m, \hat\theta_2 =\overline{Y}_n$, and the improved PQ is

$$
Q(\vec X,\vec Y,\vec\theta) = \frac{(\hat\theta_1-\theta_1)-(\hat\theta_2-\theta_2)}{\sqrt{\hat\theta_1(1-\hat\theta_1)/m +\hat\theta_2(1-\hat\theta_2)/n}} \overset{d}{\to} N(0,1).
$$

and the $100(1-\alpha)\%$ C.I is now

$$
\left((\hat\theta_1 - \hat\theta_2) - z_{\alpha/2} \cdot \sqrt{\frac{\hat\theta_1(1-\hat\theta_1)}{m}+\frac{\hat\theta_2(1-\hat\theta_2)}{n}},(\hat\theta_1 - \hat\theta_2) + z_{\alpha/2} \cdot \sqrt{\frac{\hat\theta_1(1-\hat\theta_1)}{m}+\frac{\hat\theta_2(1-\hat\theta_2)}{n}}\right)
$$

**Example:**
A medical researcher conjectures that smoking can result in wrinkled skin around the eyes. The researcher recruited $150$ smokers and $250$ nonsmokers to take part in an observational
study and found that $95$ of the smokers and $105$ of the
nonsmokers were seen to have prominent wrinkles around the
eyes (based on a standardized wrinkle score administered by a
person who did not know if the subject smoked or not). Find an
approximate $95\%$ confidence interval for the difference in the
proportions of people who have wrinkled skin around their eyes in
the two populations. Provide interpretation for the interval.

**Solution:**
Here, we have two independent random samples, let $X_1,\cdots,X_{150} \sim Bernoulli(\theta_1)$ to be the smokers sample and $Y_1,\cdots,Y_{250} \sim Bernoulli(\theta_2)$ to be the nonsmokers sample, where $\theta_1,\theta_2$ denotes the proportion of populations who have wrinkled skin, thus $\hat\theta_1 = 95/150 = 0.633$ and $\hat\theta_2 = 105/250=0.42$. Also in this case we have $\alpha = 0.05$ hence $\alpha/2 = 0.025$ and from the normal table we have $z_{\alpha/2} = z_{0.025} = 1.96$, also $\hat\theta_1-\hat\theta_2=0.213$, $\displaystyle{\sqrt{\frac{\hat\theta_1(1-\hat\theta_1)}{m}+\frac{\hat\theta_2(1-\hat\theta_2)}{n}} \approx0.0502}$, and thus our $95\%$ C.I is $(0.1146,0.3114)$. As for interpretation? You know that.


**8. Approximate Using MLE Theory:**

Recall that, let a random sample $X_1,\cdots,X_n \sim f(x,\theta)$ where $\theta$ is a one-dimensional parameter, and $\hat\theta_n$ to be the MLE of $\theta$, then we know that

$$
\sqrt{n} (\hat\theta_n - \theta) \overset{d}{\to} N\left( 0, \mathcal{I}^{-1}_1(\hat\theta_n) \right)
$$

\textit{One remark is that since we have convergence in probability $\hat\theta_n \overset{P}{\to} \theta$, so we can replaced by $\hat\theta_n$ in Fisher information, which would be easier to separate $\theta$ in the calculation.}

So we have the $100(1-\alpha)\%$ given by
$$
\left(\hat\theta_n - z_{\alpha/2} \cdot \sqrt{\frac{1}{n} [ \mathcal{I}_1(\hat\theta_n)]^{-1}}, \hat\theta_n + z_{\alpha/2} \cdot\sqrt{\frac{1}{n} [ \mathcal{I}(\hat\theta_n)]^{-1}} \right).
$$

Also we may use the ``empirical Fisher'' to get our estimate of $\mathcal{I}_1(\hat\theta)$:

$$
\mathcal{I}(\theta) = \frac{1}{n} \sum_{i=1}^n \left( \frac{\partial}{\partial \theta} \log f(x_i,\theta) \Bigg|_{ \theta = \hat\theta_{MLE}}  \right)^2 \overset{\text{under regularity conditions}}{=} -\frac{1}{n}\sum_{i=1}^n \left( \frac{\partial^2}{\partial \theta^2} \log f(x_i,\theta) \Bigg|_{\theta = \hat\theta_{MLE}}\right)
$$



Recall the delta-method and the invariance of MLE. If $\hat\theta_n$ is the MLE of $\theta$, and then for any function $g$, $g(\hat\theta_n)$ is the MLE of $g(\theta)$, and the first order delta-method shows us that if $\sqrt{n}(\hat\theta_n - \theta) \overset{d}{\to} N(0,\mathcal{I}_1^{-1}(\hat\theta_n))$, then

$$
\sqrt{n}(g(\hat\theta_n) - g(\theta)) \overset{d}{\to} N(0, [g'(\theta)]^2 \cdot \mathcal{I}_1^{-1}(\hat\theta_n)).
$$

and the $100(1-\alpha)\%$ C.I approximate is
$$
\left(g(\hat\theta_n) - z_{\alpha/2} \cdot \sqrt{\frac{1}{n} \mathcal{I}^{-1}(\hat\theta_n) \cdot|g'(\hat\theta_n)|^2}\hspace{0.2cm}, \hspace{0.2cm}g(\hat\theta_n)+z_{\alpha/2} \cdot \sqrt{\frac{1}{n} \mathcal{I}_1^{-1}(\hat\theta_n) \cdot|g'(\hat\theta_n)|^2}\right)
$$

**Example:**
Suppose a random sample $X_1,\cdots,X_n \sim Poisson(\lambda)$ and $\lambda$ is the unknown parameter. Using the MLE theory, construct
a $100(1-\alpha)\%$ approximate two-sided confidence interval for $\lambda$. Then find the $100(1-\alpha)\%$ C.I for $\lambda^2$, and $e^{-\lambda}$.

**Solution:**
Here, we can easily see that the MLE of a Poisson random sample is just the sample mean, $\hat\theta_n = \overline{X}_n$. Now we find the Fisher information. The log-pdf of one sample is
$$
\log f(X=k,\lambda) = \log e^{-\lambda} \frac{\lambda^k}{k!} = -\lambda + k\log \lambda - \log k!.
$$

The second partial derivative is
$$
\frac{\partial^2 \log f(X=k,\lambda)}{\partial \lambda^2}=-k \frac{1}{\lambda^2}
$$

and hence we have
$$
\mathcal{I}_1(\lambda) = -E\left\{ -X \frac{1}{\lambda^2} \right\} = \frac{1}{\lambda}, \mathcal{I}^{-1}_1(\lambda) = \lambda
$$

So the MLE theory says that
$$
\sqrt{n} \left( \overline{X}_n - \lambda\right) \overset{d}{\to} N\left( 0, \mathcal{I}_1^{-1}(\hat\theta_n)\right)
$$

and given that $\mathcal{I}_1^{-1}(\hat\theta) = \overline{X}_n$, hence the $100(1-\alpha)\%$ C.I is

$$
\left(\overline{X}_n - z_{\alpha/2}\cdot \sqrt{\frac{1}{n} \cdot \overline{X}_n} \hspace{0.2cm} , \hspace{0.2cm}\overline{X}_n +z_{\alpha/2} \cdot \sqrt{\frac{1}{n} \cdot \overline{X}_n}\right).
$$

For $\lambda^2$ and $e^{-\lambda}$, we will then apply delta-method to find the C.I, we define $g(\lambda) = \lambda^2$, and $h(\lambda) = e^{-\lambda}$, hence it is easy to see that  $\hat\lambda^2_{MLE} = \bar{X}^2_n$ 
and $e^{-\lambda}_{MLE} = e^{-\overline{X}_n}$. Then delta-method says that

$$
\sqrt{n}(\overline{X}_n^2 - \lambda^2) \overset{d}{\to} N\left(0,4\lambda^2\cdot\overline{X}_n \right)
$$

which is,
$$
\frac{\sqrt{n}(\overline{X}_n^2 - \lambda^2)}{2\lambda \sqrt{\overline{X}_n}} \overset{d}{\to} N(0,1)
$$

use our large sample theory, we have $\overline{X}_n \overset{P}{\to} \lambda$, so we replace the $\lambda$ in the denominator by $\overline{X}_n$, and we get the C.I as
$$
\left( \overline{X}_n^2 - z_{\alpha/2}\cdot 2\overline{X}_n \sqrt{\frac{\overline{X}_n}{n}} , \overline{X}_n^2 + z_{\alpha/2}\cdot 2\overline{X}_n \sqrt{\frac{\overline{X}_n}{n}} \right).
$$

Similarly, in $e^{-\lambda}$, we have
$$
\frac{\sqrt{n} (e^{-\overline{X}_n} - e^{-\lambda} )}{\lambda e^{-\lambda} \cdot\sqrt{e^{-\overline{X}_n}}} \overset{d}{\to} N(0,1)
$$

and the C.I is
$$
\left(e^{-\bar{X}_n } - z_{\alpha/2} \cdot 2e^{-\overline{X}_n} \cdot e^{-e^{\overline{X}_n}} \cdot \sqrt{\frac{e^{-\overline{X}_n}}{n}} \hspace{0.2cm} , \hspace{0.2cm}e^{-\overline{X}_n} + z_{\alpha/2} \cdot 2e^{-\overline{X}_n} \cdot e^{-e^{\overline{X}_n}} \cdot \sqrt{\frac{e^{-\overline{X}_n}}{n}} \right).
$$





















