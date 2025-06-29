---
title: "Conditional Distributions"
collection: publications
category: probability
permalink: /publication/conditionaldistribution
excerpt: 'We will investigate conditional distributions'
date: 2024-09-30
order: 8
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Conditional Distributions'
---


# Conditioning by One Variable

Recall the conditional probability:

$$
\mathbb{P}(A \vert B) = \frac{\mathbb{P}(A \cap B)}{\mathbb{P}(B)}, \text{when $\mathbb{P}(B) >0$}.
$$

As another example, if we have two random variables $X,Y$ we may write 

$$
\mathbb{P}(X \in C \vert Y \in D) = \frac{\mathbb{P}(X \in C, Y \in D)}{\mathbb{P}(Y \in D)} , \text{where $C,D \in \mathbb{R}$}.
$$

Now suppose that we have a continuous random variable $X$, and we know that the event $X \in I =[a,b]$ has occurred. Call this event $A$, the conditional CDF of $X$ given $A$, denoted by $F_{X \vert A}(x)$ or $F_{X \vert a \leq X \leq b}(x)$ is given by

$$
\begin{align*}
F_{X \vert A}(x) &= \mathbb{P}( X \leq  \vert A)\\
&= \mathbb{P}( X \leq x \vert a \leq X \leq b)\\
&= \frac{\mathbb{P}(X \leq x, a \leq X \leq b)}{P(A)}
\end{align*}
$$

Now if $x<a$, then $F_{X \vert A}(x) = 0$, on the other hand, if $a \leq x \leq b$, we have

$$
\begin{align*}
F_{X \vert A}(x) &= \frac{\mathbb{P}(X \leq x, a \leq X \leq b)}{\mathbb{P}(A)} \\
&= \frac{\mathbb{P}(a \leq X \leq x)}{\mathbb{P}(A)} \\
&= \frac{F_X(x) - F_X(a)}{F_x(b) - F_X(a)}
\end{align*}
$$

And finally if $x>b$ then $F_{X \vert A}(x) = 1$, thus we obtain

$$
F_{X \vert A}(x) = 
\begin{cases}
1 : x>b \\
\\
\frac{F_X(x) - F_X(a)}{F_x(b) - F_X(a)} : a \leq x \leq b \\
\\
0 : \text{otherwise} 
\end{cases}
$$

We assume that $X$ is a continuous random variable, we do not need to be careful about the end points, to obtain the conditional PDF of $X$, we may simply differentiate $F_{X \vert A}(x)$, which gives

$$
f_{X \vert A}(x) = 
\begin{cases}
\frac{f_X(x)}{\mathbb{P}(A)} : a \leq x < b \\
\\
0 : \text{otherwise}
\end{cases}
$$

The conditional expectation and variance are defined by replacing the PDF by conditional PDF in the definitions of expectation and variance. In general for a random variable $x$ and an event $A$, we have the followings:


* $\displaystyle{\mathbb{E}[X \vert A] = \int_{-\infty}^{+\infty} x f_{X \vert A}(x) dx}$;

* $\displaystyle{\mathbb{E}[g(x) \vert A] = \int_{-\infty}^{+\infty} g(x) f_{X \vert A}(x) dx}$;

* $\displaystyle{\mathbf{Var}(X \vert A) = \mathbb{E}[X^2 \vert A] - (\mathbb{E}[X \vert A])^2}$.



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Let $X \sim Exponential(1)$, i.e

$$
f_X(x) = \begin{cases} \lambda e^{-\lambda x} : x \geq 0 \\ 0 : \text{otherwise} \end{cases}
$$

where $\lambda = 1$ in this case. Find : 1. The conditional PDF and CDF of $X$ given $X>1$; 2. $\mathbb{E}[X \vert X>1]$; 3. $\mathbf{Var}(X \vert X>1)$.

<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution:.</strong><br>
    1. : Let $A$ be the event that $X>1$, then
   
$$
\mathbb{P}(A) = \int_1^{+\infty} e^{-x} dx = \frac{1}{e}.
$$

thus

