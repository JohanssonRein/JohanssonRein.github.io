---
title: "Some Continuous Random Variables"
collection: publications
category: probability
permalink: /publication/continuousdis
excerpt: 'We will investigate some famous continuous random variables'
date: 2024-09-20
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Some Continuous Distributions'
---

# Uniform Distribution

**Definition**
A random variable $X$ is said to have a uniform distribution on the interval $[a,b]$, if its probability density function is given by

$$
f(x) = \begin{cases} \frac{1}{b-a} : a \leq x \leq b \\ \\0 : \text{otherwise}
\end{cases}
$$

And we denote by $X \sim Uniform[a,b]$.



Based on that, we may derive the distribution function $F(x)$ to be

$$
F(x) = 
\begin{cases}
0 : x<a \\
\frac{x-a}{b-a} : a \leq x \leq b \\
1 : x > b
\end{cases}
$$

**Corollary**

Suppose $X \sim U[a,b]$, then for all positive integer $k$,

$$
\mathbb{E} X = \frac{a+b}{2} ; E X^k = \frac{b^{k+1} - a^{k+1}}{(k+1)(b-a)}
$$

and

$$
\mathbf{Var}(X) = \frac{(b-a)^2}{12}.
$$


**Proof**

Left as an exercise to the reader.
**QED**


Furthermore, we can derive the moment generating function of $X \sim Uniform[a,b]$, we have

$$
\begin{align*}
M_X(s) = \mathbb{E}[e^{sX}] &= \int_a^b e^{sx} \frac{1}{b-a} dx\\
&= \frac{e^{sb} - e^{sa}}{s(b-a)}.
\end{align*}
$$

# Exponential Distribution

The exponential distribution is one of the widely used continuous distributions. It is often used to model the time elapsed between events. We will now mathematically define the exponential distribution, and derive its mean and expected value. Then we will develop the intuition for the distribution and discuss several interesting properties that it has.\\

**Definition**

A continuous random variable $X$ is said to have an exponential distribution with parameter $\lambda >0$, shown as $X \sim Exponential(\lambda)$, if its PDF is given by

$$
f_X(x) = \begin{cases} \lambda e^{-\lambda x} & x >0 \\ & \\ 0 & \text{otherwise} \end{cases}
$$





We may also derive the distribution function of $X \sim Exponential(\lambda)$:

$$
\begin{align*}
F_X(x) = \mathbb{P}\{ X \leq x\} &= \int_0^{x} \lambda e^{-\lambda t} dt = 1 - e^{-\lambda x}.
\end{align*}
$$

We can also find its expected value using integration by parts:

$$
\begin{align*}
\mathbb{E} X &= \int_0^{+\infty} x \lambda e^{-\lambda x} dx \\
& = \frac{1}{\lambda} \int_0^{+\infty} ye^{-y}dy &\text{choosing $y = \lambda x$} \\ & = \frac{1}{\lambda} \left[ -e^{-y} - ye^{-y} \right]_{0}^{+\infty} \\
& = \frac{1}{\lambda}.
\end{align*}
$$

Now let's find $\mathbf{Var}(X)$. Since

$$
\begin{align*}
\mathbb{E} X^2 = \int_0^{+\infty} x^2 \lambda e^{-\lambda x} dx = \frac{2}{\lambda^2}.
\end{align*}
$$

Thus we obtain

$$
\mathbf{Var}(X) = \mathbb{E} X^2 - (\mathbb{E} X)^2 = \frac{1}{\lambda^2}.
$$

**Corollary**

If $X \sim Exponential(\lambda)$, then

$$
\mathbb{E} X = \frac{1}{\lambda}, \mathbf{Var}(X) = \frac{1}{\lambda^2}.
$$


**Proof**

This follows trivially from the arguments above.

**QED**


