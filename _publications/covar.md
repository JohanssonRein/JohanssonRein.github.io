---
title: "Covariance and Correlations"
collection: publications
category: probability
permalink: /publication/covar
excerpt: 'We will investigate covariance and correlations'
date: 2024-10-05
order: 10
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Covariance and Correlations'
---


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> If random variables $X,Y$ satisfies $\mathbb{E}\{(X - \mathbb{E} X)(Y - \mathbb{E} Y)\} <+\infty$, we then call it the covariance between $X$ and $Y$ and write

$$
\mathbf{Cov}(X,Y) = \mathbb{E}\{ (X - \mathbb{E} X)(Y - \mathbb{E} Y)\} = \mathbb{E}(XY) - \mathbb{E}(X)\mathbb{E}(Y)
$$
</div>


<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> If $X,Y$ are independent, then $\mathbf{Cov}(X,Y) = 0$.
</div>



<details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide proof</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Proof.</strong><br>
      Since $X,Y$ are independent, so for any functions $h,g$, we have
  
$$
\mathbb{E}\{ g(X)h(Y) \} = \mathbb{E}\{ g(X) \} \mathbb{E}\{ h(Y) \}
$$

So we have $\mathbb{E}(XY) = \mathbb{E}(X)\mathbb{E}(Y)$, which finishes the proof.

  </div>
  </details>



<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> We also have the following propositions for covariance:

1. $\mathbf{Cov}(Y,X) = \mathbf{Cov}(X,Y)$;

2. $\mathbf{Cov}(X,X) = \mathbf{Var}(X)$;

3. $\mathbf{Cov}(aX,Y) = a \mathbf{Cov}(X,Y)$;

4. $\displaystyle{\mathbf{Cov} \left( \sum_{i=1}^n X_i, \sum_{j=1}^m Y_j \right) = \sum_{i=1}^n \sum_{j=1}^m \mathbf{Cov}(X_i,Y_j)}$
</div>



The proofs are left as an exercise. One important remark is that we have

$$
\mathbf{Var}\left( \sum_{i=1}^n X_i \right) = \sum_{i=1}^n \mathbf{Var}(X_i) + 2 \sum \sum_{i<j} \mathbf{Cov}(X_i,X_j).
$$


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> The correlation of two random variables $X,Y$ denoted by $\rho(X,Y)$, is defined as long as $\mathbf{Var}(X), \mathbf{Var}(Y)$ is positive, is defined by
  
$$
\rho(X,Y) = \frac{\mathbf{Cov}(X,Y)}{\sqrt{\mathbf{Var}(X) \mathbf{Var}(Y)}}
$$
</div>


<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> 
$$
-1 \leq \rho(X,Y) \leq 1
$$
</div>

<details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide proof</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Proof.</strong><br>
     Suppose $X,Y$ have variances given by $\sigma_x^2, \sigma_y^2$ respectively, then on the one hand,

$$
\begin{align*}
0 &\leq \mathbf{Var} \left( \frac{X}{\sigma_x} + \frac{Y}{\sigma_y} \right)\\
&= \frac{\mathbf{Var}(X)}{\sigma_x^2} + \frac{\mathbf{Var}(Y)}{\sigma_y^2} + \frac{2 \mathbf{Cov}(X,Y)}{\sigma_x \sigma_y} \\
& = 2[1 + \rho(X,Y)]
\end{align*}
$$

implying that

$$
-1 \leq \rho(X,Y).
$$

On the other hand,

$$
\begin{align*}
0 &\leq \mathbf{Var} \left( \frac{X}{\sigma_x} - \frac{Y}{\sigma_y} \right)\\
&= \frac{\mathbf{Var}(X)}{\sigma_x^2} + \frac{\mathbf{Var}(Y)}{\sigma_y^2}  -\frac{2 \mathbf{Cov}(X,Y)}{\sigma_x \sigma_y} \\
& = 2[1 - \rho(X,Y)]
\end{align*}
$$

implying that

$$
\rho(X,Y) \leq 1.
$$
  </div>
  </details>



The correlation coefficient is a measure of the degree of linearity between $X$ and $Y$. A value of $\rho(X,Y)$ near $+1$ or $-1$ indicates a high degree of linearity between $X$ and $Y$, whereas a value near $0$ indicates that such linearity is absent. A positive
value of $\rho(X, Y)$ indicates that $Y$ tends to increase when $X$ does, whereas a negative value indicates that $Y$ tends to decrease when $X$ increases. If $\rho(X,Y) = 0$, then $X$ and $Y$ are said to be uncorrelated.

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Let $X_1,X_2,\cdots,X_n$ be independent and identically distributed random variables having variance $\sigma^2$, show that
  
$$
\mathbf{Cov}(X_i - \overline{X}, \overline{X}) = 0
$$

where $\overline{X}$ is called the sample mean, denoted by

$$
\overline{X} = \frac{\sum_{i=1}^n X_i}{n}.
$$

 <details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide solution</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Solution.</strong><br>
      We have

  $$
\begin{align*}
\Cov(X_i - \overline{X}, \overline{X}) &= \Cov(X_i, \overline{X}) - \Cov(\overline{X}, \overline{X}) \\
&= \Cov \left( X_i, \frac{1}{n} \sum_{j=1}^n X_j \right) - \Var(\overline{X}) \\
& = \frac{1}{n} \sum_{j=1}^n \Cov(X_i,X_j) - \frac{\sigma^2}{n}\\
& = \frac{\sigma^2}{n} - \frac{\sigma^2}{n} \\
&=0.
\end{align*}
$$
    </div>
  </details>

