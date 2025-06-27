---
title: "5. Some Discrete Random Variables"
collection: publications
category: probability
permalink: /publication/discretedis
order: 5
excerpt: 'We will investigate some famous discrete random variables'
date: 2024-09-25
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Some Discrete Distributions'
---

# Two-Point Distribution (Bernoulli Distribution)

**Definition**

We say that an random variable $X$ has a two-point distribution if it takes only two values $x_1$ and $x_2$, with probabilities

$$
\mathbb{P}\{X = x_1 \} = p \hspace{0.2cm}, \mathbb{P}\{ X = x_2 \} = 1-p, \hspace{0.2cm} 0<p<1
$$


We may also write

$$
X = x_1 \mathbf{1}_{X = X_1} + x_2 \mathbf{1}_{X = x_2}
$$

The probability mass function is given by

$$
f(x) = \begin{cases} p, x = x_1 \\ 1-p , x = x_2 \\ 0, \text{otherwise} \end{cases}
$$

and the cumulated distribution function is given by (where we assume $x_1<x_2$)

$$
F(x) = \begin{cases} 0, x < x_1 \\ p, x_1 \leq x < x_2 \\ 1, x \geq x_2 \end{cases}
$$

The expected value is given by

$$
\mathbb{E}(X) = px_1 + (1-p)x_2,
$$

and in general,

$$
\mathbb{E}(X^k) = px_1^k +(1-p)x_2^k.
$$

The variance is given by

$$
\mathbf{Var}(X) = p(1-p)(x_1-x_2)^2.
$$

Lastly, the generating function is given by

$$
M(t) = pe^{tx_1} + (1-p)e^{tx_2}, t \in \mathbb{R}.
$$

 Now we have a special case for two-point distribution, if we have $x_1 = 1, x_2 = 0$, we get the Bernoulli random variable:
 
$$
\mathbb{P}\{ X = 1\} = p, \mathbb{P}\{ X = 0\} = 1-p, \hspace{0.3cm} 0<p<1
$$

In Bernoulli random variable, we always assign $p$ to be the probability of success and $1-p$ to be the probability of failure.

**Example:**  In a sequence of $n$ Bernoulli trails with constant probability $p$ of success $(S)$ and $1-p$ of failure $(F)$, let $Y_n$ be the number of times that the ordered combination $SF$ occur, find its expected value and variance.

**Solution:** Let $Y_n$ denote the number of times the combination $SF$ occur, and we define

$$
f(X_i,X_{i+1}) = \begin{cases} 1, \text{if $X_i = S, X_{i+1} = F$} \\ 0, \text{otherwise} \end{cases}
$$

where $i = 1,2,\cdots,n_1$, then we have

$$
Y_n = \sum_{i=1}^{n-1} f(X_i,X_{i+1})
$$

so

$$
\mathbb{E}(Y_n) = (n-1)p(1-p)
$$

and 

$$
\begin{align*}
\E(Y_n^2) &= \E\left[ \sum_{i=1}^{n-1} f^2(X_i,X_{i+1}) \right] + \E\left[ \sum \sum_{i\neq j} f(X_i,X_{i+1}) f(X_j,X_{j+1}) \right]\\
& = (n-1)p(1-p) + (n-2)(n-3)p^2(1-p)^2.
\end{align*}
$$

So $\mathbf{Var}(Y_n) = p(1-p)[n-1+p(1-p)(5-3n)]$.

# Uniform Distribution on $n$ Points

**Definition**

$X$ is said to have a uniform distribution on $n$ points $\{x_1,x_2,\cdots,x_n \}$ if its probability mass function is of the form

$$
\mathbb{P}\{ X = x_i \} = \frac{1}{n}, \hspace{0.3cm} i = 1,2,\cdots,n
$$


So we have

$$
\mathbb{E}(X) = \frac{1}{n} \sum_{i=1}^n x_i, E(X^k) = \frac{1}{n} \sum_{i=1}^n x_i^k
$$

$$
\mathbf{Var}(X) = \frac{1}{n}\sum_{i=1}^n x_i^2 - \left( \frac{1}{n} \sum_{i=1}^n x_i \right)^2 = \frac{1}{n} \sum_{i=1}^n (x_i - \overline{x})^2
$$

where $\overline{x}$ is the average of $x_1,x_2,\cdots,x_n$, given by

$$
\overline{x} = \frac{1}{n} \sum_{i=1}^n x_i
$$

The generating function is also given by

$$
M(t) = \frac{1}{n} \sum_{i=1}^n e^{tx_i}, \hspace{0.2cm} t \in \mathbb{R}
$$

In a special case, if we let $x_i = i$, $i = 1,2,\cdots,n$, we then have
$$
\mathbb{E}(X) = \frac{n+1}{2}, E(X^2) = \frac{(n+1)(2n+1)}{6},\mathbf{Var}(X) = \frac{n^2-1}{12}.
$$

**Example:**  A box contains tickets numbered $1$ to $N$, let $X$ be the largest number drawn in $n$ random drawings with replacement, then we know that those tickets are uniformly distributed, and

$$
\mathbb{P}\{ X \leq k \} = \left( \frac{k}{N} \right)^n
$$

So

$$
\begin{align*}
\mathbb{P}\{ X = k\} &= \mathbb{P}\{ X \leq k \} - \mathbb{P}\{ X \leq k - 1\} \\
& = \left( \frac{k}{n} \right)^n - \left( \frac{k-1}{n} \right)^n.
\end{align*}
$$

Also

$$
\begin{align*}
\mathbb{E}(X) &= N^{-n} \sum_{k=1}^N k^{n+1} - (k-1)^{n+1} - (k-1)^n \\
& = N^{-n} \left[ N^{n+1} - \sum_{k=1}^N (k-1)^n \right].
\end{align*}
$$

