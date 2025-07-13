---
title: "Hypothesis Testing"
collection: publications
category: statistics
permalink: /publication/hypothesistesting
order: 8
excerpt: 'We will investigate basic theories of hypothesis testing'
date: 2025-04-01
venue: 'Winter'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2025) Hypothesis Testing'
---


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> A statistical hypothesis test is a decision rule that uses the data to infer which two mutually exclusive hypothesis, that reflect two completing hypothetical states of the nature is correct. The decision rule partitions the sample space $\mathcal{X}$ into $2$ disjoint regions 
  that respectively reflect support for the null hypothesis $\mathcal{H}_0$ and the alternative hypothesis $\mathcal{H}_1$, where $\mathcal{X} = \mathcal{H}_0 \bigcup \mathcal{H}_1$ and $\mathcal{H}_0 \bigcap \mathcal{H}_1 = \varnothing$. Our goal would be to use the data to decide whether the parameter of interest 
  $\theta$ is whether $\theta \in \mathcal{H}_0$ or $\theta \in \mathcal{H}_1$. Unlike point estimation and confidence interval, we do not perform any estimate on $\theta$.
</div>


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> uppose a test $\mathcal{H}_0$ and $\mathcal{H}_1$ partitioning the sample space $\mathcal{X}$ into two disjoint regions $\mathcal{R}$ and $\mathcal{R}^C$, and we will reject $\mathcal{H}_0$ if $\vec x \in \mathcal{R}$, 
  such $\mathcal{R}$ is called the critical region. We may formulate the test as a function:
  
$$
\phi(\vec x) = \begin{cases} 1 & \text{if $\vec x \in \mathcal{R},$ and we reject $\mathcal{H}_0$} \\ 0 & \text{if $\vec x \in \mathcal{R}^C,$ and we do not reject $\mathcal{H}_0$} \end{cases}
$$
</div>



There are two types of errors: Type one error is when $\mathcal{H}_0$ is rejected when $\mathcal{H}_0$ is indeed true; Type two error is $\mathcal{H}_0$ is not rejected when $\mathcal{H}_1$ is indeed true.


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem (Neyman-Pearson Lemma).</strong>

Let $\phi(\vec X) = \begin{cases} 1 &  \text{if $p(\vec x,\theta_1) > k p(x,\theta_0)$} \\ \\ 0 & \text{if $p(\vec x,\theta_1) < kp(\vec x,\theta_0)$} \end{cases}$, and $k$ is such that $P(\text{rejecting $\mathcal{H}_0$}) = \alpha$, (we reject $\mathcal{H}_0$ if $\phi(\vec X) = 1$)then $\phi$ is the 
UMP test in the class of all tests $\phi^*$ with the same level $\alpha$, $\alpha$ is called the significance level. Hence the UMP test has a rejection region

$$
\mathcal{R} := \left\{ \vec x \in \mathcal{X},\frac{p(\vec x, \mathcal{H}_1)}{p(\vec x, \mathcal{H}_0)} > k\right\}, \text{ $k$ is chosen such that} \hspace{0.2cm} P( \vec x \in \mathcal{R}) \leq \alpha.
$$
</div>

**Example:** Suppose we have a random sample $X_1,\cdots,X_n \sim N(\mu,1)$, and $\mu = \{ 0,1\}$. So we would like to test that $\mathcal{H}_0 : \mu = 0$ and $\mathcal{H}_1: \mu=1$.


To use NP lemma, we first construct the ratio:

$$
\begin{align*}
\frac{p(\vec x, \mu=1)}{p(\vec x,\mu=0)} = \frac{\left(\frac{1}{\sqrt{2\pi}}\right)^n \exp \left\{ -\frac{1}{2} \sum(x_i-1)^2\right\}}{\left(\frac{1}{\sqrt{2\pi}}\right)^n \exp \left\{ -\frac{1}{2} \sum(x_i)^2\right\}} = e^{-\frac{1}{2}\sum(x_i-1)^2+\frac{1}{2}\sum x_i^2} = e^{n\overline{X}_n - n/2}
\end{align*}
$$

