---
title: "Order Statistics and Exchangeable Random Variables"
collection: publications
category: probability
permalink: /publication/orderstats
excerpt: 'We will investigate order statistics and exchangeable random variables'
date: 2024-10-01
order: 9
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Order Statistics and Exchangeable Random Variables'
---


# Order Statistics


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $X_1,X_2,\cdots,X_n$ be $n$ independent and identically distributed continuous random variables having a common density $f$ and distribution function $F$, define
$$
\begin{align*}
X_{(1)} &= \text{the smallest of $X_1,X_2,\cdots,X_n$}\\
X_{(2)} &= \text{the second smallest of $X_1,X_2,\cdots,X_n$}\\
&\vdots\\
X_{(j)} &= \text{the $j$th smallest of $X_1,X_2,\cdots,X_n$}\\
&\vdots\\
X_{(n)} &= \text{the largest of $X_1,X_2,\cdots,X_n$}
\end{align*}
$$

Then the ordered values $X_{(1)} \leq X_{(2)} \leq \cdots \leq X_{(n)}$ are known as the order statistics corresponding to the random variables $X_1,X_2,\cdots,X_n$. 
</div>


The joint density function of the order statistics is obtained by noting that the order statistics $X_{(1)},X_{(2)},\cdots,X_{(n)}$ will take on the values $x_1 \leq x_2 \leq \cdots \leq x_n$ if and only if for some permutation $(i_1,i_2,\cdots,i_n) \in S_n$, we have

$$
X_1 = x_{i_1} , X_2 = x_{i_2}, \cdots, X_n = x_{i_n}
$$

Since for any permutation $(i_1,i_2,\cdots,i_n) \in S_n$,

$$
\begin{align*}
&\mathbb{P} \left\{ x_{i_1} - \frac{\epsilon}{2} < X_1 < x_{i_1} + \frac{\epsilon}{2}, \cdots,x_{i_n} < X_n < x_{i_n} + \frac{\epsilon}{2} \right\}\\
&\approx \epsilon^n f_{X_1,X_2,\cdots,X_n}(x_{i_1}, x_{i_2}, \cdots, x_{i_n})\\
&= \epsilon^n f(x_1) \cdots f(x_n)
\end{align*}
$$


it follows that for $x_1 < x_2 < \cdots < x_n$,

$$
\begin{align*}
&\mathbb{P} \left\{ x_1 - \frac{\epsilon}{2} < X_{(1)} < x_1 + \frac{\epsilon}{2}, \cdots,x_n < X_{(n)} < x_n + \frac{\epsilon}{2} \right\}\\
& \approx n! \epsilon^n f(x_1) \cdots f(x_n)
\end{align*}
$$

Dividing by $\epsilon^n$ and letting $\epsilon \to 0$ yields

$$
f_{X_{(1)},\cdots,X_{(n)}} (x_1,x_2,\cdots,x_n) = n! f(x_1) f(x_2) \cdots f(x_n), \hspace{0.2cm} x_1<x_2<\cdots<x_n
$$


**Example:** Along a $1$ mile long road are $3$ people "distributed at random". Find the probability that no $2$ people are less than a distance of $d$ miles apart when $d \leq \frac{1}{2} $.

**Solution:** Assume the the positions of the $3$ people are independent and uniformly distributed over the road, if $X_i$ denote the position of the $i$th person, the desired probability is given by

$$
\mathbb{P} \{ X_{(i)} > X_{(i-1)} + d, i = 2,3 \}
$$

and we have

$$
f_{X_{(1)}, X_{(2)}, X_{(3)}} (x_1,x_2,x_3) = 3!, \hspace{0.2cm} 0<x_1<x_2<x_3<1
$$

Thus

$$
\begin{align*}
\mathbb{P}\{ X_{(i)} > X_{(i-1)} + d, i =2,3 \} &= \iiint_{x_i > x_{j-1}+d} f_{X_{(1)}, X_{(2)}, X_{(3)}} (x_1,x_2,x_3) dx_1dx_2dx_3 \\
& = 3! \int_0^{1-2d} \int_{x_1+d}^{1-d} \int_{x_2+d}^1 dx_3dx_2dx_1\\
&= (1-2d)^3
\end{align*}
$$

In fact, this method can be generalized, when $n$ people are distributed at random over the unit interval, the desired probability is

$$
[1-(n-1)d]^n, \hspace{0.2cm} \text{when} \hspace{0.2cm} d \leq \frac{1}{n-1}
$$