$$
f_{X \vert X>1}(x) = \begin{cases} e^{-x+1} : x>1 \\ 0 : \text{otherwise} \end{cases}
$$

and for $x>1$, we have

$$
F_{X \vert A}(A) = \frac{F_X(x) - F_X(1)}{\mathbb{P}(A)} = 1 - e^{-x+1}
$$

and $F_{X \vert A}(x) = 0$ otherwise.

<br>

2. : We have

 $$
\begin{align*}
\mathbb{E}[X \vert X>1] &= \int_1^{+\infty} x f_{X \vert X>1}(x) dx \\
&= \int_1^{+\infty} x e^{-x+1} dx \\
&=2.
\end{align*}
$$

<br>

3: We have

$$
\begin{align*}
\mathbb{E}[X^2 \vert X>1] &= \int_1^{+\infty} x^2 f_{X \vert X>1}(x) dx \\
& = \int_1^{+\infty} x^2 e^{-x+1} dx \\
= 5.
\end{align*}
$$

Thus

$$
\mathbf{Var}(X \vert X>1) = \mathbb{E}[X^2 \vert X>1] - (\mathbb{E}[X \vert X>1])^2 = 1.
$$
  </div>
</details>


</div>






# Discrete Conditional Distribution

Recall that for any two events $E,F$, the conditional probability of $E$ given $F$ is defined, provided that $\mathbb{P}(F)>0$ is that

$$
\mathbb{P} (E \vert F) = \frac{\mathbb{P}(EF)}{\mathbb{P} (F)}
$$

Hence, if $X,Y$ are discrete random variables, it's natural to define the conditional probability mass function of $X$ given that $Y = y$ by

$$
\begin{align*}
p_{X \vert Y}(x \vert y) &= \mathbb{P}\{ X = x \vert Y = y \} \\
&= \frac{\mathbb{P}\{ X = x, Y = y\}}{\mathbb{P} \{ Y = y \}} \\
& = \frac{p(x,y)}{p_Y(y)}
\end{align*}
$$

Similarly, the conditional probability distribution function given that $Y = y$ is defined, for all $y$ such that $p_Y(y) >0$ by

$$
F_{X \vert Y} (x \vert y) = \mathbb{P} \{ X \leq x \vert Y = y \} = \sum_{a \leq x} p_{X \vert Y}(a \vert y)
$$

In other words, the definitions are exactly the same as in the unconditional case, except that everything is not conditional on the event that $Y=y$. If $X$ is independent of $Y$, then the conditional mass function and the distribution function are the same as the respective unconditional ones. This follows because if $X$ is independent of $Y$, then we have

$$
\begin{align*}
p_{X\vert Y}(x \vert y) &= \mathbb{P}\{ X = x \vert Y = y\}\\
&= \frac{\mathbb{P}\{ X = x , Y = y\}}{\mathbb{P}\{ Y=y\}}\\
&= \frac{\mathbb{P}\{ X =x \} \mathbb{P}\{ Y = y \}}{\mathbb{P} \{ Y = y\}}\\
& = \mathbb{P}\{ X = x\}.
\end{align*}
$$

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Suppose that $p(x,y)$, the joint probability mass function of $X$ and $Y$, is given by

$$
p(0,0) = 0.4 , p(0,1) = 2,p(1,0) = 0.1,p(1,1) = 0.3
$$

Then find the conditional probability mass function of $X$ given that $Y = 1$.


<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    We first note that

$$
p_Y(1) = \sum_x p(x,1) = p(0,1) + p(1,1) = 0.5
$$

Hence

$$
p_{x\vert Y}(x \vert y)= \frac{p(1,1)}{p_Y(1)} = \frac{2}{5}
$$

and

$$
p_{X \vert Y}(1\vert 1) = \frac{p(1,1)}{p_Y(1)} = \frac{3}{5}.
$$

  </div>
</details>

</div>






<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  If $X,Y$ are independent Poisson random variables with respective parameters $\lambda_1$ and $\lambda_2$, calculate the conditional distribution of $X$ given that $X+Y = n$.


  <details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>