Then the NP lemma says that we will reject $\mathcal{H}_0$ if $\displaystyle{\frac{p(\vec x,\mu=1)}{p(\vec x,\mu=0)}} > k$ for some $k$, so we solve for $e^{n\overline{X}_n - n/2}>k$, and we get $\overline{x}_n >k^* = \frac{\ln k}{n} +\frac{1}{2}$, and this is the rejection region. Now given 
significance level $\alpha$, the type one error is given by

$$
P(\text{Reject $\mathcal{H}_0$ when it is true}) = P(\overline{x}_n >k  \big\vert \mu=0) = \alpha.
$$

Then we use the fact that $\displaystyle{\overline{X}_n \sim N\left(0,\frac{1}{n} \right)}$ (the case when $\mathcal{H}_0$ is true), and we have

$$
P\left(\frac{\sqrt{n} (\overline{X}_n - 0)}{1} > \sqrt{n} k^* \right) = \alpha
$$

and then we can refer to the normal table to solve for $k^*$. The same idea applies for type two error, where in this case we have

$$
P(\text{Not rejecting $\mathcal{H}_0$ when it is false)} = P(\overline{x}_n < k^* \big\vert \mu=1).
$$


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem (Likelihood Ratio Test).</strong> 

Consider the random sample $X_1,\cdots,X_n \sim f(x,\theta)$, and we have $\mathcal{H}_0$ and $\mathcal{H}_1$ as two tests, and we define the likelihood ratio (LR) statistic to be

$$
\lambda_n(\vec X) = \frac{L_n(\hat\theta_{MLE,\mathcal{H}_0})}{L_n(\hat\theta_{MLE,\Theta})}
$$

A test based on LR statistic has the following form

$$
\phi(\vec X) = \begin{cases} 1 &  \lambda_n(\vec X) < C \text{ (reject $\mathcal{H}_0$)}\\ 0 & \lambda_n(\vec X) > C \end{cases}
$$

for $C\in [0,1]$ and the rejection region takes the form $\mathcal{R}:= \{ \vec x \in \mathcal{X}: \lambda_n(\vec X) < C\}$.
</div>


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> 

At significance level $\alpha$, the rejection region ($\lambda_n(\vec X) < C$) of the LR-based test under regularity conditions for large $n$ is approximately

$$
\mathcal{R} := \Big\{ \vec x \in \mathcal{X} : -2\log[\lambda_n(\vec X)] \geq \chi_{d,\alpha}^2 \Big\}, d=\dim\Theta - \dim\Theta_0
$$

where

$$
-2\log[\lambda_n(\vec X)] = 2\Big\{ \sup_{\theta \in \Theta} l_n(\theta) - \sup_{\theta \in \Theta_0} l_n(\theta) \Big\}
$$
</div>


Also, we have a general formula to solve for hypothesis testing. We list some cases here:

* Testing the Mean in a (Asymptotically) Normal Sample with Known Variance

Suppose we know the random sample takes the form $N(\mu,\sigma^2)$ where $\sigma^2$ is known, and we wish to test:

$$
\mathcal{H}_0 : \mu = \mu_0 , \mathcal{H}_1: \mu \neq \mu_0 (\mu >\mu_0) (\mu <\mu_0)
$$

and we first compute the value under the null hypothesis:

$$
z=\frac{\sqrt{n}(\overline{x}_n - \mu_0)}{\sigma} \hspace{0.2cm} \text{In a large sample we may replace $(\sigma$ by $s_n$)}
$$

and we will reject $\mathcal{H}_0$ at significance level $\alpha$ if:

$$
\vert z\vert > z_{\alpha/2} (z>z_{\alpha})(z<-z_{\alpha}).
$$

* Testing the Mean in a Normal Sample with Unknown Variance

Suppose we know the random sample takes the form $N(\mu,\sigma^2)$ where $\sigma^2$ is unknown, and we wish to test:

$$
\mathcal{H}_0 : \mu = \mu_0 , \mathcal{H}_1: \mu \neq \mu_0 (\mu >\mu_0) (\mu <\mu_0)
$$

and we first compute the value under the null hypothesis:

$$
t=\frac{\sqrt{n}(\overline{x}_n - \mu_0)}{s_n} \hspace{0.2cm} 
$$

and we will reject $\mathcal{H}_0$ at significance level $\alpha$ if:

$$
\vert t\vert > t_{\alpha/2,n-1} (t>t_{\alpha,n-1})(t<-t_{\alpha,n-1}).
$$