To get some intuition for this interpretation of the exponential distribution, suppose you are waiting for an event to happen. For example, you are at a store and are waiting for the next customer. In each millisecond, the probability that a new customer enters the store is very small. You can imagine that, in each millisecond, a coin (with a very small $\mathbb{P}(H)$
) is tossed, and if it lands heads a new customers enters. If you toss a coin every millisecond, the time until a new customer arrives approximately follows an exponential distribution.

The above interpretation of the exponential is useful in better understanding the properties of the exponential distribution. The most important of these properties is that the exponential distribution is memoryless. To see this, think of an exponential random variable in the sense of tossing a lot of coins until observing the first heads. If we toss the coin several times and do not observe a heads, from now on it is like we start all over again. In other words, the failed coin tosses do not impact the distribution of waiting time from now on. The reason for this is that the coin tosses are independent. We can state this formally as follows:

$$
\mathbb{P}( X > x+a | X > a) = \mathbb{P}(X > x).
$$

To see why this is true, we have

$$
\begin{align*}
P(X > x+a | X > a) &= \frac{\mathbb{P}(X > x+a, X>a)}{\mathbb{P}(X>a)}\\
& = \frac{\mathbb{P}(X>x+a)}{\mathbb{P}(X>a)}\\
&= \frac{1-F_X(x+a)}{1-F_X(a)}\\
&=\frac{e^{-\lambda(x+a)}}{e^{-\lambda a}}\\
&=e^{-\lambda x} \\
&= \mathbb{P}(X \geq x).
\end{align*}
$$


# Normal (Gaussian) Distribution

The normal distribution is by far the most important probability distribution. One of the main reasons for that is the Central Limit Theorem (CLT) that we will discuss later. To give you an idea, the CLT states that if you add a large number of random variables, the distribution of the sum will be approximately normal under certain conditions. The importance of this result comes from the fact that many random variables in real life can be expressed as the sum of a large number of random variables and, by the CLT, we can argue that distribution of the sum should be normal. The CLT is one of the most important results in probability and we will discuss it later on. Here, we will introduce normal random variables.

We first define the standard normal random variable. We will then see that we can obtain other normal random variables by scaling and shifting a standard normal random variable.

**Definition**

A continuous random variable $Z$ is said to be a standard normal (standard Gaussian) random variable, shown as $Z \sim N(0,1)$, if its PDF is given by

$$
f_Z(z) = \frac{1}{\sqrt{2\pi}} \exp\left\{ -\frac{z^2}{2} \right\}, \hspace{1cm} \text{for all $z \in \mathbb{R}$}
$$




And the total area under the curve is $1$. This is because of the fact that 

$$
\int_{-\infty}^{+\infty} e^{-x^2} dx = \sqrt{\pi}.
$$


Now we will study the expected value and the variance of a standard normal variable.

**Corollary**

If $Z \sim N(0,1)$, then $\mathbb{E} Z = 0, \mathbf{Var}(Z) = 1$.


**Proof**

Left as an exercise for the reader.

**QED**


To find the distribution function of the standard normal distribution, we need to integrate the PDF function. In particular we define

$$
F_Z(x) = \mathbb{P}hi(x) = \mathbb{P}(Z \leq x) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^x \exp\left\{ -\frac{u^2}{2} \right\}.
$$

And based on that, here are some properties of the $\mathbb{P}hi$ function:

* $\lim_{x \to +\infty} \mathbb{P}hi(x) = 1, \lim_{x \to -\infty} \mathbb{P}hi(x) = 0$;

* $\mathbb{P}hi(0) = \displaystyle{\frac{1}{2}}$;

* $\mathbb{P}hi(-x) = 1 - \mathbb{P}hi(x), \text{for all $x \in \mathbb{R}$}$.

Indeed, $\mathbb{P}hi(x)$ is a distribution function.


In general, we can obtain any normal random variable variable by shifting and scaling a standard normal random variable. In particular, define

$$
X = \sigma Z + \mu, \hspace{0.5cm}\text{where $\sigma >0$}
$$