We calculate the conditional probability mass function of $X$ given that $X+Y =n$ as follows:

$$
\begin{align*}
\mathbb{P}\{ X = k \vert X+Y =n \} &= \frac{\mathbb{P}\{ X =k, X + Y = n\}}{\mathbb{P} \{ X + Y +n \}} \\
&= \frac{\mathbb{P}\{ X = k, Y = n - k\}}{\mathbb{P}\{ X+Y = n\}}\\
&= \frac{\mathbb{P}\{ X =k\} \mathbb{P}\{ Y = n -k \}}{\mathbb{P}\{ X + Y =n \}}.
\end{align*}
$$
    Recall that $X + Y$ has a Poisson distribution with parameter $\lambda_1+\lambda_2$, we see that the preceding equals

$$
\begin{align*}
\mathbb{P}\{ X = k \vert X + Y =n \} &= \frac{e^{-\lambda_1} \lambda_1^k}{k!} \frac{e^{-\lambda_2} \lambda_2^{n-2}}{(n-k)!} \left[ \frac{e^{-(\lambda_1+\lambda_2)}(\lambda_1+\lambda_2)^n}{n!} \right]^{-1} \\
&= \frac{n!}{(n-k)!k!} \frac{\lambda_1^k \lambda_2^{n-k}}{(\lambda_1+\lambda_2)^n} \\
&= \binom{n}{k} \left( \frac{\lambda_1}{\lambda_1+\lambda_2} \right)^k \left( \frac{\lambda_2}{\lambda_1+\lambda_2} \right)^{n-k}.
\end{align*}
$$

In other words, the conditional distribution of $X$ given that $X+Y=n$ is the binomial distribution with parameters $n$ and $\lambda_1 / (\lambda_1+\lambda_2)$.
  </div>
</details>

</div>


 




<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Consider $n$ independent trails, with each trail being a success with a probability $p$. Given a total of $k$ success, show that all possible orderings of the $k$ successes and $n-k$ failures are equally likely.


  <details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    We want to show that given a total of $k$ success, each of the $\binom{n}{k}$ possible orderings of $k$ success and $n-k$ failures is equally likely. Let $X$ denote the number of successes, and consider any ordering of $k$ success and $n-k$ failures, say $\vec o = (s,s,f,f,\cdots,f)$, then

$$
\begin{align*}
\mathbb{P}\{ \vec o \vert  X= K ) &= \frac{\mathbb{P}\{ \vec o , X = k \}}{\mathbb{P}\{ X =k\}} \\
&= \frac{\mathbb{P}(\vec o)}{\mathbb{P}\{X=k\}}\\
&= \frac{p^k(1-p)^{n-k}}{\binom{n}{k} p^k (1-p)^{n-k}}\\
& = \frac{1}{\binom{n}{k}}.
\end{align*}
$$
  </div>
</details>
</div>





<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Consider two random variables $X$ and $Y$ with joint probability mass function given below:





Find : (a) $\mathbb{P}\{ X \leq 2, Y \leq 4\}$ ; (b) The marginal probability mass functions of $X$ and $Y$; (c) $\mathbb{P}\{ Y =2 \vert X =1\}$ ; (d) Are $X,Y$ independent?

 <details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    (a) : By definition, we have

$$
\begin{align*}
\mathbb{P}\{ X \leq 2, Y \leq 4 \} &= \sum_{i \leq 2, j \leq 4} \mathbb{P}\{ X = i, Y = j\} \\
& = p_{12} + p_{14} + p_{22} +p_{24} \\
&= \frac{1}{12} + \frac{1}{24} + \frac{1}{6} + \frac{1}{12} \\
&= \frac{3}{8}.
\end{align*}
$$

(b) : The marginal pmf of $X$ is given by:

$$
\begin{align*}
p_{1 \cdot} &= p_{12} + p_{14} + p_{15} = \frac{1}{12} + \frac{1}{24} + \frac{1}{24} = \frac{4}{24} \\
p_{2 \cdot} &= p_{22} + p_{24} + p_{25} = \frac{1}{6} + \frac{1}{12} + \frac{1}{8} = \frac{9}{24} \\
p_{3 \cdot} &= p_{32} + p_{34} + p_{35} = \frac{1}{4} + \frac{1}{8} + \frac{1}{12} = \frac{12}{24}
\end{align*}
$$

and thus we have

$$
f_X(x) = \begin{cases}
\frac{4}{24} : X=1 \\ \frac{9}{24} : X =2 \\ \frac{12}{24} : X = 3 \\ 0 : \text{otherwise} \end{cases}
$$

Same idea may be applied on $Y$, The marginal pmf of $X$ is given by:

$$
\begin{align*}
p_{\cdot 2} &= p_{12} + p_{22} + p_{32} = \frac{1}{12} + \frac{1}{6} + \frac{1}{4} = \frac{12}{24} \\
p_{\cdot 4} &= p_{14} + p_{24} + p_{34} = \frac{1}{24} + \frac{1}{12} + \frac{1}{8} = \frac{6}{24} \\
p_{\cdot 5} &= p_{15} + p_{25} + p_{35} = \frac{1}{24} + \frac{1}{8} + \frac{1}{12} = \frac{6}{24}
\end{align*}
$$

and thus we have

$$
f_Y(y) = \begin{cases}
\frac{12}{24} : Y=2 \\ \frac{6}{24} : Y =4 \\ \frac{6}{24} : Y=5 \\ 0 : \text{otherwise} \end{cases}
$$


(c) : By definition, we have

$$
\begin{align*}
\mathbb{P}\{ Y = 2 \vert X=1 \} &= \frac{\mathbb{P}\{ X =1, Y=2\}}{\mathbb{P}\{ X=1\}}\\
&= \frac{p_{12}}{p_{1 \cdot}} \\
&= \frac{\frac{1}{12}}{\frac{1}{6}}\\
&= \frac{1}{2}.
\end{align*}
$$

(d) : To check that whether $X,Y$ are independent, we need to check

$$
\mathbb{P}\{X = x, Y=y \} = \mathbb{P}\{ X = x\} \mathbb{P}\{ Y = y\} \hspace{2cm} (*)
$$

For all possible pairs of $X,Y$. We find that

$$
\mathbb{P}\{ X = 2, Y = 2\} = \frac{1}{6}
$$

But

$$
\mathbb{P}\{ X = 2 \} \mathbb{P}\{ Y=2\} = \frac{3}{8} \times \frac{1}{2} = \frac{3}{16}
$$

Which means this pair does not satisfy equation $(*)$, thus they are not independent.
  </div>
</details>


</div>


|           | $Y=2$           | $Y=4$           | $Y=5$           |
|-----------|-----------------|-----------------|-----------------|
| $X=1$     | $\frac{1}{12}$  | $\frac{1}{24}$  | $\frac{1}{24}$  |
| $X=2$     | $\frac{1}{6}$   | $\frac{1}{12}$  | $\frac{1}{8}$   |
| $X=3$     | $\frac{1}{4}$   | $\frac{1}{8}$   | $\frac{1}{12}$  |
 




<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Suppose that the number of customers visiting a fast food restaurant in a given day is $N \sim Poisson(\lambda)$. Further assume that each customer purchases a drink with probability $p$, independently from other customers and independently from the value $N$. Let $X$ be the number of customers who purchase drinks, let $Y$ be the number of customer that do not purchase drinks, so $X+Y = N$. Find : (a) The marginal PMFs of $X$ and $Y$; (b) The joint PMF of $X$ and $Y$; (c) Are $X$ and $Y$ independent? (d) Find $\mathbb{E}[X^2 Y^2]$.

  <details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
   (a) : Based on what we are given, clearly

$$
X \vert (N = n) \sim Binomial(n,p) ; Y \vert (N = n) \sim Binomial(n,1-p)
$$

Then by the law of total probability, we have

