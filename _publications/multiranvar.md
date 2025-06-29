---
title: "Multiple and Independent Random Variables"
collection: publications
category: probability
permalink: /publication/multiranvar
excerpt: 'We will investigate multiple random variables and independent random variables'
date: 2024-09-25
order: 7
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Multiple and Independent Random Variables'
---

# Multiple Random Variables


<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> The vector $\mathbf{X} = (X_1,X_2,\cdots,X_n)$ defined on $(\Omega,\mathcal{F},\mathbb{P})$ into $\mathbb{R}^n$ by

$$
\mathbf{X}(\omega) = \{ X_1(\omega),X_2(\omega),\cdots,X_n(\omega) \}, \omega \in \Omega
$$

is called an $n$-dimensional random variable if the inverse image of every $n$-dimensional interval is also in $\mathcal{F}$.



Let $\mathbf{X} = (X_1,X_2,\cdots,X_n)$ be a vector of random variables, and $\vec x = (x_1,x_2,\cdots,x_n)$, we define

$$
F_{\mathbf{X}}(\vec x) = \mathbb{P}\{ X_1 \leq x_1 ; X_2 \leq x_2; \cdots; X_n \leq x_n \}
$$

</div>




And we claim the following properties:

* $F_{\mathbf{X}}$ is non-decreasing in every argument $x_1,x_2,\cdots,x_n$;

* $F_{\mathbf{X}}$ is right continuous in all arguments $x_1,x_2,\cdots,x_n$;

* $F_{\mathbf{X}} (-\infty,x_2,\cdots,x_n) = F_{\mathbf{X}} (x_1,-\infty,x_3,\cdots,x_n) = \cdots = 0$;

* $F_{\mathbf{X}} (+\infty,+\infty,\cdots,+\infty) = 1$;

* Let $n=2$, $\forall \epsilon_1,\epsilon_2 >0$, we have
 
$$
F_{\mathbf{X}} (x_1 + \epsilon , x_2 + \epsilon) - F_{\mathbf{X}}(x_1+\epsilon,x_2) - F_{\mathbf{X}} (x_1,x_2+\epsilon_2) + F_{\mathbf{X}}(x_1,x_2) \geq 0
$$

This idea can also be generalized for $n\geq 2$.

For better notation and simplification, we will discuss the case when $n=2$ from now on.



<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> A $2$-dimensional random variable $(X,Y)$ is said to be of the discrete type if it takes on pairs of values belonging to a countable set $A$ with probability $1$. We define $ p_{ij} = (x_i,y_j)$ for every pair, and define

$$
p_{ij} = \mathbb{P}\{ X = x_i ; Y = y_j \}
$$

to be the joint probability mass function of $(X,Y)$, the distribution function is given by

$$
F(x,y) = \sum_{(i,j) \in B} p_{ij}, \hspace{0.2cm} B = \{ (i,j) : x_i \leq x; y_j \leq y \}
$$

</div>



We also give the definition for the continuous type:

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> A $2$-dimensional random variable $(X,Y)$ is said to be of the continuous type if there exists a non-negative function $f$, such that for every pair $(x,y) \in \mathbb{R}^2$, we have

$$
F(x,y) = \int_{-\infty}^x \int_{-\infty}^y f(x,y) dudv
$$

where $F(x,y)$ is the distribution function of $(X,Y)$ and $f$ is the joint probability density function of $(X,Y)$.
</div>



We know that $f(x,y) \geq 0$, also

$$
\int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(x,y) dudv = 1
$$

And in particular if $f$ is twice continuous at $(x,y)$, then we have

$$
\frac{\partial^2 F(x,y)}{\partial x \partial y} = f(x,y)
$$



<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> If $f$ is a non-negative function satisfying $\displaystyle{\int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(x,y) dxdy = 1}$, then $f$ is the joint probability density function for some random variable.
</div>



Suppose a $2$-dimensional random variable $(X,Y)$, assume it is of the continuous type, then we define

$$
F_1(x) = \mathbb{P}(X_1 \leq x) = F(x,+\infty) = \lim_{y \to \infty} F(x,y)
$$

and

$$
\lim_{y \to \infty} F(x,y) = \lim_{y \to \infty} \mathbb{P} \{ X \leq x, Y \leq y \}.
$$

Likewise,

$$
F_2(y) = F(+\infty,y) = \lim_{x \to \infty} F(x,y)
$$

and

$$
\lim_{x \to \infty} F(x,y) = \lim_{x \to \infty} \mathbb{P}\{ X \leq x , Y \leq y \}
$$

Also we have

