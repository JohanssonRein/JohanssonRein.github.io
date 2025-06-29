---
title: "Convergence Theorems"
collection: publications
category: probability
permalink: /publication/convergence
excerpt: 'We will investigate convergence theorems'
date: 2024-10-20
order: 13
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Convergence Theorems'
--- 

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $\{ F_n \}$ be a sequence of distribution functions, if there exists a distribution function $F$ such that 
  
$$
\lim_{n \to +\infty} F_n(x) = F(x)
$$

at every point $x$ which $F$ is continuous, we say that $F_n$ converges in law (or weakly) to $F$, and we write $F_n \overset{\omega}{\to} F$;

Let $\{ X_n \}$ be a sequence of random variables and $\{ F_n \}$ be the corresponding distribution functions, we say that $X_n$ converges in distribution (or law) to $X$ if there exists an random variable $X$ with distribution function $F$ such that $F_n \overset{\omega}{\to} F$. We write $X_n \overset{L}{\to} X$.

</div>



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $\{ X_n \}, X$ be continuous random variables such that $\lim_{n \to +\infty} f_n(x) = f(x)$ for a.e $x \in \mathbb{R}$ where $f_n, f$ are the probability density functions of $X_n$ and $X$ respectively, then $X_n \overset{L}{\to} X$.
</div>


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $\{ X_n \}$ be a sequence of random variables defined on some probability space $(\Omega,\mathcal{F},\mathbb{P})$, we say that the sequence $\{ X_n \}$ converges in probability to the random variable $X$ if $\forall \epsilon >0$,
$$
\lim_{n \to +\infty} \mathbb{P} \{ \vert X_n - X \vert > \epsilon \} = 0
$$
And we denote by $X_n \overset{P}{\to} X$.
</div>

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Let $X$ be a random variable and $X_n = X + Y_n$, where
  
$$
\mathbb{E}EY_n = \frac{1}{n} \hspace{0.4cm} \mathbf{Var}(Y_n) = \frac{\sigma^2}{n}
$$

where $\sigma >0$ is a constant. Show that $X_n \overset{P}{\to} X$.
</div>
 
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    By triangle inequality, we have
    
$$
\vert Y_n \vert \leq \vert Y_n - \mathbb{E} Y_n \vert + \vert \mathbb{E} Y_n \vert = \vert Y_n - \mathbb{E} Y_n \vert + \frac{1}{n}.
$$

Then, $\forall \epsilon >0$, we have