$$
\begin{align*}
\mathbb{P}_X(k) &= \sum_{n=0}^{+\infty} \mathbb{P}\{ X = k \vert N = n \} \mathbb{P}_N(n)\\
&= \sum_{n=k}^{+\infty} \binom{n}{k} p^k (1-p)^{n-k} \exp(-\lambda) \frac{\lambda^n}{n!}\\
&= \sum_{n=k}^{+\infty} \frac{p^k(1-p)^{n-k} \exp(-\lambda) \lambda^n}{k!(n-k)!}\\
& = \frac{\exp(-\lambda) (\lambda p)^k}{k!} \sum_{n=k}^{+\infty} \frac{(\lambda(1-p))^{n-k}}{(n-k)!} \\
& = \frac{\exp(-\lambda) (\lambda p)^k}{k!} \exp(\lambda (1-p)) \\
& = \frac{\exp(-\lambda p)(\lambda p)^k}{k!}, \text{for $k=0,1,2,\cdots$}
\end{align*}
$$

and thus we conclude that

$$
X \sim Poisson(\lambda p) ; Y \sim Poisson(\lambda(1-p))
$$
  </div>
</details>

 
</div>






<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Suppose tossing a coin with $\mathbb{P}(H) = p$, repeatedly toss the coin until there are two consecutive heads. Let $X$ denote the total number of coin tosses, find $\mathbb{E} X$.

  <details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    Suppose $\mathbb{E} X = \mu$, we first condition on the result of the first toss, then

$$
\mu = \mathbb{E} X = \mathbb{E}[ X \vert H] \mathbb{P}(H) + \mathbb{E}[X \vert T]\mathbb{P}(T) = \mathbb{E}[X \vert H] p + (1+\mu)(1-p).
$$

Since geometric distribution is "memoryless", i.e $\mathbb{E} X$ should be a fixed value regardless of the number of fails it gave. So if the first toss is a tail, it is then considered as a "fail" and start over again, but the number of trails increase by $1$, however $\mathbb{E} X$ is still fixed. So that's why we have $\mathbb{E} (X \vert H) = 1 +\mathbb{E} X$, and we get

$$
p \mathbb{E} X = \mathbb{E}[ X \vert H] p + 1-p \hspace{1cm} (*)
$$

Then, in order to find $\mathbb{E}[X \vert H]$, we condition on the second trail:

$$
\begin{align*}
\mathbb{E} [X \vert H ] &= \mathbb{E} [ X \vert HH] \mathbb{P}(H) + \mathbb{E}[ X \vert HT] \mathbb{P}(T)\\
&= \underbrace{\mathbb{E}[X \vert HH]}_\text{success with 2 tosses} \cdot p + \underbrace{\mathbb{E}[ X \vert HT]}_\text{a fail} (1-p) \hspace{1cm} (**)\\
& = 2p + (2 +\mathbb{E} X)(1-p) = 2 + (1-p) \mathbb{E} X
\end{align*}
$$

Now combine equations $(*),(**)$, we have

$$
p\mathbb{E} X =  ( 2p + ( 2+ \mathbb{E} X)(1-p)) p + 1-p 
$$

Thus

$$
\mathbb{E} X = \frac{1+p}{p^2}.
$$

  </div>
</details>

</div>
 


 


# Continuous Conditional Distribution

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> If $X,Y$ have a joint probability density function $f(x,y)$, then the conditional probability density function of $X$ given that $Y =y$ is defined, for all values of $y$ such that $f_Y(y)>0$, by

$$
f_{X \vert Y}(x \vert y)=\frac{f(x,y)}{f_Y(y)}
$$
</div>




We may multiply the left-hand-side by $dx$ and the right hand side by $(dx dy) / dy$ and we will get

$$
\begin{align*}
f_{X \vert Y}(x \vert y) dx &= \frac{f(x,y) dxdy}{f_Y(y) dy} \\
&\approx \frac{\mathbb{P}\{ x \leq X \leq x+ dx , y \leq Y \leq y+dy\}}{\mathbb{P}\{ y \leq Y \leq y+dy \}}\\
& = \mathbb{P}\{ x \leq X \leq x+ dx \vert y \leq Y \leq y+dy \}
\end{align*}
$$