$$
f_1(x) = \int_{-\infty}^{+\infty} f(x,y) dy ; f_2(y) = \int_{-\infty}^{+\infty} f(x,y) dx
$$

We have $f_1(x), f_2(y) \geq 0$, and $f_1(x)$ is called the marginal probability density function of $X$, and $f_2(y)$ is called the marginal probability density function of $Y$.

Now for discrete type, assume $X = \{ x_1,x_2,\cdots \}, Y = \{ y_1,y_2,\cdots \}$, then

$$
F(x ,+\infty) = \sum \sum_{(i,j)\in B} p_{ij}, \hspace{0.2cm} B = \{ (i,j) : X_i \leq x , y_j \leq +\infty \}
$$

$$
f_1(x_i) = \mathbb{P}(X = x_i) = \sum_{j=1}^{+\infty} \mathbb{P}(X = x_i), Y = y_j) = \sum_{j=1}^{+\infty} p_{ij} = p_{i \cdot}
$$

Likewise,

$$
f_2(y_j) = \mathbb{P}(Y = y_j) = \sum_{i=1}^{+\infty} p_{ij} = p_{\cdot j}
$$

Likewise, $p_{i \cdot}$ is called the marginal probability mass function of $X$, and $p_{\cdot j}$ is called the marginal probability mass function of $Y$.


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong> Consider a circle of radius $R$ centered at the origin. A point is randomly chosen on the circle, and we say the the point is uniformly distributed within the circle. That is, assume the point has coordinates $(x,y)$, then the joint distribution of the random variable $X,Y$ is given by

$$
f_{X,Y}(x,y) = \begin{cases} \frac{1}{\pi R^2} : x^2 + y^2 \leq R^2 \\ 0: \text{otherwise} \end{cases}
$$

Compute the marginal density functions of $X,Y$; compute the probability that $D$, the distance from the origin of the point selected, is less than or equal to $a$, where $a$ is a given constant. Finally find $\mathbb{E}(D)$.



<br>


<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
     The marginal distribution of $X$ is given by

$$
\begin{align*}
f_X(x) &= \int_{-\infty}^{+\infty} \frac{1}{\pi R^2} dy \\
& = \frac{1}{\pi R^2} \int_{-\sqrt{R^2-x^2}}^{\sqrt{R^2-x^2}} dy \\
& = \frac{2}{\pi R^2} \sqrt{R^2 - x^2}, \text{where $x^2 \leq R^2$}.
\end{align*}
$$

and is equal to $0$ otherwise. Likewise, we have

$$
f_Y(y) = \frac{2}{\pi R^2} \sqrt{R^2 - y^2}, \text{where $y^2 \leq R^2$}.
$$

and is equal to $0$ otherwise.

Since the distace is always non-negative, thus we have

$$
\begin{align*}
\mathbb{P}\{  \sqrt{X^2 + Y^2} \leq a \} &= \mathbb{P}\{ X^2 + Y^2 \leq a^2 \} \\
&= \iint_{x^2 + y^2 \leq a^2} f(x,y) dxdy\\
& = \frac{1}{\pi R^2} \iint_{x^2+y^2 \leq a^2} dxdy\\
& = \frac{\pi a^2}{\pi R^2} \\
& = \left( \frac{a}{R} \right)^2.
\end{align*}
$$

So we know that $F_D(a) := \frac{a^2}{R^2}$, so

$$
f_D(a) = \frac{2a}{R^2}, 0 \leq a \leq R
$$

Hence

$$
\mathbb{E} D = \frac{2}{R^2} \int_0^R a^2 da = \frac{2R}{3}
$$

  </div>
</details>


</div>
 



Suppose $(X,Y)$ be jointly distributed with joint probability density function given by $f(x,y) = 2, 0<x<y<1$, and $f(x,y) = 0$ otherwise. Then we have

$$
f_1(x) = \int_x^1 2 dy = \begin{cases} 2-2x, 0<x<1 \\ 0,\text{otherwise} \end{cases}
$$

$$
f_2(y)  = \int_0^y 2 dx = \begin{cases} 2y, 0<y<1 \\ 0, \text{otherwise} \end{cases}
$$




<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Let $(X,Y)$ be a random variable of the discrete type, if $\mathbb{P}(Y = y_j) >0$, the function

$$
p_{i \vert j} = \mathbb{P}(X = x_i \vert Y = y_j) = \frac{\mathbb{P}(X=x_i, Y = y_j)}{\mathbb{P}(Y = y_j)}
$$

for a fixed $j$ is known as the conditional probability mass function of $X$ given $Y = y_j$, a similar definition can also be given on $Y$
for a fixed $x_i$
</div>



