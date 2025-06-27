---
title: "Moments, Generating Functions and Inequalities"
collection: publications
category: probability
permalink: /publication/moments
excerpt: 'We will investigate moments of a random variable, and generating functions, and some inequalities related to moments.'
date: 2024-09-20
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Moments, Generating Functions and Inequalities'
---


# Moments of a Distribution Function

**Definition**
Let $X$ be a random variable of the discrete type (continuous type) with probability mass function (probability density function) defined as $p_k := \mathbb{P}\{ X = x_k \}, k = 1,2,\cdots$ ,$(f_X)$, then if

$$
\sum \vert x_k \vert p_k < +\infty \hspace{0.2cm} \left( \int_{\mathbb{R}} \vert x \vert f_X(x) dx < +\infty \right),
$$

We then say that the expected value of $X$ exists, and denote

$$
\mu_X = \mathbb{E}(X) = \sum x_k p_k \left( = \int_{\mathbb{R}} x f_X(x) dx \right)
$$




*Remark:* Sometimes $\sum x_k p_k$ converges but not for $\sum \vert x_k \vert p_k$, in this case we say $\mathbb{E}(X)$ doesn't exist. The same idea applies for $\displaystyle{\int_{\mathbb{R}} x f_X(x) dx}$.


**Corollary**

Suppose $X$ is a random variable and $\mathbb{E}(X)$ exists, then if $a,b \in \mathbb{R}$ and $\mathbb{E}(\vert aX+b\vert) <+\infty$, we then have $\mathbb{E}(aX+b) = a\mathbb{E}(X) + b$


**Theorem**

If $X$ is a random variable of the discrete type, $g$ is a Borel measurable function on $\mathbb{R}$, if $Y = g(X)$, then

$$
\mathbb{E}(Y) = \sum_k g(x_k) \mathbb{P}\{ X = x_j \} = \sum_m y_m \mathbb{P}\{ Y = y_m \}
$$

On the other hand, if $X$ is a random variable of the continuous type with probability density function $f$, and $g$ is a Borel measurable function, then denote $Y = g(X)$ and $\mathbb{E}(\vert g(x) \vert) <+\infty$, where

$$
\mathbb{E}(Y) = \int_{\mathbb{R}} g(x) f(x) = \int_{\mathbb{R}} y h(y) dy
$$


**Example:** Suppose $X$ has the uniform distribution on the first $N$ natural numbers, i,e $\mathbb{P}(X = k) = \displaystyle{\frac{1}{N}}$ where $k =1,2,\cdots,N$, then 

$$
\mathbb{E}(X) = \sum_{k=1}^N k \frac{1}{N} = \frac{N+1}{2},
$$

$$
\mathbb{E}(X^2) = \sum_{k=1}^N k^2 \frac{1}{N} = \frac{(N+1)(2N+1)}{6}.
$$

**Example:** Let $X$ be an random variable with probability density function defined by

$$
f_X(x) = \begin{cases} \displaystyle{\frac{2}{x^3}} : x \geq 1 \\ \\ 0 : x < 1  \end{cases}.
$$

Then

$$
\mathbb{E}(X) = \int_{-\infty}^{1} x \cdot 0 dx + \int_{1}^{\infty} x \cdot \frac{2}{x^3} dx = 2,
$$

However