* Testing the Variance in a Normal Sample with Unknown Mean and Variance

Suppose we know the random sample takes the form $N(\mu,\sigma^2)$ where $\mu,\sigma^2$ is unknown, and we wish to test:

$$
\mathcal{H}_0 : \sigma^2 = \sigma_0^2 , \mathcal{H}_1: \sigma^2 \neq \sigma_0^2 (\sigma^2 >\sigma_0^2) (\sigma^2 <\sigma^2_0)
$$

and we first compute the value under the null hypothesis:

$$
\chi=\frac{(n-1)s^2}{\sigma_0^2} \hspace{0.2cm} 
$$

and we will reject $\mathcal{H}_0$ at significance level $\alpha$ if:

$$
\chi^2 > \chi^2_{\alpha/2,n-1} \text{or} <\chi^2_{1-\alpha/2,n-1} (\chi^2 > \chi^2_{\alpha,n-1})(\chi^2<\chi^2_{1-\alpha,n-1})
$$

* Testing the Ratio in a Bernoulli Sample

Suppose we know the random sample takes the form $Bernoulli(\theta)$ where $\theta$ is unknown, and we wish to test:

$$
\mathcal{H}_0 : \theta=\theta_0 , \mathcal{H}_1:\theta \neq \theta_0 (\theta>\theta_0)(\theta<\theta_0)
$$

and we first compute the value under the null hypothesis:

$$
z = \frac{\hat\theta -\theta_0}{\displaystyle{\sqrt{\frac{\theta_0(1-\theta_0)}{n}}}}
$$

and we will reject $\mathcal{H}_0$ at significance level $\alpha$ if:

$$
\vert z\vert > z_{\alpha/2} (z>z_{\alpha})(z<-z_{\alpha}).
$$

* Testing the Difference in Mean of Two Bernoulli Samples

Suppose we have two mutually independent large random samples $(\geq25)$ $X_1,\cdots,X_m \sim Bernoulli(\theta_1)$ and $Y_1,\cdots,Y_n \sim Bernoulli(\theta_2)$, and we wish to test

$$
\mathcal{H}_0: \theta_1-\theta_2=D_0 ; \mathcal{H}_1: \theta_1-\theta_2 \neq D_0(\theta_1-\theta_2 > D_0)(\theta_1-\theta_2<D_0)
$$

and we first compute the value under the null hypothesis:

If $D_0 = 0$, then

$$
z = \frac{\hat\theta_1-\hat\theta_2}{\displaystyle{\sqrt{\frac{\hat\theta(1-\hat\theta)}{m}+\frac{\hat\theta(1-\hat\theta)}{n}}}}, \hat\theta=\frac{x+y}{m+n}, \text{where $x/m = \hat\theta_1, y/n = \hat\theta_2$}
$$

If $D_0 \neq 0$, then

$$
z = \frac{\hat\theta_1-\hat\theta_2-D_0}{\displaystyle{\sqrt{\frac{\hat\theta_1(1-\hat\theta_1)}{m}+\frac{\hat\theta_2(1-\hat\theta_2)}{n}}}}
$$

and we will reject $\mathcal{H}_0$ at significance level $\alpha$ if

$$
\vert z\vert > z_{\alpha/2} (z>z_{\alpha})(z<z_{\alpha}).
$$

* Testing the Difference in Mean of Two Normal Samples with Known Variance

Suppose we have two mutually independent large samples $(>25)$ $X_1,\cdots,X_m \sim N(\mu_1,\sigma_1^2)$ and $Y_1,\cdots,Y_n \sim N(\mu,\sigma_2^2)$ where $\sigma_1,\sigma_2$ are known. We wish to test

$$
\mathcal{H}_0: \mu_1-\mu_2 = D_0 ; \mathcal{H}_1 : \mu_1-\mu_2 \neq D_0 (\mu_1-\mu_2 > D_0)(\mu_1-\mu_2 < D_0)
$$

We first compute the value under the null hypothesis:

$$
z = \frac{\overline{x}_m - \overline{y}_n - D_0}{\displaystyle{\sqrt{\frac{\sigma_1^2}{m}+\frac{\sigma_2^2}{n}}}}
$$

and we will reject $\mathcal{H}_0$ at significance level $\alpha$ if