Then

$$
\mathbb{E} X = \sigma \mathbb{E} Z +\mu = \mu,
$$

$$
\mathbf{Var}(X) = \sigma^2 \mathbf{Var}(Z) = \sigma^2.
$$

And we say that $X$ is a normal random variable with mean $\mu$ and variance $\sigma^2$. We write $X \sim N(\mu,\sigma^2)$.\\

**Definition**

If $Z$ is a standard normal random variable and $X = \sigma Z +\mu$, then $X$ is a normal random variable with mean $\mu$ and variance $\sigma^2$, i.e

$$
X \sim N(\mu,\sigma^2).
$$


Conversely, if $X \sim N(\mu,\sigma^2)$, then the random variable defined by $\displaystyle{Z = \frac{X-\mu}{\sigma}}$ is a standard random variable, so

$$
\begin{align*}
F_X(x) &= \mathbb{P}(X \leq x) \\
& = \mathbb{P}(\sigma Z + \mu \leq x), \hspace{0.5cm} \text{where $Z \sim N(0,1)$}\\
&= \mathbb{P}\left( Z \leq \frac{x-\mu}{\sigma} \right)\\
&= \mathbb{P}hi \left( \frac{x-\mu}{\sigma} \right).
\end{align*}
$$

And we may differentiate $F_X(x)$ to find the PDF of $X$:

$$
f_X(x) = \frac{d}{dx} F_X(x) = \frac{1}{\sigma \sqrt{2 \pi}} \exp \left\{ - \frac{(x-\mu)^2}{2\sigma^2} \right\}.
$$

**Corollary**

If $X$ is a normal random variable with mean $\mu$ and variance $\sigma^2$, $X \sim N(\mu,\sigma^2)$, then

$$
\mathbb{P}(a \leq X \leq b) = \mathbb{P}hi\left( \frac{b-\mu}{\sigma}\right) - \mathbb{P}hi \left( \frac{a-\mu}{\sigma} \right).
$$




An important property of the normal distribution is that a linear transformation of a normal random variable is itself a normal random variable.\\

**Theorem**

If $X \sim N(\mu_X,\sigma_X^2)$ and $Y = aX+b$ where $a,b \in \mathbb{R}$, then

$$
Y \sim N(a \mu_X + b , a^2 \sigma_X^2).
$$


**Proof**

This follows trivially from the arguments shown above.

**QED**


# Gamma Distribution

The gamma distribution is another widely used distribution. Its importance is largely due to its relation to exponential and normal distributions. Before introducing the gamma random variable, we need to introduce the gamma function.\\

**Definition**

The gamma function, shown by $\Gamma(x)$ is an extension of the factorial function to real and complex numbers. If $n \in \{1,2,3,\cdots\}$, then

$$
\Gamma(n) = (n-1)!
$$

More generally, for any positive real number $\alpha$, define

$$
\Gamma(\alpha) = \int_0^{+\infty} x^{\alpha-1} e^{-x} dx, \hspace{0.5cm} \text{for $\alpha>0$}.
$$



Note that when $\alpha =1$, we have

$$
\Gamma(1) = \int_0^{+\infty} e^{-x} dx = 1.
$$

Using the change of variable $x = \lambda y$, the following equation is also very useful:

$$
\Gamma(\alpha) = \lambda^{\alpha} \int_0^{+\infty} y^{\alpha-1} e^{-\lambda y} dy, \hspace{0.5cm} \text{for $\alpha,\lambda >0.$}
$$

More properties of a gamma function follows:

* $\Gamma(\alpha+1) = \alpha\Gamma(\alpha)$;

* $\displaystyle{\Gamma\left( \frac{1}{2} \right) = \sqrt{\pi} }$.

Now we may define the gamma distribution:

**Definition**

A continuous random variable $X$ is said to have a gamma distribution with parameters $\alpha>0$ and $\lambda>0$, shown as $X \sim Gamma(\alpha,\lambda)$, if its PDF is given by