The density function of the $j$th order statistic $X_{(j)}$ can be obtained either by integrating the joint density function or by direct reasoning as follows: In order for $X_{(j)}$ to equal $x$, it is necessary for $j-1$ of the $n$ values $X_1,\cdots,X_n$ to be less than $x$ and $n-j$ of them to be greater than $x$, and $1$ of them to equal $x$. Now the probability density that any given set of $j-1$ of the $X_i$'s are less than $x$, another given set of $n-j$ are all greater than $x$, and the remaining value is equal to $x$ equals

$$
[F(x)]^{j-1} [1-F(x)]^{n-j} f(x)
$$

Hence, since there are

$$
\binom{n}{j-1,n-j,1} = \frac{n!}{(n-j)!(j-1)!}
$$

different partitions, it follows that the density function of $X_{(j)}$ is given by

$$
f_{X_{(j)}}(x) = \frac{n!}{(n-j)!(j-1)!}[F(x)]^{j-1}[1-F(x)]^{n-j}f(x)
$$

and the cumulative distribution function of $X_{(j)}$ is given by

$$
F_{X_{(j)}}(y) = \frac{n!}{(n-j)!(j-1)!} \int_{-\infty}^y [F(x)]^{j-1} [1-F(x)]^{n-j}f(x)dx
$$

However by definition we also have