$$
\vert z\vert > z_{\alpha/2} (z>z_{\alpha})(z<-z_{\alpha})
$$

* Testing the Difference in Mean of Two Normal Samples with Unknown Variance

Suppose we have two mutually independent large samples $(>25)$ $X_1,\cdots,X_m \sim N(\mu_1,\sigma_1^2)$ and $Y_1,\cdots,Y_n \sim N(\mu,\sigma_2^2)$ where $\sigma_1,\sigma_2$ are unknown, but we have $\sigma_1^2 = \sigma_2^2$. We wish to test

$$
\mathcal{H}_0: \mu_1-\mu_2 = D_0 ; \mathcal{H}_1 : \mu_1-\mu_2 \neq D_0 (\mu_1-\mu_2 > D_0)(\mu_1-\mu_2 < D_0)
$$

We first compute the value under the null hypothesis:

$$
t = \frac{\overline{x}_m - \overline{y}_n - D_0}{s_p\displaystyle{\sqrt{\frac{1}{m}+\frac{1}{n}}}}, s_p^2 = \frac{(m-1)s_m^2+(n-1)s_n^2}{m+n-2}
$$

and we will reject $\mathcal{H}_0$ at significance level $\alpha$ if

$$
\vert t\vert > t_{\alpha/2,m+n-2} (t>t_{\alpha,m+n-2})(t<-t_{\alpha,m+n-2})
$$




Now I have listed a bunch of exercises, do it carefully, and identify which of the above $7$ cases! The values of $z,t,\chi$ can all be found in the standard table.


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Atlantic bluefin tuna is the largest and most endangered of the
tuna species; the concern is that this species has been overfished
and that the mean weight has decreased. Suppose a random
sample of 12 Atlantic blue fin tuna was obtained from commercial
fishing boats and weighted. The sample is normally distributed
with $x_n = 535.7$ and $s_n = 37.8$. Is there any evidence that the
mean weight is less than $550$ pounds? Use the significance level
$\alpha = 0.05$.
</div>


A general approach is that, we always make null hypothesis to be simple, i.e it is equal to something. So $\mathcal{H}_0 : \mu=550$. Also we want to see if its the weight has been reduced, so we make the alternative hypothesis to be 
$\mathcal{H}_1 : \mu<550$. Then according to the table, here both $\mu,\sigma$ unknown, we compute the value under the null hypothesis $\mathcal{H}_0$ first: 

$$
t = \frac{\overline{x} - \mu_0}{s/\sqrt{12}} = \frac{535.7-550}{37.8/\sqrt{12}} = -1.310493468
$$

now, in order to reject $\mathcal{H}0$ under level $\alpha$, we need $t < -t_{\alpha, n-1}$, which according to the $t$-table we have $t_{0.05,11} = 1.796$, where we have $-1.31049 > -1.796$, 
hence we do not reject $\mathcal{H}_0$, so at significance level $\alpha=0.05$, we do not see any evidence that the mean weight is less than $550$ pounds.


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Despite a sophisticated recycling system, a water park informs the
city water department of their need for 1 million liter of water per
day. The city water department selected a random sample of
$n = 21$ days; the mean and sample standard deviation of the
park?s water usage (in thousands of liter) were $x_n = 927.43$,
$s_n = 154.45$. Assuming the usage is normally distributed, is there
evidence to suggest the mean water usage is different from $1$
million liter per day? Use the significance level $\alpha = 0.05$.
</div>



Here, we have a similar case as the previous exercise: We're in a normal random sample with both $\mu$, $\sigma^2$ unknown. So let $\mathcal{H}_0 : \mu = 1000$ and $\mathcal{H}_1 := \mu \neq 1000$. So again we compute the value under $\mathcal{H}_0$, we have

$$
t = \frac{\overline{x} - \mu_0}{s/\sqrt{21}} = \frac{927.43-1000}{154.45/\sqrt{21}} = -2.153
$$