The use of conditional densities allows us to define conditional probabilities of events associated with one random variable when we are given the value of a second random variable. That is, if $X$ and $Y$ are jointly continuous, then for any set $A$,

$$
\mathbb{P}\{ X \in A \vert Y = y \} = \int_A f_{X \vert Y}(x \vert y) dx
$$

In particular, by letting $A  =(-\infty,a]$, we can define the conditional cumulative distribution function of $X$ given that $Y=y$ by

$$
F_{X \vert Y}(a \vert y) \equiv \mathbb{P}\{ X \leq a \vert Y = y\} = \int_{-\infty}^a f_{X \vert Y}(x \vert y)d x
$$

For two jointly continuous random variables $X,Y$, we can define the following conditional concepts:


**Properties of Jointly Conditional Distribution:**

* The marginal distribution of $y$, denoted by $f_Y(y)$ is given by
  
$$
f_Y(y) = \int_{-\infty}^{+\infty} f_{X.Y}(x,y) dx
$$


* The conditional PDF of $X$ given $Y=y$:
  
$$
f_{X \vert Y}(x \vert y) = \frac{f_{XY}(x,y)}{f_Y(y)}
$$

* The conditional probability that $X \in A$ given $Y = y$:
  
$$
\mathbb{P}\{X \in A \vert Y = y\} = \int_A f_{X \vert Y} (x \vert y) dx
$$

* The conditional CDF of $X$ given $Y =y$:
  
$$
F_{X \vert Y}(x \vert y)= \mathbb{P}\{ X \leq x \vert Y = y\} = \int_{-\infty}^x f_{X \vert Y}(x \vert y) dx
$$

* The expected value of $x$ given $Y=y$:
  
$$
\mathbb{E}[X \vert Y=y] = \int_{-\infty}^{+\infty} x f_{X \vert Y}(x\vert y)dx
$$

* Conditional LOTUS:
  
$$
\mathbb{E}[g(x) \vert Y = y] = \int_{-\infty}^{+\infty} g(x) f_{X \vert Y}(x\vert y) dx
$$

* Conditional variance of $X$ given $Y=y$:
  
$$
\mathbf{Var}(X \vert Y=y) = \mathbb{E}[X^2 \vert Y=y] - (\mathbb{E}[X \vert Y=y])^2
$$




<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Let $X,Y$ be jointly distributed as 

$$
f_{XY}(x,y) = \begin{cases} \frac{x^2}{4} + \frac{y^2}{6} + \frac{xy}{6} : 0\leq x \leq 1, 0 \leq y \leq 2 \\ \\ 0 :\text{otherwise} \end{cases}
$$

Find : 1.The conditional PDF of $X$ given $Y = y$ where $0 \leq y \leq 2$; 2. $\mathbb{P}\{ X < 0.5 \vert Y = y \}$ ; 3. $\mathbb{E}[X \vert Y=1]$; 4. $\mathbf{Var}(X \vert Y=1)$.


<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    1: We first compute $f_Y(y)$, given by
   
$$
f_Y(y) = \int_{-\infty}^{+\infty} f_{X,Y}(x,y) dx = \int_{0}^1 \frac{x^2}{4} + \frac{y^2}{4} + \frac{xy}{6} dx = \frac{1}{12} + \frac{y^2}{4} + \frac{y}{12}.
$$

Then we know that

$$
\begin{align*}
f_{X \vert Y}(x,y) &= \frac{f_{XY}(x,y)}{f_Y(y)} \\
& = \frac{\frac{x^2}{4} + \frac{y^2}{4} + \frac{xy}{6}}{\frac{1}{12} + \frac{y^2}{4} + \frac{y}{12}} \\
&= \frac{3x^2 + 3y^2 + 2xy}{3y^2+y+1}
\end{align*}
$$

and thus for $0 \leq y \leq 2$ we obtain

$$
f_{X \vert Y}(x \vert y) = \begin{cases}
\frac{3x^2 + 3y^2 + 2xy}{3y^2+y+1} : 0 \leq x \leq 1\\ \\ 0 : \text{otherwise} \end{cases}
$$