# Binomial Distribution

Binomial distribution can be viewed as the sum of $n$ Bernoulli random variables with the same success probability $p$.

**Definition**

We say that $X$ has a binomial distribution with parameter $p$ if its probability mass function is given by

$$
p_k = \mathbb{P}\{ X = k \} = \binom{n}{k} p^k(1-p)^{n-k}
$$

where $k  =0,1,\cdots,n; 0 \leq p \leq 1$.


In Binomial distribution, we have

$$
\mathbb{E}(X) = np, E(X^2) = n(n-1)p^2 + np, \mathbf{Var}(X) = np(1-p)
$$

and most importantly,

$$
\begin{align*}
M(t) &= \sum_{k=0}^n e^{tk} \binom{n}{k} p^k (1-p)^{n-k}\\
&=(1-p +pe^t)^n, \hspace{0.2cm} t \in \mathbb{R}.
\end{align*}
$$

**Example:** Five fair coins are flipped. If the outcomes are assumed independent, find the probability mass function of the number of heads obtained.

**Solution:** If we denote $X$ to be the number of heads, then $X$ is a binomial random variable with parameters $n=5,p=\frac{1}{2}$. Hence we have

$$
\begin{align*}
\mathbb{P}\{ X = 0\} &= \binom{5}{0} \left( \frac{1}{2} \right)^0 \left( 1 - \frac{1}{2} \right)^5 = \frac{1}{32} \\
\mathbb{P}\{ X = 1\} &= \binom{5}{1} \left( \frac{1}{2} \right)^1 \left( 1 - \frac{1}{2} \right)^4 = \frac{5}{32} \\
\mathbb{P}\{ X = 2\} &= \binom{5}{2} \left( \frac{1}{2} \right)^2 \left( 1 - \frac{1}{2} \right)^3 = \frac{10}{32} \\
\mathbb{P}\{ X = 3\} &= \binom{5}{3} \left( \frac{1}{2} \right)^3 \left( 1 - \frac{1}{2} \right)^2 = \frac{10}{32} \\
\mathbb{P}\{ X = 4\} &= \binom{5}{4} \left( \frac{1}{2} \right)^4 \left( 1 - \frac{1}{2} \right)^1 = \frac{5}{32} \\
\mathbb{P}\{ X = 5\} &= \binom{5}{5} \left( \frac{1}{2} \right)^5 \left( 1 - \frac{1}{2} \right)^0 = \frac{1}{32} \\
\end{align*}
$$

**Example:** A communication system consists of $n$ components, each of which will independently function with probability $p$. The total system will be able to operate effectively if at least one-half of its components function. For what values of $p$ is a $5$-component system better than a $3$-component system?

**Solution:**  The number of functioning components $X$ is a binomial random variable with parameters $n,p$, so the probability that a $5$-component system will be effective is given by

$$
\binom{5}{3} p^3(1-p)^2 + \binom{5}{4}p^4(1-p)^1 + p^5
$$

and similarly, for a $3$-component system, the probability is given by

$$
\binom{3}{2} p^2(1-p) + p^3
$$

Hence, the $5$-component system is effective if

$$
\binom{5}{3} p^3(1-p)^2 + \binom{5}{4}p^4(1-p)^1 + p^5 > \binom{3}{2} p^2(1-p) + p^3
$$

Which is,

$$
p > \frac{1}{2}.
$$

*In general, when is a $(2k+1)$-component system better than a $(2k-1)$- component system?*



# Poisson Random Variable

If $n$ independent trials, each of which results in a success with probability $p$, are performed, then, when $n$ is large and $p$ is small enough to make $np$ moderate, the number of successes occurring is approximately a Poisson random variable with parameter $\lambda = np$.

The Poisson random variable has a tremendous range of applications in diverse areas because it may be used as an approximation for a binomial random variable with parameters $(n, p)$ when $n$ is large and $p$ is small enough so that $np$ is of moderate
size. To see this, suppose that $X$ is a binomial random variable with parameters $(n, p)$, and let $\lambda = np$. Then

$$
\begin{align*}
\mathbb{P}\{ X = i \} &= \binom{n}{i} p^i (1-p)^{n-i} \\
& = \frac{n!}{(n-i)!i!}\left( \frac{\lambda}{n} \right)^i \left(1 - \frac{\lambda}{n} \right)^{n-i} \\
& = \frac{n(n-1) \cdots (n-i+1)}{n^i} \frac{\lambda^i}{i!} \frac{(1 - \lambda/n)^n}{(1-\lambda/n)^i}
\end{align*}
$$

Now, for large $n$ and $\lambda$ moderate, we have

$$
\left( 1 - \frac{\lambda}{n} \right)^n \approx e^{-\lambda} \hspace{0.5cm} \frac{n(n-1) \cdots (n-i+1)}{n^i} \approx 1 \hspace{0.5cm} \left( 1 - \frac{\lambda}{n} \right)^i \approx 1
$$

Hence we have

$$
\mathbb{P}\{ X = i\} \approx e^{-\lambda} \frac{\lambda^i}{i!}.
$$



**Definition**
A random variable $X$ that takes one of the values $0,1,2,\cdots$ is said to be a Poisson random variable with parameter $\lambda$, if for some $\lambda >0$, 
$$
\mathbb{P}\{ X = i\} = e^{-\lambda} \frac{\lambda^i}{i!}
$$

We have the following properties of a Poisson variable:

$$
\mathbb{E}(X) = \lambda; \mathbb{E}(X^2) = \lambda(\lambda+1) ; \mathbf{Var}(X) = \lambda
$$