$$
\begin{align*}
F_{X_{(j)}}(y) = \mathbb{P}\{ X_{(j)} \leq y \} &= \mathbb{P}\{ \text{$j$ or more of the $X_i$'s are less or equal than $y$} \} \\
& = \sum_{k=j}^n \binom{n}{k} [F(y)]^k [1-F(y)]^{n-k}
\end{align*}
$$


So we have an interesting inequality:

$$
\frac{n!}{(n-j)!(j-1)!} \int_{-\infty}^y [x]^{j-1} [1-x]^{n-j}dx = \sum_{k=j}^n \binom{n}{k} y^k [1-y]^{n-k}, \hspace{0.2cm} 0 \leq y \leq 1
$$

Furthermore, the joint density function of the order statistics $X_{(i)}$ and $X_{(j)}$ when $1 < j$ is

$$
f_{X_{(i)}, X_{(j)}}(x_i,x_j) = \frac{n!}{(i-1)!(j-i-1)!(n-j)!}[F(x_i)]^{i-1} [F(x_j) - F(x_i)]^{j-i-1}[1-F(x_j)]^{n-j} f(x_i)f(x_j).
$$

Now suppose that $n$ independent and identically distributed random variables $X_1,X_2,\cdots,X_n$ are observed, the random variable $R$ defined by $R:= X_{(n)} - X_{(1)}$ 
is called the range of the observed random variables. If the random variables $X_i$ have distribution function $F$ and density function $f$, then for $a \geq 0$ we have

$$
\begin{align*}
\mathbb{P}\{ R \leq a\} & = \mathbb{P} \{ X_{(n)} - X_{(1)} \leq a \} \\
& = \iint_{x_n -x_1 \leq a} f_{X_{(1)}, X_{(n)}}(x_1,x_n) dx_1dx_n\\
& = \int_{-\infty}^{+\infty} \int_{x_1}^{x_1+a} \frac{n!}{(n-2)!} [F(x_n) - F(x_1)]^{n-2} f(x_1)f(x_n) dx_ndx_1 
\end{align*}
$$

By making $y = F(x_n) - F(x_1)$, we have

$$
\int_{x_1}^{x_1+a} [F(x_n) - F(x_1)]^{n-2}f(x_n)dx_n = \int_0^{F(x_1+a) - F(x_1)} y^{n-2}dy = \frac{1}{n-1}[F(x_1+a) - F(x_1)]^{n-1}
$$

Thus

$$
\mathbb{P}\{ R \leq a\} = n \int_{-\infty}^{+\infty} [F(x_1+a) - F(x_1)]^{n-1} f(x_1)dx_1
$$

In the case when $X_i$'s are all uniformly distributed on $(0,1)$, for $0<a<1$, we have

$$
\begin{align*}
\mathbb{P}\{ R < a\} & = n \int_0^1 [F(x_1+a) - F(x_1)]^{n-1} f(x_1)dx_1\\
&= n \int_0^{1-a} a^{n-1} dx_1 + n \int_{1-a}^1 (1-x_1)^{n-1}dx_1\\
& n(1-a)^{n-1} + a^n
\end{align*}
$$

Differentiation yields the density function of the range, given in this case by

$$
f_R(a) = \begin{cases} n(n-1)a^{n-2}(1-a) : 0 \leq a \leq 1 \\ 0 : \text{otherwise} \end{cases}
$$

That is, the range of $n$ independent uniform $(0,1)$ random variables is a beta random variable with parameters $n-1,2$. 


**Exercise:** Let $(X,Y)$ denote a random point in the plane, and assume that the rectangular coordinates $X,Y$ are independent standard normal random variables. We are interested in the joint distribution of $R,\Theta$, the polar coordinate representation of $(x,y)$


# Exchangeable Random Variables

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> The random variables $X_1,X_2,\cdots,X_n$ are said to be exchangeable if, for every permutation $\pi(i_1,i_2,\cdots,i_n) \in S_n$, we have

$$
\mathbb{P} \{ X_{i_1} \leq x_1, X_{i_2} \leq x_2, \cdots, X_{i_n} \leq x_n \} = \mathbb{P}\{ X_1 = x_1, X_2 = x_2, \cdots, X_n = x_n \}
$$

That is, the $n$ random variables are exchangeable if their joint distribution is the same no matter in which order the variables are observed.
</div>



For example, if $n=4$ and using a particular permutation $\pi = (3,1,2,4)$, we want

$$
f_{X_1,X_2,X_3,X_4}(x_1,x_2,x_3,x_4) = f_{X_3,X_1,X_2,X_4}(x_1,x_2,x_3,x_4)
$$

If $X_i$'s are discrete, this is equivalent to say

$$
\mathbb{P}\{ X_1=x_1, X_2=x_2, X_3 = x_3,X_4 = x_4 \} = \mathbb{P}\{ X_3 = x_1, X_1 = x_2,X_2 = x_3,X_4 = x_4\}
$$

**Example:** Suppose we have an urn containing $1$ red ball and $2$ white balls, draw out balls one at a time and without replacement, and note the color. Define

$$
X_i = \begin{cases} 1, \hspace{0.2cm} \text{if the $i$th ball is red} \\ 0, \hspace{0.2cm} \text{otherwise} \end{cases}


Then the random variables $X_1,X_2,X_3$ are exchangeable.

To see this, we compute the followings:

$$
\mathbb{P}(X_1 = 1, X_2 = 0, X_3 = 0) = \frac{1}{3} \cdot 1 \cdot 1 = \frac{1}{3}
$$

$$
\mathbb{P}(X_1 = 0, X_2 = 1, X_3 = 0) = \frac{2}{3} \cdot \frac{1}{2} \cdot 1 = \frac{1}{3}
$$

$$
\mathbb{P}(X_1 = 0, X_2 = 0, X_3 = 1) = \frac{2}{3} \cdot \frac{1}{2} \cdot 1 = \frac{1}{3}
$$
Since they are all the same, so we say $X_1, X_2, X_3$ are exchangeable.

<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Suppose that $X_1,X_2,\cdots, X_n$ are independent and identically distributed (iid), then $X_1,X_2,\cdots, X_n$ are exchangeable.
</div>

**Proof:**
Let $f$ be the probability density function for any of the $X_i$, then by definition we have

$$
f_{X_1,X_2,\cdots,X_n}(x_1,x_2,\cdots,x_n) \overset{iid}{=} f(x_1)\cdot f(x_2)\cdots f(x_n)
$$

Thus $R.H.S$ can be arranged in any order as desired.

**QED**

<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Exchangeable random variables are identically distributed.

</div>

**Proof:**
consider the continuous interchangeable random variables $X_1,X_2,\cdots, X_n$, and by the generalized Fubini's theorem, it's clear that

$$
\begin{align*}
f_{X_i}(x_i) &= \int \int \cdots \int f_{X_1,\cdots,X_n}(x_1,\cdots x_i ,\cdots, x_j , \cdots x_n) dx_1 \cdots d_{x_{i-1}} d_{x_{i+1}} \cdots dx_n\\
&=\int \int \cdots \int f_{X_1,\cdots,X_n}(x_1,\cdots x_j ,\cdots, x_i , \cdots x_n) dx_1 \cdots d_{x_{i-1}} d_{x_{i+1}} \cdots dx_n
\end{align*}
$$

Thus it also holds for any permutation $\pi \in S_n$, and
thus we conclude that $f_{X_1}(x_1) = f_{X_2}(x_2) = \cdots = f_{X_n}(x_n)$

**QED**

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> The random variables $X_1,X_2,\cdots$ in an infinite sequence are said to be exchangeable if the finite collection $X_1,X_2,\cdots,X_n$ are exchangeable for any finite $n \geq 1$.
</div>



**Example:** (Pólya’s Urn) Suppose we have an urn containing $R_0$ red balls and $W_0$ white balls, and $c \geq 0$ be a fixed integer. We draw a ball, note the color, replace the ball and put an additional $c$ balls of that color in the urn as well. Rinse and repeat. Define

$$
X_i = \begin{cases} 1, \hspace{0.2cm} \text{if the $i$th ball is red} \\ 0, \hspace{0.2cm} \text{otherwise} \end{cases}
$$

Then the infinite sequence of random variables $X_1,X_2,\cdots,X_n$ are exchangeable.

To see this, we begin with an illustration that we will later generalize, note that

$$
\begin{align*}
& \mathbb{P}(X_1=1,X_2=1,X_3=0,X_4=1,X_5=0) \\=  &\frac{R_0}{R_0+W_0} \cdot \frac{R_0+c}{R_0+W_0+c} \cdot \frac{W_0}{R_0+W_0+2c} \cdot \frac{R_0+2c}{R_0+W_0+3c} \cdot \frac{W_0 +c}{R_0+W_0+4c}
\end{align*}
$$

Fix any positive integer $n$ and consider the sequence $X_1,X_2,\cdots,X_n$, we want to give an general expression for $\mathbb{P}(X_1=x_1,X_2=x_2,\cdots,X_n = x_n)$, from the particular case illustrated above, it is easy to see that the denominator of this more general case will be

$$
(R_0+W_0)(R_0+W_0+c)(R_0+W_0+2c)\cdots(R_0+W_0+(n-1)c)
$$

Note that $\sum_{i=1}^n x_i$ is the number of red balls chosen in $n$ draws from the urn and $n - \sum_{i=1}^n x_i$ is the number of the white balls.

If $\sum x_i = n$ (all balls drawn are red), we have

$$
\begin{align*}
&\mathbb{P}(X_1 = x_1, X_2 = x_2, \cdots, X_n = x_n) \\ &= \frac{R_0(R_0+c)(R_0+2c)\cdots(R_0 + c(\sum x_i -1))}{(R_0+W_0)(R_0+W_0+c)(R_0+W_0+2c)\cdots(R_0+W_0+(n-1)c)}
\end{align*}
$$

and if $\sum x_i = 0$ (all balls drawn are white), we have

$$
\begin{align*}
&\mathbb{P}(X_1 = x_1, X_2 = x_2,\cdots X_n = x_n) \\ &=
\frac{W_0(W_0+c)(W_0+2c)\cdots(W_0+c(n - \sum x_i -1))}{(R_0+W_0) (R_0+W_0+c)(R_0+W_0+2c)\cdots(R_0+W_0+(n-1)c)}
\end{align*}
$$

If $0<\sum x_i < n$, we have

$$
\begin{align*}
&\mathbb{P}(X_1 = x, X_2 = x_2,\cdots, X_n = x_n) \\ &=
\frac{R_0(R_0+c)(R_0+2c)\cdots(R_0 + c(\sum x_i -1))\cdot W_0(W_0+c)(W_0+2c)\cdots(W_0+c(n - \sum x_i -1))}{(R_0+W_0)(R_0+W_0+c)(R_0+W_0+2c)\cdots(R_0+W_0+(n-1)c)}
\end{align*}
$$

In all cases, the probability is a function of $\sum x_i$ and not the individual positions of the $1$'s and $0$'s that make up the $x_i$, thus we say $X_1,X_2,\cdots, X_n$ are exchangeable.

**Example:** Let $X_1,X_2,\cdots,X_n$ be independent uniform $(0,1)$ random variables and denote their order statistics by $X_{(1)}, X_{(2)},\cdots,X_{(n)}$, that is $X_{(j)}$ is the $j$ th smallest of $X_1,X_2,\cdots, X_n$. Also denote $Y_1 = X_{(1)}, Y_i = X_{(i)} - X_{(i-1)}$, show that $Y_1, Y_2,\cdots,Y_n$ are exchangeable.\\

**Solution:** The transformations yield that

$$
x_i = y_1 + y_2 + \cdots + y_i
$$

and the Jacobian of this transformation is just $1$, so we have

$$
f_{Y_1,Y_2,\cdots,Y_n}(y_1,y_2,\cdots,y_n) = f(y_1,y_1+y_2,\cdots, y_1+y_2+\cdots +y_n)
$$

where $f$ is the joint density function of the order statistics, hence we have that 

$$
f_{Y_1,Y_2,\cdots,Y_n}(y_1,y_2,\cdots,y_n) = n!
$$

Because the preceding joint density is a symmetric function of $y_1,y_2,\cdots,y_n$, we see that the random variables are exchangeable.