2: We have

$$
\begin{align*}
\mathbb{P}\left( X < \frac{1}{2} \Bigg\vert Y=y \right) &= \int_0^{\frac{1}{2}} \frac{3x^2+3y^2+2xy}{3y^2+y+1}dx\\
&= \frac{\frac{3}{2} y^2 + \frac{y}{4} + \frac{1}{8}}{3y^2 + y+1}.
\end{align*}
$$

3: We have

$$
\begin{align*}
\mathbb{E}[X \vert Y=1] &= \int_{\infty}^{+\infty} x f_{X\vert Y}(x \vert y=1) dx \\
& = \int_0^1 x \frac{3x^2 + 3y^2+2xy}{3y^2+y+1} \Bigg\vert_{y=1} dx \\
&= \int_{0}^1 x \frac{3x^2+3+2x}{3+1+1} dx \\
& = \frac{1}{5} \int_0^1 (3x^3 + 2x^2 + 3x )dx \\
&= \frac{7}{12}.
\end{align*}
$$

4: We have

$$
\begin{align*}
\mathbb{E}[ X^2 \vert y=1] &= \int_{-\infty}^{+\infty} x^2 f_{X\vert Y}(x \vert y=1) dx \\
& = \frac{1}{5} \int_0^1 (3x^4 + 2x^3 + 3x^2 )dx \\
&= \frac{21}{50}.
\end{align*}
$$

So we have

$$
\begin{align*}
\mathbf{Var}(X \vert Y=1) &= \mathbb{E}[X^2 \vert Y=1 ] - (\mathbb{E}[X \vert Y=1])^2\\
&= \frac{21}{50} - \left(\frac{7}{12} \right)^2 \\
&= \frac{287}{3600}.
\end{align*}
$$

  </div>
</details>


</div>
 



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  The joint density function of $X$ and $Y$ is given by

$$
f(x,y) = \begin{cases} x(2-x-y) : (x,y) \in (0,1)^2 \\ 0 : \text{otherwise} \end{cases}
$$

Compute the conditional density of $X$ given that $Y  =y$, $0<y<1$.


<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    For $(x,y) \in (0,1)^2$, we have

$$
\begin{align*}
f_{X \vert Y}(x \vert y) &= \frac{f(x,y)}{f_Y(y)}\\
& = \frac{f(x,y)}{\int_{-\infty}^{+\infty} f(x,y) dx} \\
&=\frac{x(2-x-y)}{\int_0^1 x(2-x-y) dx} \\
& = \frac{x(2-x-y)}{\frac{2}{3} - \frac{y}{2}}\\
& = \frac{6x(2-x-y)}{4-3y}.
\end{align*}
$$

**Example:** Suppose that the joint density of $X$ and $Y$ is given by

$$
f(x,y) = \begin{cases} \frac{e^{-x/y} e^{-y}}{y} : (x,y) \in (0,+\infty)^2 \\ 0 : \text{otherwise} \end{cases}
$$

Find $\mathbb{P} \{ X>1 \vert Y =y \}$.

**Solution:**  We obtain the conditional density of $X$ given that $Y=y$:

$$
\begin{align*}
f_{X \vert Y}(x \vert y) &= \frac{f(x,y)}{f_Y(y)}\\
&= \frac{e^{-x/y} e^{-y}/y}{e^{-y} \int_0^{+\infty} (1/y)e^{-x/y} dx} \\
&= \frac{1}{y} e^{-x/y}
\end{align*}
$$

Hence,

$$
\begin{align*}
\mathbb{P}\{ X >1 \vert Y = y \} &= \int_1^{+\infty} \frac{1}{y} e^{-x/y} dx \\
&= -e^{-x/y} \Bigg\vert_1^{+\infty}\\
&= e^{-1/y}.
\end{align*}
$$

If $X$ and $Y$ are independent continuous random variables, the conditional density of $X$ given that $Y=y$ is just the unconditional density of $X$. 

  </div>
</details>

</div>


 