By definition, we also have

$$
p_{i \vert j} = \frac{p_{ij}}{p_{\cdot j}}
$$

$$
F_{X \vert Y} (x,y) = \mathbb{P}(X \leq x \vert Y = y) = \frac{\mathbb{P}(X \leq x, Y = y)}{\mathbb{P}(Y=y)}
$$

For a continuous random variable, we have

$$
\begin{align*}
F_{X \vert Y} (x \vert y) &= \mathbb{P} (X \leq x \vert Y = y) \\
& = \lim_{\epsilon \to 0+} \mathbb{P} (X \leq x \vert Y \in (y - \epsilon, y + \epsilon)) \\
& = \lim_{\epsilon \to 0+} \frac{\mathbb{P}(X \leq x , Y \in (y-\epsilon, y+\epsilon))}{\mathbb{P}(Y \in (y - \epsilon, y+\epsilon))}\\
& = \lim_{\epsilon \to 0+} \left(  \frac{\displaystyle{\int_{-\infty}^x \int_{y-\epsilon}^{y+\epsilon} f(u,v) dudv}}{\displaystyle{\int_{y-\epsilon}^{y+\epsilon} f_2(v) dv}} \right)\\
& = \frac{\displaystyle{\int_{-\infty}^x f(u,y) du}}{f_2(y)} = 
\int_{-\infty}^x \frac{f(u,y)}{f_2(y)}du
\end{align*}
$$

and thus

$$
f_{X \vert Y} (x,y) = \frac{f(x,y)}{f_2(y)}
$$

is called the conditional probability density function of the random variable of the continuous type.



<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> he conditional probability distribution function for a random variable of the continuous type $X$ given $Y =y$ is given by

$$
F_{X \vert Y} (x \vert y) = \lim_{\epsilon \to 0^+} \mathbb{P}\{ X \leq x \vert Y \in (y-\epsilon,y+\epsilon] \}
$$
</div>




<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $f$ be the joint probability density function of a random variable $(X,Y)$ of the continuous type. Let $f_2(y)$ be the marginal probability density function of $Y$. At every point $(x,y)$ which $f$ is continuous and $f_2(Y) >0$ and also continuous, the conditional probability density function of $X$ given $Y = y$ is given by

$$
f_{X \vert Y}(x \vert y) = \frac{f(x,y)}{f_2(y)}
$$

and the same idea applies for $f_{Y \vert X}(y \vert x)$.
</div>




Note that 

$$
\int_{-\infty}^x f(u,y) du = f_2(y) F_{X \vert Y}(x \vert y)
$$

so we have

$$
F_1(x) = \int_{-\infty}^{+\infty} \left[ \int_{-\infty}^x f(u,y) du \right] dy = \int_{-\infty}^{+\infty} f_2(y) F_{X \vert Y}(x \vert y) dy
$$

where $F_1(x)$ is the marginal distribution function of $X$.



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Consider random variable $(X,Y)$ which has a joint distribution function given by

$$
f(x,y) = \begin{cases} 2, 0<x<y<1 \\ 0, \text{otherwise} \end{cases}
$$

Then we can find

$$
f_{Y \vert X}(y \vert x) = \frac{f(x,y)}{f_1(x)} = \frac{1}{1-x}, \hspace{0.2cm} x<y<1
$$

also

$$
f_{X \vert Y}(x \vert y) = \frac{f(x,y)}{f_2(x)} = \frac{1}{y}, \hspace{0.2cm} 0<x<y
$$

Now we also need to care about the bounds, since they might be tricky:

$$
\mathbb{P} \left\{ Y \geq \frac{1}{2} \Bigg\vert x = \frac{1}{2} \right\} = \int_{\frac{1}{2}}^1 \frac{1}{1 - \frac{1}{2}} dy = 1
$$

$$
\mathbb{P}\left\{ X \geq \frac{1}{3} \Bigg\vert y = \frac{2}{3} \right\} = \int_{\frac{1}{3}}^{\frac{2}{3}} \frac{1}{\frac{2}{3}}dx = \frac{1}{2}.
$$
</div>



# Independent Random Variables

<div style="background-color: #cceeff; padding: 1em; border-left: 6px solid #3399cc; border-radius: 8px; margin: 1em 0;">
  <strong>Definition.</strong> Given $X = \{ x_1,x_2,\cdots\}, Y = \{ x_1, x_2,\cdots \}$, we say that $X,Y$ are independent, if 

$$
\mathbb{P}(X = x_i , Y = y_j ) = \mathbb{P}(X = x_i) \mathbb{P}(Y = y_j)
$$