$$
\mathbb{E}(X^2) = \int_1^{\infty} \frac{2}{x} dx \hspace{0.2cm} \text{diverges, thus doesn't exist.}
$$

**Theorem**

Let $X$ be a random variable, if $\mathbb{E}( \vert X \vert^t)$ exists for some $t>0$, then for any $s \in (0,t)$, $\mathbb{E}(\vert X \vert^s)$ exists.


**Proof**

We will prove for continuous random variable. Let $f$ be the PDF of the random variable $X$, then

$$
\begin{align*}
\mathbb{E} \vert X \vert^s &= \int_{\vert x \vert^s \leq 1} \vert x \vert^s f(x) dx + \int_{\vert x \vert^s > 1} \vert x \vert^s f(x)dx\\
& \leq \mathbb{P}\{ \vert X \vert^s \leq 1\} + \mathbb{E}\vert X \vert^t \\
& <+\infty
\end{align*}
$$

A discrete random variable can be proven in a similar way.


**QED**

**Theorem**

Let $X$ be an random variable, if $\mathbb{E}(\vert X \vert^k)$ exists for some $k>0$, then

$$
\lim_{n \to \infty} n^k \mathbb{P}\{ \vert X  \vert > n \} = 0
$$


**Proof**
We will prove for the case when $X$ is of the continuous type. A similar proof can be used for discrete type. Denote $f_X(x)$ to be the probability density function of $X$, then

$$
\int_{-\infty}^{\infty} \vert x \vert^k f_X(x) dx = \lim_{n \to \infty} \int_{-n}^{n} \vert x \vert^k f_X(x) dx < +\infty
$$

Then

$$
\lim_{n \to \infty} \int_{\vert x \vert > n} \vert x \vert^k f_X(x) dx \geq n^k\mathbb{P}\{ \vert X \vert > n \} = 0
$$

**QED**

Probabilities of the type $\mathbb{P}\{ \vert X \vert > n\}$ or either of its components are called tail probabilities.

*Remark:* The converse of theorem 24 is not necessarily true.

**Theorem**

Let $X$ be a non-negative random variable with distribution function $F_X(x)$, then

$$
\mathbb{E}(X) = \int_0^{\infty} [1-F_X(x)]dx
$$



**Proof**

Since $X$ is non-negative, then

$$
\mathbb{E}(X) = \int_0^{+\infty} xf_X(x)dx = \lim_{n \to \infty} \int_0^n xf_X(x)dx
$$

According to integration by parts, we have

$$
\begin{align*}
\int_0^n xf_X(x) &= xF_X(x) \Bigg\vert_0^n - \int_0^n F_X(x)dx\\
&= -n[1-F_X(n)] + \int_0^n [1-F_X(x)]dx
\end{align*}
$$

As $n \to \infty$, $-n[1-F_X(n)] \to 0$ and hence we finished the proof.

**QED**

**Corollary**

For any random variable $X$, $\mathbb{E}(X)<+\infty$ if and only if both $\displaystyle{\int_{-\infty}^0 \mathbb{P}\{ X \leq x \}dx}$ and $\displaystyle{\int_0^{\infty} \mathbb{P} \{ X \leq x \} dx}$ converge.



**Corollary**

Let $X$ be a random variable, $\alpha>0$, then

$$
\mathbb{E}(\vert X \vert^{\alpha}) < +\infty \Longleftrightarrow \sum_{n=1}^{\infty} \mathbb{P} \{ \vert X \vert > n^{\frac{1}{\alpha}} \} < +\infty
$$


**Theorem**

Let $X$ be a random variable satisfying $\lim_{n \to \infty} n^{\alpha} \mathbb{P} \{ \vert x \vert > n \} = 0$ with $\alpha >0$, then for any $0<\beta<\alpha$, we have $\mathbb{E} ( \vert X \vert^{\beta}) < +\infty$.


**Proof**

Given any $\mathbb{E}psilon >0$, we can always choose a large enough $N$ such that $\forall n \geq N$,

$$
\mathbb{P} \{ \vert x \vert > n \} < \frac{\mathbb{E}psilon}{n^{\alpha}},
$$

and 

$$
\mathbb{E}(\vert X \vert^{\beta}) = \beta \int_0^N x^{\beta - 1} \mathbb{P} \{ \vert X \vert > x \} dx + \beta \int_N^{\infty} x^{\beta - 1} \mathbb{P} \{ \vert X \vert > x \} dx \hspace{1cm} (*)
$$

also

$$
\begin{align*}
\mathbb{E} \vert X \vert^{\beta} &= \int_0^{+\infty} \mathbb{P} \{ \vert X \vert^{\beta} > x \} dx \\ &= \int_0^{\infty} \mathbb{P} \{ \vert X \vert > x^{\frac{1}{\beta}} \} dx \\ & = \beta \int_0^{+\infty} u^{\beta-1} \mathbb{P} \{ \vert X \vert > u \} du \hspace{0.2cm} \text{(denote $x^{\frac{1}{\beta}} = u$)}.\hspace{0.2cm} (**)
\end{align*}
$$

Now we have

$$
\begin{align*}
\mathbb{E}\vert X \vert^{\beta} &\leq \beta \int_0^{N} x^{\beta-1} dx + \beta \int_{N}^{\infty} x^{\beta-1} \mathbb{P} \{ \vert X \vert > x \} dx\\
& \leq N^{\beta} + \beta \mathbb{E}psilon \int_N^{\infty} x^{\beta-\alpha-1} dx < +\infty.
\end{align*}

**QED**

**Definition**

Let $k$ be a positive integer and $c$ be a constant, if $\mathbb{E}(X -c)^k$ exists, we then call it the moment of order $k$ about the point $c$. If we take $c = \mathbb{E}(X) = \mu_X$, then we call $E(X - \mu_X)^k$ to be the central moment of order $k$ about the mean. Generally $\mathbb{E}(X^n)$ is the $n$th moment of $X$ and $\mathbb{E}\vert X \vert^{\alpha}$ is the $\alpha$th absolutely moment of $X$.


We will mainly study one special case, that is when $k=2$:


**Definition**

Let $X$ be a random variable, if $\mathbb{E}(X^2)$ exists, we denote $\mathbb{E}(X - \mathbb{E}(X))^2$ to be the variance of $X$, written as $\sigma_X^2 = \mathbf{Var}(X) = \mathbb{E}(x - \mu_X)^2$.


*Remark:*  We know that

$$
\begin{align*}
\mathbf{Var}(X) &= \mathbb{E}[(x - \mu_x)^2]\\
&=\mathbb{E}[X^2 - 2X\mu_X + \mu_X^2]\\
&=\mathbb{E}(x^2) -2\mu_X\mathbb{E}(X) + \mu_X^2\\
&=\mathbb{E}(X^2) - (\mathbb{E}(X))^2
\end{align*}
$$

**Corollary**

Let $X$ be a random variable, $a,b \in \mathbb{R}$. Then 

$$
\mathbf{Var}(aX+b) = a^2\mathbf{Var}(X)
$$



**Definition**

Let $X$ be a random variable and $\mathbb{E} \vert X \vert^2 < +\infty$, then define

$$
Z = \frac{X - \mathbb{E}(X)}{\sqrt{\mathbf{Var}(X)}} = \frac{X - \mu_X}{\sigma_X}
$$

to be the standardized random variable, and $\mathbb{E}(Z) = 0, \mathbf{Var}(Z) = 1$.




# Generating Functions


Here, we will introduce and discuss moment generating functions (MGFs). Moment generating functions are useful for several reasons, one of which is their application to analysis of sums of random variables. Before discussing MGFs, let's define moments.\\

**Definition**

The $n$th moment of a random variable $X$ is dedfined to be $\mathbb{E}[X^n]$. The $n$th central moment of $X$ is defined to be $\mathbb{E}[ (X - \ \mathbb{E} X)^n]$.




**Definition**

The function $P(s) = \sum_{k=0}^{\infty} p_k s^k $ where $ \{ p_k \}$ is the probability mass function of a discrete random variable $X$, is called the probability generating function (PGF). It's clear that $P(s)$ exists for $\vert s \vert < 1$



**Corollary**

For the probability generating function $P(s)$ of the discrete type, we have

$$
\frac{1}{n!} P^{(n)}(s) \Bigg\vert_{s=0} = p_n = \mathbb{P}\{ X = n \}.
$$



Also, in $P(s)$, we notice that

$$
P'(s) \Bigg\vert_{s=1} = \mathbb{E}(X) ; P''(s) \Bigg\vert_{s=1} = \mathbb{E}[X(X-1)],
$$

and

$$
\mathbb{E}(X^2) = \mathbb{E}[X(X-1)] + \mathbb{E}(X).
$$

**Example:** Consider $X \sim Possion(\lambda)$, where 

$$
\mathbb{P}(X = k) = \frac{e^{-\lambda} \lambda^k}{k!}
$$

Then we know that

$$
P(s) = \sum_{k=0}^{\infty} e^{-\lambda} \frac{\lambda^k}{k!} s^k = e^{-\lambda} \sum_{k=0}^{\infty} \frac{(\lambda s)^k}{k!} = e^{-\lambda(1-s)}
$$

Thus

$$
\mathbb{E}(X) = P'(s) \Bigg\vert_{s=1} = \lambda e^{-\lambda(1-s)} \Bigg\vert_{s=1} = \lambda,
$$

and

$$
\mathbb{E}[X(X-1)] = P''(s) \Bigg\vert_{s=1} = \lambda^2 e^{-\lambda(1-s)} \Bigg\vert_{s=1} = \lambda^2
$$

Thus we know that

$$
\mathbb{E}(X^2) = \mathbb{E}(X) + \mathbb{E}[X(1-X)] = \lambda^2 + \lambda,
$$

and

$$
\mathbf{Var}(X) = \mathbb{E}(X^2) - [\mathbb{E}(X)]^2 = \lambda.
$$


**Definition**

Let $X$ be a random variable, the function

$$
M_X(s) = \mathbb{E}[e^{sX}] = \int_{\mathbb{R}} e^{sx} f_X(x) dx
$$

is known as the moment generating function (MGF) of the continuous type of random variable $X$, if $\mathbb{E}[e^{SX}]$ exists in some neighborhood of the origin. For discrete type, we have

$$
M_X(s) = \mathbb{E}[e^{sX}] = \sum e^{sx_i} p_i
$$


**Example:** For each of the following random variables, find the MGF:

(a) $X$ is a discrete random variable with pmf $P_{X}(k) = \begin{cases} \frac{1}{3} : k=1 \\ \frac{2}{3} : k=2\end{cases}$;\\

(b) $Y$ is a $Uniform(0,1)$ random variable.

**Solution:**

(a) We have

$$
M_X(s) = \mathbb{E}[e^{sX}] = \frac{1}{3}e^s + \frac{2}{3}e^{2s}.
$$

(b) We have

$$
M_Y(s) = \mathbb{E}[e^{sY}] = \int_0^1 e^{sy} dy = \frac{e^s-1}{s}.
$$



**Example:** Suppose $X \sim \mathbb{E}xp(\lambda), \lambda > 0$ which is given by

$$
f_X(x) = \begin{cases} \lambda e^{-\lambda x} : x > 0 \\ 0 : \text{otherwise} \end{cases}
$$

In this case

$$
\begin{align*}
\mathbb{E}[e^{sx}] &= \int_{\mathbb{R}} e^{sx} f_X(x) dx \\
& = \int_0^{+\infty} e^{sx} \lambda e^{-\lambda x} dx = \lambda \left[ -\frac{e^{-(\lambda-s)x}}{\lambda - s} \right]_{x=0}^{x=+\infty},
\end{align*}
$$

and

$$
M_X(s) = \begin{cases} \displaystyle{\frac{\lambda}{\lambda - s} : s < \lambda }\\ \\ \text{\scshape{Does Not Exist} } : s \geq \lambda \end{cases}.
$$

We will introduce two theorems, however we will omit the proof:

**Theorem**

The moment generating function uniquely determines a distribution function and conversely, if the moment generating function exists, then it is unique, i.e the map

$$
\Gamma : f_X \longrightarrow m(s) := \int_{\mathbb{R}} e^{sx} f_X(x) dx
$$

is bijective.


**Theorem**

If the moment generating function $M_X(s)$ of a random variable $X$ exists for some $\vert s \vert < s_0$, then the derivatives of all order exist at $s=0$, and

$$
M_X^{(k)}(s)\Bigg\vert_{s=0} = \mathbb{E}(X^k)
$$
for positive integers $k$.



Why is the MGF useful? There are basically two reasons for this. First, the MGF of $X$
 gives us all moments of $X$
. That is why it is called the moment generating function. Second, the MGF (if it exists) uniquely determines the distribution. That is, if two random variables have the same MGF, then they must have the same distribution. Thus, if you find the MGF of a random variable, you have indeed determined its distribution. We will see that this method is very useful when we work on sums of several independent random variables. Let's discuss these in detail.

Recall that

$$
e^x = \sum_{k=0}^{+\infty} \frac{x^k}{k!}
$$

where we have

$$
e^{sX} = \sum_{k=0}^{+\infty} \frac{(sX)^k}{k!} = \sum_{k=0}^{+\infty} \frac{X^k s^k}{k!}
$$

Thus we have

$$
M_X(s) = \mathbb{E}[ e^{sX}] = \sum_{k=0}^{+\infty} \mathbb{E}[X^k] \frac{s^k}{k!}
$$

So, we conclude that the $k$th moment of $X$ is the coefficient of $\frac{s^k}{k!}$ in the Taylor series of $M_X(s)$. If we have the Taylor series of $M_X(s)$, we can then obtain all moments of $X$.

**Example:** If $Y \sim Uniform(0,1)$, find $\mathbb{E}[Y^k]$.

**Solution:** Recall that

$$
M_Y(s) = \frac{e^s -1}{s}
$$

Also

$$
\begin{align*}
M_Y(s) &= \frac{1}{s} \left( \sum_{k=0}^{+\infty} \frac{s^k}{k!} -1 \right) \\
& = \frac{1}{s} \sum_{k=1}^{+\infty} \frac{s^k}{k!} \\
& = \sum_{k=1}^{+\infty} \frac{s^{k-1}}{k!} \\
& = \sum_{k=0}^{+\infty} \frac{1}{k+1}\frac{s^k}{k!}.
\end{align*}
$$

Thus the coefficient of $\frac{s^k}{k!}$ in the Taylor series for $M_Y(s)$ is $\frac{1}{k+1}$, thus

$$
\mathbb{E}[X^k] = \frac{1}{k+1}.
$$

**Corollary**

We can also obtain all moments of $X^k$ from its MGF:

$$
M_X(s) = \sum_{k=0}^{+\infty} \mathbb{E}[X^k] \frac{s^k}{k!},
$$

$$
\mathbb{E}[X^k] = \frac{d^k}{ds^k} M_X(s) \Bigg\vert_{s=0}.
$$



**Example:** Let $X \sim Exponential(\lambda)$, find all of its moments $\mathbb{E}[X^k]$.

**Solution:** Recall that

$$
M_X(s) = \frac{\lambda}{\lambda-s}, s < \lambda
$$

So

$$
\begin{align*}
M_X(s) &= \frac{\lambda}{\lambda-s} \\
&= \frac{1}{1 - \frac{s}{\lambda}}\\
&= \sum_{k=0}^{+\infty} \left( \frac{s}{\lambda} \right)^j, \left|\frac{s}{\lambda} \right|<1 \\
&= \sum_{k=0}^{+\infty} \frac{k!}{\lambda^k} \frac{s^k}{k!}.
\end{align*}
$$

And thus we conclude that 

$$
\mathbb{E}[X^k] = \frac{k!}{\lambda^k}.
$$


**Example:** Suppose $X \sim Geometric(p)$ which is given by

$$
p_k = \mathbb{P}(X = k) = p(1-p)^k,
$$

then

$$
\begin{align*}
M_X(s) &= \mathbb{E}(e^{SX})\\
& = \sum_{n=0}^{\infty} e^{sn} \mathbb{P}(X = n)\\
& = p \sum_{n=0}^{\infty} [(1-p)e^s]^n\\
& = p \frac{1}{1 - (1-p)e^s}, \hspace{0.2cm} \text{if $s < -\ln(1-p)$}.
\end{align*}
$$



# Moments Inequalities

We shall discuss several moments inequalities in this section.

**Theorem**
(Markov's Inequality)

Let $h(x)$ be a non-negative function of a random variable $X$, if $\mathbb{E}(X)$ exists, then for every $\mathbb{E}psilon >0$, we have

$$
\mathbb{P}\{ h(x) \geq \mathbb{E}psilon \} \leq \frac{\mathbb{E}[h(x)]}{\mathbb{E}psilon}
$$



**Proof**

Define $A:=\{ x : h(x) \geq \mathbb{E}psilon\}$ then define $f_X(x)$ to be the probability density function, then we have

$$
\begin{align*}
\mathbb{E}[h(x)] & = \int_{\mathbb{R}} h(x) f_X(x)dx\\
&= \int_A h(x) f_X(x) dx + \int_{A^C} h(x) f_X(x) dx\\
&\geq \int_A \mathbb{E}psilon f_X(x) dx + \int_{A^C} h(x) f_X(x)dx\\
&\geq \mathbb{E}psilon \mathbb{P}\{ h(x) \geq \mathbb{E}psilon \}
\end{align*}
$$

**QED**

**Corollary**

Let $h(x) = \vert x \vert^r, \mathbb{E}psilon = k^r$ where $r>0,k>0$, then

$$
\mathbb{P}\{ \vert X \vert \geq k \} \leq \frac{\mathbb{E}\vert X \vert^r}{k^r}
$$


**Corollary**

Let $h(x) = (x - \mu_X)^2, \mathbb{E}psilon = k^2 \sigma_X^2$ where $\mu_X = \mathbb{E}(X)$ and $\sigma_X^2 = \mathbf{Var}(X)$, then

$$
\mathbb{P} \{ \vert X - \mu_X \vert \geq k \sigma_X \} \leq \frac{1}{k^2}
$$



if we choose $k=3$, then we get

$$
\mathbb{P}\{ \vert X - \mu_X \vert \geq 3 \sigma_X \} \leq \frac{1}{9} \approx 11\%
$$

it will also result in another inequality:

**Theorem**
(Chebyshev's Inequality)

If $X$ is any random variable, then for any $b>0$ we have

$$
\mathbb{P}\{ \vert X - \mathbb{E}(X) \vert \geq b \} \leq \frac{\mathbf{Var}(X)}{b^2}
$$



**Proof**

According to Markov's Inequality, we have

$$
\mathbb{P}\{ (X - \mathbb{E}(X) )^2 \geq b^2 \} \leq 
\frac{\mathbb{E}[ (X - \mathbb{E}(X) )^2]}{b^2}.
$$

**QED**


Here are some extensions of Chebyshev's Inequality, namely Gauss Inequality and Vysochanskij–Petunin Inequality.

**Corollary**
(Gauss Inequality)

Assume $X \sim f$ where $f$ is uni modal (meaning that $f$ obtain a single maximum) with modal $\nu$ where

$$
\nu = \arg\max_x f(x)
$$

and define $\tau^2 = \mathbb{E}(X - \nu)^2$, then we have

$$
\mathbb{P}_r \{ \vert X - \nu \vert  \geq \mathbb{E}psilon \} \leq \begin{cases} 
\displaystyle{\frac{4\tau^2}{9\mathbb{E}psilon^2} : \mathbb{E}psilon \geq \frac{2}{\sqrt{3}} \tau} \\ \\ \displaystyle{1 - \frac{\mathbb{E}psilon}{\tau \sqrt{3}} : \mathbb{E}psilon < \frac{2}{\sqrt{3}} \tau} \end{cases}
$$


**Corollary**
(Vysochanskij–Petunin Inequality)

Let $X \sim f$ where $f$ is uni modal and define $\xi^2 = \mathbb{E}[(x - \alpha)^2]$ for any $\alpha \in \mathbb{R}$, then $\forall \mathbb{E}psilon >0$, we have

$$
\mathbb{P}_r \{ \vert X -\alpha \vert \geq \mathbb{E}psilon \} \leq \begin{cases}
\displaystyle{\frac{4\xi^2}{9\mathbb{E}psilon^2} : \mathbb{E}psilon \geq \sqrt{\frac{8}{3}} \xi} \\ \\
\displaystyle{\frac{4\xi^2}{3\mathbb{E}psilon^2} - \frac{1}{3} : \mathbb{E}psilon < \sqrt{\frac{8}{3}} \xi}\end{cases}
$$


The proof for corollary 13 and 14 will not be proved, since those require some work.

**Theorem**
(Chernoff Bounds)


Let $X$ be a random variable, then $\forall a \in \mathbb{R}$, 

$$
\mathbb{P}\{ X \geq a \} \leq e^{-sa}M_X(s) : s >0
$$

and

$$
\mathbb{P}\{ X \geq a \} \geq e^{-sa}M_X(s) : s<0
$$

Where $M_X(s)$ denotes the moment generating function of the random variable $X$.


**Proof**

For $t>0$, we have

$$
\mathbb{P}\{ X \geq a\} = \mathbb{P}\{ e^{tX} \geq e^{ta} \} \leq \mathbb{E}(e^{tX}) e^{-ta}, \text{by Markov's Inequality}.
$$

A similar proof can be done when $t<0$.

**QED**

**Corollary**

Let $Z$ to be the standard normal random variable, then for $a>0$, we have

$$
\mathbb{P}\{ Z \geq a \} \leq e^{-a^2/2}
$$

and similarly, for $a<0$, we have

$$
\mathbb{P}\{ Z \leq a \} \leq e^{-a^2/2}
$$

**Corollary**

Let $X$ be a random variable with $\mathbb{E}(X) = 0$ and $\mathbf{Var}(X) = \sigma_X^2$, then

$$
\mathbb{P}(X \geq x) \leq \frac{\sigma_X^2}{\sigma_X^2 + x^2} : x >0
$$

and

$$
\mathbb{P}(X \geq x) \geq \frac{\sigma_X^2}{\sigma_X^2 + x^2} : x < 0
$$



**Proof**

Proof is left as an exercise : ) 

**QED**


**Theorem**
(Minkouski Inequality)

Let $X,Y$ be random variables, $r>0$. If $\mathbb{E} X^r, \mathbb{E} Y^r$ exist, then so is $\mathbb{E}\vert X + Y \vert^r$ and

$$
\mathbb{E}\vert X + Y \vert^r \leq C_r [ \mathbb{E}\vert X \vert^r + \mathbb{E}\vert Y \vert^r]
$$

where $C_r = \begin{cases} 1 : 0 \leq r \leq 1 \\ 2^{r-1} : r > 1 \end{cases}$.