$$
f_X(x) = \begin{cases} \displaystyle{\frac{\lambda^{\alpha} x^{\alpha-1} e^{-\lambda x} }{\Gamma(\alpha)}} &x>0 \\ 0 &\text{otherwise}
\end{cases}
$$


If $\alpha =1$, we get $Gamma(1,\lambda) = Exponential(\lambda)$, which is a special case. More generally, if we take the sum of $n$ independent $Exponential(\lambda)$ random variables, we will get a $Gamma(n,\lambda)$ random variable. It can be proved by using moment generating functions. 



**Corollary**

If $X \sim Gamma(\alpha,\lambda)$, then

$$
\mathbb{E} X = \frac{\alpha}{\lambda}, \mathbf{Var}(X) = \frac{\alpha}{\lambda^2}.
$$


# Weibull Distribution

The Weibull distribution is widely used in engineering practice due to its versatility. It was originally proposed for the interpretation of fatigue data, but now its use has been extended to many other engineering problems. In particular, it is widely used in the field of life phenomena as the distribution of the lifetime of some object, especially when the “weakest link” model is appropriate for the object. That is, consider an
object consisting of many parts, and suppose that the object experiences death (failure) when any of its parts fail. It has been shown (both theoretically and empirically) that under these conditions a Weibull distribution provides a close approximation to the distribution of the lifetime of the item.

**Definition**

A continuous random variable is said  to have a Weibull distribution if its distribution function is given by

$$
F(x) = \begin{cases} 0 & x \leq \nu \\ & \\ 
\displaystyle{1 - \exp\left\{ - \left( \frac{x - \nu}{\alpha} \right)^{\beta} \right\}} & x > \nu \end{cases}
$$

By differentiating the function above, we get the PDF of a Weibull random variable with parameters $\nu,\alpha,\beta$:

$$
f(x) = \begin{cases} 0 & x \leq \nu \\ & \\
\displaystyle{\frac{\beta}{\alpha} \left( \frac{x - \nu}{\alpha} \right)^{\beta-1} \exp\left\{ - \left( \frac{x - \nu}{\alpha} \right)^{\beta} \right\}} & x > \nu \end{cases}
$$



# Cauchy Distribution

**Definition**

A continuous random variable is said to have a Cauchy Distribution with parameter $\theta \in \mathbb{R}$, if its PDF is given by

$$
f(x) = \frac{1}{\pi} \frac{1}{1+(x-\theta)^2} \hspace{0.3cm} x \in \mathbb{R}
$$




Suppose that a narrow beam flashlight is spun around its center, which is located a unit distance from the $x$-axis. Consider the point $X$ at which the beam interests the $X$ axis when the flashlight has stopped spinning, as shown in figure $3.6$.

The point $X$ is determined by the angle $\theta$ between the flashlight and the $y$-axis, which from the physical situation, appears to be uniformly distributed between $-\pi/2$ and $\pi/2$/ The distribution function of $X$ is thus given by

$$
\begin{align*}
F(x) &= \mathbb{P}\{ X \leq x\} \\
& = \mathbb{P}\{ \tan \theta \leq x\}\\
& = \mathbb{P}\{ \theta \leq \tan^{-1} x\}\\
& = \frac{1}{2} + \frac{1}{\pi} \tan^{-1} x.
\end{align*}
$$

Where we know that

$$
\mathbb{P}\{ \theta \leq a\} = \frac{a - (-\pi/2)}{\pi} = \frac{1}{2} + \frac{a}{\pi} \hspace{0.3cm} -\frac{\pi}{2} < a< \frac{\pi}{2}
$$

Hence the density function of $X$ is given by

$$
f(x) = \frac{d}{dx} F(x) = \frac{1}{\pi(1+x^2)} \hspace{0.3cm} x \in \mathbb{R}
$$

and we see that $X$ has the Cauchy distribution.