now in order to reject $\mathcal{H}0$ under level $\alpha$,
we need $\vert t\vert > t_{\alpha/2.n-1} $ and from the $t$-table we have $t_{\alpha/2 , n-1} = t_{0.025,20} = 2.086$, and since we do have $\vert t\vert = 2.153 > 2.086$, we will hence reject $\mathcal{H}_0$ and in favor of $\mathcal{H}_1$, that is, 
there is evidence that the mean water usage is different from $1$ million liter per day.

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> A study conducted by the Florida Game and Fish Commission
aims at assessing the amounts of the DDT insecticide in the brain
tissue of brown pelicans. Approximately Normal and independent
samples of $n = 10$ juveniles and $m = 13$ nestlings gave (in parts
per million), and
$$
\overline{x}_n = 0.041 , s_n = 0.017 , \overline{y}_m = 0.026 , s_
m = 0.006.
$$
Test whether the mean amounts of DDT in juveniles and nestlings
are the same. Use the significance level $\sigma= 0.05$.
</div>




In this example, we have two mutually independent random samples, and we design $\mathcal{H}_0 : \mu_1 -\mu_2 = 0$ while $\mathcal{H}_1 : \mu_1-\mu_2 \neq 0$, and in this two samples we have $\sigma_1^2=\sigma_2^2$ unknown, so we first compute the value under the null hypothesis, which is

$$
t = \frac{\overline{x}_n - \overline{y}_m - 0}{s_p \cdot \sqrt{\frac{1}{n}+\frac{1}{m}}} , s_p^2 = \frac{(n-1)s_n^2+(m-1)s_m^2}{n+m-2}
$$

where we compute $\displaystyle{s_p = \sqrt{\frac{9\times0.017^2 + 12\times 0.006^2}{10+13-2}} = 0.012}$, and we have

$$
t = \frac{0.041-0.026}{0.012\times\sqrt{\frac{1}{10}+\frac{1}{13}}} = 2.97178
$$

while we will reject $\mathcal{H}0$ if
$\vert t\vert >t_{\alpha/2, n+m-2} = t_{0.025,21 } = 2.08$, which we see that clearly we should reject $\mathcal{H}_0$, meaning that the amount of DDT in juveniles and nestlings are not the same.


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> A company produces machine engine parts that are supposed to
have a diameter variance no larger than $0.0002$.
A random sample of $n = 10$ parts gave a sample variance of
$0.0003$. We wish to test
$\mathcal{H}_0 : \sigma^2 = 0.0002$, 
$\mathcal{H}_1 : \sigma^2 > 0.0002$.
at the significance level $\alpha = 0.05$. Assume that the random
sample is iid from $N(\mu, \sigma^2)$ with both parameters unknown.
</div>


In this example, we will first compute the value under the null hypothesis $\mathcal{H}_0$:

$$
\chi^2 = \frac{(n-1)s^2}{\sigma_0^2} = \frac{9\times0.0003}{0.0002} = 13.5
$$

In this case we will reject $\mathcal{H}0$ if we have $\chi^2 > \chi^2_{\alpha,n-1} = \chi^2_{0.05,9} = 16.918$, where we see that we do not satisfy this condition, and hence we will not reject $\mathcal{H}_0$, and we conclude that at significance level 
$\alpha=0.05$, we do not have much information that $\sigma^2>0.0002$.


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> An experimenter was convinced that the variability in his/her
measuring equipment results in a standard deviation of $2$; $n = 16$
measurements yielded $s^2
 = 6.1$. Do the data disagree with his/her claim? Use the significance level $\alpha = 0.05$. Assume the
measurements are normally distributed with both mean and
variance unknown.
</div>


In this example, we will test $\mathcal{H}_0 : \sigma^2 = 4$ and $\mathcal{H}_1:\sigma^2\neq 4$. Note that standard deviation is $\sigma$!!!. In this normal sample with both mean and variance unknown, we first compute the value under the null hypothesis $\mathcal{H}_0$:

$$
\chi^2 = \frac{(n-1)s^2}{\sigma_0^2} = \frac{15\times6.1}{4} = 22.875
$$

Under this condition we will reject $\mathcal{H}0$ if $\chi^2 > \chi^2_{\alpha/2,n-1}$ or $\chi^2 <\chi^2_{1-\alpha/2,n-1}$. Here we have $\alpha=0.05, n-1=15$, and $\chi_{0.025,15}^2 = 27.48839$ and $\chi_{0.975,15}^2=6.26214$, and we see that 
$\chi^2$ do not satisfy any of these two conditions, so we will not reject $\mathcal{H}_0$, at significance level $0.05$.

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> A study published in $2004$ in Current Allergy and Clinical
Immunology concerns the allergy to the powder on latex gloves.
Among other things, the exposure to the powder of $n = 46$
hospital employees with diagnosed latex allergy was investigated.
The number of latex gloves used per week by these sampled
workers is summarized as
$\overline{x}_n = 19.3$ , $s_n = 11.9$.
Is there evidence to conclude that the mean number of latex
gloves used per week by hospital employees with latex allergy is
more than $15$? Use $\alpha = 0.01$.
</div>