</div>


<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Let $X,Y$ to be random variables, consider $X' = aX+b, Y'= cY + d$ where $a,c >0$, then
  
$$
\rho(X,Y) = \rho(X',Y').
$$
</div>


<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide proof
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Proof.</strong><br>
    If we denote $\mu_X = \mathbb{E} X, \mu_Y = \mathbb{E} Y$, then we have

$$
\mathbb{E} X' = a\mathbb{E} X + b = a \mu_X + b
$$

$$
\mathbb{E} Y' = c\mathbb{E} Y + d = c \mu_Y + d
$$

Also

$$
\begin{align*}
\mathbf{Var}(X') &= \mathbb{E}[(X - \mu_{X'})^2]\\
& = \mathbb{E}[ (aX + b - a\mu_X - b)^2] \\
& = \mathbb{E}[ a^2(X - \mu_X)^2] \\
& = a^2 \mathbb{E}[ (X - \mu_X)^2] = a^2 \sigma_X.
\end{align*}
$$

Likewise, we have

$$
\mathbf{Var}(Y') = c^2 \sigma_Y.
$$

So

$$
\begin{align*}
\rho(X',Y') & = \frac{\mathbf{Cov}(X',Y')}{\sigma_{X'} \sigma_{Y'}}\\
& = \frac{\mathbb{E}[(X' - \mu_{X'})(Y' - \mu_{Y'})]}{\sigma_{X'} \sigma_{Y'}} \\
& = \frac{ac \mathbf{Cov}(X,Y)}{\sigma_{X'} \sigma_{Y'}}\\
& = \frac{ac\mathbf{Cov}(X,Y)}{(a\sigma_X)(c\sigma_Y)} \\
& = \rho(X,Y).
\end{align*}
$$

</div>
</details>


It shows that shifting and re-scaling of random variables does not change the correlation.


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  $N$ people sit around a round table ($N>5$). Each person will toss a fair coin. Anyone whose outcome is different from his/her two neighbors will receive a present. Let $X$ be the number of people who receives presents, find $\mathbb{E} X$ and $\mathbf{Var} X$.


<details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide solution</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Solution.</strong><br>
     Number those $N$ people from $1$ to $N$, let $X_i$ be the random variable defined as

$$
X_i = \begin{cases} 1:\text{if the person receives the present} \\ 0: \text{otherwise} \end{cases}
$$

then clearly $X = X_1+X_2+\cdots+X_n$. And observe that $\mathbb{P}(X_i = 1) = 0.25$, this is because all possible outcomes of that person and his/her neighbors are:

$$
HHH,TTT,HTT,HHT,HTH,THH,THT,TTH
$$

and then by linearity we have

$$
\mathbb{E} X = \mathbb{E} X_1 + \cdots +\mathbb{E} X_n = \frac{N}{4}.
$$

The variance is left as an exercise.
    </div>
  </details>
</div>


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Suppose $X,Y$ are random variables, then
  
$$
\mathbb{E}\vert X + Y \vert^r \leq C_r \left( \mathbb{E}\vert X \vert^r +\mathbb{E}\vert Y \vert^r\right)
$$
where $C_r = \begin{cases} 1: 0 \leq r \leq 1 \\ 2^{r-1} : r>1 \end{cases}$.
</div>

<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide proof
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Proof.</strong><br>
    This follows from the fact that 

$$
\vert a + b \vert^r \leq C_r [ \vert a \vert^r + \vert b \vert^r ].
$$

**QED**

<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Hölder's Inequality)

Let $X,Y$ be random variables and let $p>1,q>1$ so that $\frac{1}{p} + \frac{1}{q} = 1$, then

$$
\mathbb{E}\vert X Y \vert \leq \left( \mathbb{E}\vert X \vert^p \right)^{\frac{1}{p}} \left( \mathbb{E} \vert X \vert^q \right)^{\frac{1}{q}}
$$

If we take $p=q=2$, we will get a special case of Hölder's inequality, which is known as the Cauchy-Schwarz inequality.
</div>

<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $X,Y$ be random variables, then
  
$$
\mathbb{E} \vert X Y \vert \leq \sqrt{\mathbb{E}\vert X \vert^2} \cdot \sqrt{\mathbb{E}\vert Y \vert^2}
$$
  </div>
</details>

</div>



<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Let $X,Y$ be random variables, then
  
$$
\vert \mathbf{Cov}(X,Y) \vert \leq \sigma_{X} \cdot \sigma_{Y}
$$

where we define

$$
\sigma_X = \sqrt{\mathbf{Var}(X)}, \sigma_Y = \sqrt{\mathbf{Var}(Y)}.
$$
</div>



<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> (Lyapononv's Inequality)

Let $X$ be a random variable, and $1\leq r < s <+\infty$, then

$$
\left( \mathbb{E}\vert X \vert^r \right)^{\frac{1}{r}} \leq \left( \mathbb{E}\vert X \vert^s \right)^{\frac{1}{s}}
$$
</div>



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> (Jensen's Inequality)

If $g$ is a convex function (i.e $f''(x)>0$) and $\mathbb{E} X$ exists, then

$$
g(\mathbb{E} X) \leq \mathbb{E}(g(X)).
$$

Likewise, if $g$ is concave (i.e $f''(x)<0$) and $\mathbb{E} X$ exists, then

$$
g(\mathbb{E} X) \geq \mathbb{E}(g(X)).
$$
</div>