$$
\begin{align*}
\mathbb{P}\{ \vert X_n - X \vert \geq \epsilon \} & = \mathbb{P} \{ \vert Y_n \vert \geq \epsilon \}\\
& \leq \mathbb{P} \left\{ \vert Y_n -\mathbb{E} Y_n \vert + \frac{1}{n} \geq \epsilon \right\} \\
& = \mathbb{P} \left\{ \vert Y_n - \mathbb{E} Y_n \vert \geq \epsilon - \frac{1}{n} \right\} \\
& \leq \frac{\mathbf{Var}(Y_n)}{\left( \epsilon - \frac{1}{n} \right)^2} \hspace{2cm} \text{By Chebyshev's Inequality} \\
& = \frac{\sigma^2}{n \left( \epsilon - \frac{1}{n} \right)^2} \to 0, \hspace{1cm} \text{as $n \to +\infty$}.
\end{align*}
$$

Therefore we conclude that $X_n \overset{P}{\to} X$.
  </div>
</details>




As we mentioned previously, convergence in probability is stronger than convergence in distribution. That is, if $X_n \overset{P}{\to} X$ then $X_n \overset{d}{\to} X$. However the converse is not necessarily true. To see this, let $X_1,X_2,\cdots,X_3$ be a sequence of i.i.d $Bernoulli(0.5)$ random variables, Let also $X \sim Bernoulli(0.5)$ be independent from the $X_i$'s, then $X_n \to X$, however $X_n$ does not converge in probability to $X$ since $\vert X_n - X \vert$ is in fact also a $Bernoulli(0.5)$ random variable and

$$
\mathbb{P}\{ \vert X_n - X \vert \geq \epsilon \} = 0.5
$$

A special case in which the converse true is when $X_n \overset{d}{\to} c$ where $c$ is a constant. In this case convergence in distribution implies convergence in probability.

<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> If $X_n \overset{d}{\to} c$ where $c$ is a constant, then $X_n \overset{P}{\to} c$.
</div>



<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide proof
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Proof.</strong><br>
    Suppose $X_n$ has distribution function $F_X$, then by definition we know that $\lim_{n \to +\infty} F_X = c$. Now for anny $k>0$ we have

  $$
\begin{align*}
\mathbb{P}\{ \vert X_n - c \vert < k \} &= \mathbb{P} \{ -k < X_n - c < k\} \\
&= \mathbb{P}\{ -k+c < X_n < k+c \}\\
&= F_{X}(k+c) - F_X(-k+c) \\
&=1
\end{align*}
$$

thus $X_n \overset{P}{\to} c$.
  </div>
</details>





<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> 
  1. $X_n \overset{P}{\to} X \Longleftrightarrow
X_n - X \overset{P}{\to} 0$;

2.  If $X_n \overset{P}{\to} X$ and $X_n \overset{P}{\to} Y$, then $\mathbb{P}\{ X = Y\} = 1$.
</div>


<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> 
  
  If $X_n  \overset{P}{\to} X$, then $X_n - X_m \overset{P}{\to} 0$.



If $X_n \overset{P}{\to} X$ and $Y_n \overset{P}{\to} Y$, then 

$$
X_n \pm Y_n \overset{P}{\to} X \pm Y
$$

</div>


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Continuous Mapping Theorem.</strong> Let $X_n \overset{P}{\to} X$ and $g$ is a continuous function defined on $\mathbb{R}$, then $g(X_n) \overset{P}{\to} g(X)$.
</div>



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> If $X_n \overset{P}{\to} X$, then $X_n \overset{L}{\to} X$.
</div>


In general, the reverse of this theorem is not true!



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Slutsky's Theorem.</strong> 
If $\vert X_n - Y_n \vert \overset{P}{\to} 0$ and $Y_n \overset{P}{\to} Y$, then $X_n \overset{P}{\to} Y$.
</div>


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Cramer's Theorem.</strong> 

If $X_n \overset{L}{\to} X, Y_n \overset{P}{\to} c$ where $c$ is a constant, then

1. $X_n \pm Y_n \overset{L}{\to} X \pm c$;

2. $X_n Y_n \overset{L}{\to} cX$ if $c\neq 0$ and $X_nY_n \overset{P}{\to} 0$ if $c=0$;

3. $\displaystyle{\frac{X_n}{Y_n} \overset{L}{\to} \frac{X}{c}}$ if $c \neq 0$.
</div>



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Let $X_1,X_2,\cdots$ be a sequence of $i.i.d$ random variables with common probability density function $f(x) = e^{-(x-\theta)}$ for $x \geq \theta$ and $=0$ otherwise. Let $\overline{X}_n$ denote the sample mean given by $\overline{X}_n = \frac{1}{n} \sum_{i=1}^n X_i$.

(a) Show that $\overline{X}_n \overset{P}{\to} 1+\theta$;

(b) Show that for any sequence $Y_1,Y_2,\cdots,Y_n$ of random variables and a constant $c$, if $ Y_n \overset{L}{\to} c$, then $Y_n \overset{P}{\to} c$;

(c) Show that $\min(X_1,X_2,\cdots,X_n) \overset{P}{\to} \theta$.
</div>
 
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    (a) : First we find $\mathbb{E} X$, since those are $i.i.d$, they must have the same $\mathbb{E} X$ value:

  $$
\begin{align*}
\mathbb{E} X &= \int_{-\infty}^{+\infty} x f_X(x) dx \\
& = \int_{\theta}^{+\infty} x e^{-(x - \theta)} dx\\
& = -xe^{-(x - \theta)} \Bigg\vert_{\theta}^{+\infty}
- \int_{\theta}^{+\infty} -e^{-(x - \theta)} dx \\
& = \theta + 1.
\end{align*}
$$


Then, we find out that what we want to show is just $\overline{X}_n \overset{P}{\to} \mathbb{E} X$, to further prove this we consider for any $\epsilon>0$, the term
$\mathbb{P} \{ \vert \overline{X}_n - \mathbb{E} X \vert >\epsilon \}$, and by Chevbeshev's inequality,

$$
\begin{align*}
\mathbb{P}\{ \vert \overline{X}_n - \mathbb{E} X \vert > \epsilon \} &\leq \frac{\mathbf{Var}(\overline{X}_n)}{\epsilon^2} \\
& = \frac{\frac{1}{n} \mathbf{Var}(X)}{\epsilon^2}\\
& = \frac{\mathbf{Var}(X)}{\epsilon^2} \cdot \frac{1}{n} \to 0, \text{as $n \to +\infty$}.
\end{align*}
$$

So we have proved that $\overline{X}_n \overset{P}{\to} 1+\theta$.

(b) : By definition, $Y_n \overset{L}{\to} c$ implies $\lim_{n \to +\infty} F_{Y_n} = c$ where $c$ is a constant and $F_{Y_n}$ is the distribution function of the random variable $Y_n$, and we have

$$
\begin{align*}
\mathbb{P} \{ \vert Y_n - c \vert < \epsilon \} &= \mathbb{P}\{ -\epsilon < Y_n - c < \epsilon \} \\
&= \mathbb{P}\{ -\epsilon + c < Y_n < \epsilon + c \} \\
&= F_{Y_n}(\epsilon + c) - F_{Y_n}(-\epsilon + c) \\
& \overset{\text{as $n \to +\infty$}}{\to} 1
\end{align*}
$$

Thus we have proved that $Y_n \overset{P}{\to} c$.

(c) : Define $X_0 = \min(X_1,X_2,\cdots,X_n)$, then by definition, 

$$
\begin{align*}
\mathbb{P}(X_0 \geq x) \implies \mathbb{P}(X_1 \geq x, X_2 \geq x, \cdots, X_n \geq x) &= \left( \int_{x}^{+\infty} e^{-(t - \theta)} dt \right)^n \\
&=e^{-n(x - \theta)}, \text{if $x > \theta$}.
\end{align*}
$$

Thus we have 

$$
f_{Y_0}(x) = \begin{cases} 1 : x \leq \theta \\ e^{-n(y - \theta)} : y > \theta \end{cases}
$$

and the distribution function is

$$
F_{Y_0}(x) = \begin{cases} 0 : x \leq \theta \\ e^{-n(x - \theta)} : x > \theta \end{cases}
$$

as $n \to +\infty$, $F_{Y_0}(x) \to \begin{cases} 0 : x \leq \theta \\ 1: y > \theta \end{cases}$ and hence we have $Y_n \overset{L}{\to} \theta$ where $\theta$ is a constant, and thus by (b), $Y_n \overset{P}{\to} \theta$.
 </div>
</details>




<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Let $X_1,X_2,\cdots,X_n$ be $i.i.d$ random variables with common mean $0$ and variance $1$, suppose $\beta_4 = \mathbb{E} X^4 < +\infty$. Find the limiting distribution of the random variable
    
$$
W_n = \sqrt{n} \frac{\sum_{i=1}^n X_i}{\sum_{i=1}^n X_i^2}.
$$
</div>

<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
     Note that
    
$$
W_n = \sqrt{n} \frac{\sum_{i=1}^n X_i}{\sum_{i=1}^n X_i^2} = \frac{\frac{\sum X_i}{\sqrt{n}}}{\frac{\sum X_i^2}{n}}
$$

We define

$$
U_n = \frac{\sum_{i=1}^n X_i}{\sqrt{n}}, V_n = \frac{\sum_{i=1}^n X_i^2}{n}
$$

Then, according to the properties of $X_i$, we know that $\mu = 0, \sigma = 1$, and the Central Limit Theorem states that

$$
\frac{\sum_{i=1}^n X_n - \mu}{\sigma / \sqrt{n}} \to N(0,1)
$$

If we define $\overline{X} = \frac{1}{n} \sum_{i=1}^n X_i$, then

$$
U_n = \frac{\sum_{i=1}^n X_i}{\sqrt{n}} = \frac{n\overline{X}}{\sqrt{n}} = \frac{\overline{X}}{1/\sqrt{n}} = \frac{\overline{X} - n\mu}{\sigma  \sqrt{n}} \to N(0,1)
$$

So we have $U_n \overset{L}{\to} N(0,1)$ by Central Limit Theorem.

Furthermore, if we define $Y_i = X_i^2$, then $V_n = \overline{Y}_n$, and we know that

$$
\mathbb{E}(Y) = \mathbb{E}(X^2) = \mathbf{Var}(X) + (\mathbb{E} X)^2 = 1, \mathbf{Var}(Y) = \mathbb{E}(X^4) - (\mathbb{E}(X^2))^2 = \beta_4 - 1 < +\infty
$$

And then we have

$$
\mathbb{E}(\overline{Y}_n) = \mathbb{E}\left( \frac{Y_1+\cdots+Y_n}{n} \right) = \frac{1}{n} \sum_{i=1}^n \mathbb{E} Y_i = \mathbb{E} Y = 1
$$

and

$$
\mathbf{Var}(\overline{Y}_n) = \mathbf{Var}\left( \frac{1}{n} \sum_{i=1}^n Y_i \right) =\frac{1}{n^2} \mathbf{Var}(Y_1 + \cdots+Y_n) = \frac{1}{n^2} n \mathbf{Var}(Y_i) = \frac{\mathbf{Var}(Y)}{n}.
$$

So Chevbeshev's inequality states that for any $k >0$,

$$
\begin{align*}
\mathbb{P}\{ \vert \overline{Y}_n - \mathbb{E} \overline{Y}_n \vert \geq k \} &\leq \frac{\mathbf{Var}(\overline{Y}_n)}{k^2}\\
& = \frac{\mathbf{Var}(Y)}{n k^2} \leq \frac{\beta_4}{n k^2} \to 0, \text{as $n \to +\infty$}.
\end{align*}
$$

So we have that $\overline{Y}_n \overset{P}{\to} 1$, and by Cramer's theorem, we have

$$
\frac{U_n}{V_n} \overset{L}{\to} N(0,1).
$$

  </div>
</details>


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Exercise.</strong>  Let $X_1,\cdots$ be a sequence of $i.i.d$, $U[0,1]$ random variables, and define
  
$$
Y_n = \min\{ X_1,\cdots, X_n\}
$$

Then prove the following results separately:

(a) $Y_n \overset{d}{\to} 0$;

(b) $Y_n \overset{P}{\to} 0$;

(c) $Y_n \overset{a.s}{\to} 0$;

(d) $Y_n \overset{L^r}{\to} 0$ for all $r \geq 1$.
</div>