Here since we have a large sample so we could use a normal approximation for this sample. We will test $\mathcal{H}_0 : \mu = 15$ and $\mathcal{H}_1 : \mu>15$. We first compute the value under the null hypothesis:

$$
t = \frac{\overline{x} - \mu_0}{s/\sqrt{n}} = \frac{19.3-15}{11.9/\sqrt{46}} = 2.4507
$$

We will reject $\mathcal{H}0$ if $t > t_{\alpha,n-1} = t_{0.01,45} = 2.326$, where we will reject $\mathcal{H}_0$ under this case, at a significance level $\alpha=0.01$.


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> A psychological study was conducted to compare the reaction
times of men and women to a stimulus. Independent random
samples of 50 men and 50 women were employed in the
experiment. The results (in seconds) are summarized as
$\overline{x}_m = 3.6 , s^2_m
 = 0.18$ , $\overline{x}_n = 3.8 , s^2_n
 = 0.14$
Is there evidence to suggest a difference between true mean
reaction times for men and women? Use  $\alpha= 0.05$.
</div>



This one is similiar to the one in exercise $26$.



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> A machine in a factory produces $10\% $ of defectives among a large
lot of items that it produces in a day. A random sample of $100$
items from the day?s production contains $15$ defectives, and the
supervisor says that the machine must be repaired. Is there
evidence that the machine produces more than $10\%$ of defectives
on average? Use $\alpha = 0.05$.
</div>



Here, we have a Bernoulli random sample, and we test $\mathcal{H}_0 : p = 0.1$ and $\mathcal{H}_1:p>0.1$. We first compute the value under the null hypothesis:

$$
z = \frac{\hat{p} - p_0}{\sqrt{\frac{p_0(1-p_0)}{n}}} = \frac{0.15-0.1}{\sqrt{0.1\times 0.9 / 100}} = 1.66667
$$

and we will reject $\mathcal{H}_0$ if $z > z_{\alpha} = z_{0.005} = 1.645$, which means we will reject $\mathcal{H}_0$ under significance level $\alpha=0.05$.



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Lipitor is a drug that is used to control cholesterol. In a randomized
clinical trial, $94$ subjects were treated with Lipitor and $270$
independently selected subjects were given a placebo. Among $94$
treated with Lipitor, $7$ developed infections, while among $270$ given
a placebo, $27$ developed infections. Is there a difference between
the infection rates for the two drugs? Use $\alpha = 0.05$.
</div>




Here, we have two Bernoulli random samples, let $X_i$ be the sample treated with Lipitor and $Y_j$ be the sample treated with placebo. We have $X_1,\cdots,X_{94} \sim Bernoulli(\theta_1)$, $\theta_1 = 0.074468$ and $Y_1,\cdots,Y_{270} \sim Bernoulli(\theta_2), \theta_2 = 0.1$, we test 
$\mathcal{H}_0:\mu_1-\mu_2=0$, and $\mathcal{H}_1: \mu_1-\mu_2\neq 0$. We first compute the value under the null hypothesis:

$$
z = \frac{\hat\theta_1 - \hat\theta_2 }{\sqrt{\displaystyle{\frac{\hat{p}(1-\hat{p})}{n_1} +
\frac{\hat{p}(1-\hat{p})}{n_2}}}}, \hat{p} = \frac{x_1+x_2}{n_1+n_2} = \frac{7+27}{94+270}=0.09341
$$

and we get

$$
z = \frac{0.074468-0.1}{\displaystyle{\sqrt{0.09341(1-0.09341)/94+0.09341(1-0.09341)/270}}} = -0.73262
$$

We will reject $\mathcal{H}0$ if $\vert z\vert > z_{\alpha/2} = z_{0.025} = 1.96$, and hence we do not reject $\mathcal{H}_0$, under the significance level $\alpha=0.05$.