for all $x_i \in X ,y_j \in Y$.


We can also say that $X,Y$ are independent if and only if

$$
F(x,y) = F_1(x) F_2(y) \hspace{0.2cm} \text{for all $(x,y) \in \mathbb{R}^2$}
$$
</div>



<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Let $X,Y$ be independent random variables, then we have $F_{Y \vert X}(y \vert x) = F_Y(y)$ for all $y$ and $F_{X \vert Y}(x \vert y) = F_X(x)$ for all $x$.
</div>




<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  A man and a woman decide to meet at a certain location. If each of them independently arrives at a time uniformly distributed between 12 noon and 1 P.M., find the probability that the first to arrive has to wait longer than 10 minutes


 <br>

  <details style="margin-top: 1em;">
    <summary style="font-weight: bold; color: #444; cursor: pointer;">Click to show/hide solution</summary>
    <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
      <strong>Solution.</strong><br>
       If we let $X,Y$ denote, respectively the time past $12$ that the man an the woman arrive, then $X,Y$ are independent random variables and each of which is uniformly distributed over $[0,60]$. The desired probability is given by

$$
\mathbb{P}\{ X + 10 < Y \} + \mathbb{P}\{ Y + 10 < X\}
$$

And by symmetry, is just $2\mathbb{P}\{ X + 10 < Y\}$, thus we have

$$
\begin{align*}
2\mathbb{P}\{ X+10<Y\} &= 2 \iint_{x+10<y} f(x,y) dxdy \\
&= 2 \iint_{x+10<y} f_X(x) f_Y(y) dxdy\\
& = 2 \int_{10}^{60} \int_{0}^{y-10} \left( \frac{1}{60} \right)^2 dxdy\\
& = \frac{25}{36}.
\end{align*}
$$
    </div>
  </details>
</div>




<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example. (Buffon's Needle Problem).</strong> A table is ruled with equidistant parallel lines with a distance $D$ apart. A needle of length $L$ where $L \leq D$ is randomly thrown on the table. What is the probability that the needle will intersect one of the lines (the other probability will be that the needle will be completely contained in the strip between two lines)?

  <br>

  <div style="text-align: center;">
  <img src="/images/buffon.png" alt="McGill" width="400">
  <p><em>Figure: The Buffon's neddle problem</em></p>
</div>


<br>

<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
   Let $X$ be the distance from the middle point of the needle to the nearest parallel line, and $\theta$ be the angle of the needle and the projected line of length $X$. Then by the construction, the needle will intersect the line if and only if

$$
\frac{X}{\cos(\theta)} < \frac{L}{2}
$$


And we see that $X \in [0,D/2]$ and $\theta \in [0,\pi/2]$, so we may assume that they are independent, and uniformly distributed throughout their ranges, hence we have

$$
\begin{align*}
\mathbb{P} \left\{ X < \frac{L}{2}\cos(\theta) \right\} &= \iint_{x < \frac{L}{2} \cos(y)} f_X(x) f_{\theta}{y} dxdy \\
& = \frac{4}{\pi D} \int_0^{\pi/2} \int_{0}^{\frac{L}{2} \cos(y)} dxdy\\
& = \frac{2L}{\pi D}.
\end{align*}
$$

  </div>
</details>


</div>




<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  If random variables $X,Y,Z$ are independent and uniformly distributed over $[0,1]$, compute $\mathbb{P} \{ X \geq YZ \}$.

  <br>

  <details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
    Since

$$
f_{X,Y,Z} (x,y,z) = f_X(x) f_Y(y)f_Z(z) = 1, \hspace{0.1cm} (x,y,z) \in [0,1]^3,
$$

so we have

$$
\begin{align*}
\mathbb{P}\{ X \geq YZ \} &= \iiint_{x \geq yz} f_{X,Y,Z}(x,y,z) dxdydz \\
&= \int_{0}^1 \int_0^1 \int_{yz}^1 dxdydz\\
&=\frac{3}{4}.
\end{align*}
$$

Suppose $X,Y$ are independent random variables, we also want to find the probability distribution of $X+Y$. We have

$$
\begin{align*}
F_{X+Y}(a) &= \mathbb{P}\{ X + Y \leq a\}\\
&=\iint_{x+y\leq a} f_X(x) f_Y(y) dxdy\\
&= \int_{-\infty}^{+\infty} \int_{-\infty}^{a-y} f_X(x) f_Y(y) dxdy\\
& = \int_{-\infty}^{+\infty} \int_{-\infty}^{a-y} f_X(x) dx f_Y(y)dy\\
&= \int_{-\infty}^{+\infty} F_X(a-y) f_Y(y)dy
\end{align*}
$$

The cumulative distribution function $F_{X+Y}$ is called the convolution of the distributions $F_X$ and $F_Y$, by differentiating the equation, we get

$$
f_{X+Y}(a) = \int_{-\infty}^{+\infty} f_X(a-y) f_Y(y) dy
$$
  </div>
</details>


</div>



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Suppose $X,Y$ are independent random variables both uniformly distributed on $[0,1]$, find the probability density function of $X+Y$.


<br>
<details style="margin-top: 1em;">
  <summary style="font-weight: bold; color: #444; cursor: pointer;">
    Click to show/hide solution
  </summary>
  <div style="border-left: 6px solid gray; background-color: #f9f9f9; padding: 10px; margin-top: 10px;">
    <strong>Solution.</strong><br>
     We know that

$$
f_X(a) = f_Y(a) = \begin{cases} 1, 0<a<1 \\ 0, \text{otherwise} \end{cases},
$$

so we have

$$
f_{X+Y}(a) = \int_0^1 f_X(a-y) f_Y(y) dy = \int_0^1 f_X(a-y) dy
$$

For $0 \leq a \leq 1$, we have

$$
f_{X+Y}(a) = \int_0^a dy = a
$$

and for $1 \leq a \leq 2$, we have

$$
f_{X+Y}(a) = \int_{a-1}^1 dy = 2-a
$$

Hence

$$
f_{X+Y}(a) = \begin{cases} a, 0 \leq a \leq 1 \\ 2 - a , 1<a<2 \\ 0, \text{otherwise} \end{cases}.
$$
  </div>
</details>


</div>


<div style="background-color: #ffd6e8; padding: 1em; border-left: 6px solid #ff66b2; border-radius: 8px; margin: 1em 0;">
  <strong>Corollary.</strong> Suppose $X_1,X_2,\cdots,X_n$ are independent random variables uniformly distributed on $[0,1]$, and let $F_n(x) = \mathbb{P}\{ X_1 + X_2 + \cdots +X_n \leq x \}$, then 

$$
F_n(x) = \frac{x^n}{n!}, \hspace{0.2cm} \text{when $0 \leq x \leq 1$}
$$


</div>


<div style="background-color: #fff9cc; padding: 1em; border-left: 6px solid #ffeb3b; border-radius: 8px; margin: 1em 0;">
  <strong>Proof.</strong> Proof can be done by induction.
</div>




Based on example above, what is the expected number of $n$ such that $X_1+X_2+\cdots+X_n >1$? That is, we want to find

$$
N := \min \{ n : X_1 + X_2+ \cdots+X_n > 1 \}
$$

Note that $N > n$ if and only if $X_1+X_2+\cdots+X_n \leq 1$, so

$$
\mathbb{P}\{ N > n\} = F_n(1) = \frac{1}{n!}, \hspace{0.2cm} n>0,
$$

thus

$$
\mathbb{P}\{ N = n\} = \mathbb{P}\{ N > n-1\} - \mathbb{P}\{ N >n\} = \frac{1}{(n-1)!} - \frac{1}{n!} = \frac{n-1}{n!}
$$

Therefore 

$$
\mathbb{E}(N) = \sum_{n=1}^{+\infty} \frac{n(n-1)}{n!} = \sum_{n=2}^{+\infty} \frac{1}{(n-2)!} = e.
$$



The sum of the independent random variables can also be calculated using moment generating functions. Suppose $X_1,X_2,\cdots,X_n$ are $n$ independent random variables and

$$
Y = X_1+X_2+\cdots+X_n
$$

Then

$$
\begin{align*}
M_Y(s) &= \mathbb{E}[ e^{sY} ] \\
& = \mathbb{E}[ e^{s(X_1+\cdots+X_n)}]\\
&= \mathbb{E}[ e^{sX_1} e^{sX_2} \cdots e^{sX_n}\\
&= \mathbb{E}[e^{sX_1}] \cdots \mathbb{E}[e^{sX_n}]\\
&= M_{X_1}(s) \cdots M_{X_n}(s).
\end{align*}
$$

This important application can be used to find the moment generating function for a binomial random variable. Suppose $X \sim Binomial(n,p)$, then we know that

$$
X = X_1+X_2+\cdots+X_n
$$

where $X_i \sim Bernoulli(p)$, thus

$$
M_X(s) = M_{X_1}(s) \cdots M_{X_n}(s)
$$

where

$$
M_{X_i}(s) = \mathbb{E}[e^{sX_i}] = pe^s + 1-p
$$

So 

$$
M_X(s) = (pe^s+1-p)^n.
$$













