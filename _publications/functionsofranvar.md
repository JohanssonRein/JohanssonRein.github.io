---
title: "Functions of Random Variables and Transformations"
collection: publications
category: probability
permalink: /publication/functionsofranvar
excerpt: 'We will investigate functions of random variables and transformations'
date: 2024-10-10
order: 11
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Functions of Random Variables and Transformations'
---


<div style="background-color: #ccffcc; padding: 1em; border-left: 6px solid #33cc33; border-radius: 8px; margin: 1em 0;">
  <strong>Theorem.</strong> Let $\vec X = \begin{bmatrix} X_1 & X_2 & \cdots & X_n \end{bmatrix}^T$ be an $n$-dimensional random vector with joint PDF $f_{\vec X}(\vec x)$. Let $G : \mathbb{R}^n \to \mathbb{R}^n$ be a continuous and invertible function with continuous partial derivatives and let $H = G^{-1}$. Suppose a random vector $\vec Y = \begin{bmatrix} Y_1 & Y_2 & \cdots & Y_n \end{bmatrix}^T$ is given by $\vec Y = G(\vec X)$, hence $\vec X = H(\vec Y)$, and
  
$$
\vec X = \begin{bmatrix} X_1 \\ X_2 \\ \vdots \\ X_n \end{bmatrix} =
\begin{bmatrix}
H_1(Y_1,Y_2,\cdots,Y_n) \\
H_2(Y_1,Y_2,\cdots,Y_n) \\
\vdots \\
H_n(Y_1,Y_2,\cdots,Y_n)
\end{bmatrix}
$$

Then the PDF of $\vec Y$ is given by

$$
f_{\vec Y}(\vec y) = f_{\vec X}(H(\vec y)) \vert J \vert
$$

where $J$ is the Jacobian of $H$ defined by

$$
J = 
\begin{bmatrix}
\frac{\partial H_1}{\partial y_1} & \frac{\partial H_1}{\partial y_2} & \cdots & \frac{\partial H_1}{\partial y_n} \\
\frac{\partial H_2}{\partial y_1} & \frac{\partial H_2}{\partial y_2} & \cdots & \frac{\partial H_2}{\partial y_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial H_n}{\partial y_1} & \frac{\partial H_n}{\partial y_2} & \cdots & \frac{\partial H_n}{\partial y_n} \\
\end{bmatrix}.
$$
</div>


<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Suppose $Y_1,Y_2 \sim N(0,1)$ are independent random variables, find the probability density function of $\sqrt{Y_1^2 + Y_2^2}$.

Solution: We first define two new variables:

$$
U = \sqrt{Y_1^2 + Y_2^2}, V = Y_2
$$

Then we have

$$
Y_1 = \pm \sqrt{U^2 - V^2} ; Y_2 = V
$$

Thus we may define two linear maps given by

$$
\vec{\Phi}_1 : (+\sqrt{u^2 - v^2}, v) \mapsto (u,v)
$$

$$
\vec{\Phi}_2 : (-\sqrt{u^2 - v^2}, v) \mapsto (u,v)
$$

The Jacobians are given by

$$
\mathcal{J}_1 = \det 
\begin{bmatrix}
u(\sqrt{u^2-v^2})^{-1} & -v(\sqrt{u^2-v^2})^{-1} \\
 & \\
0 & 1 
\end{bmatrix} = u(\sqrt{u^2 - v^2})^{-1}
$$

$$
\mathcal{J}_1 = \det 
\begin{bmatrix}
-u(\sqrt{u^2-v^2})^{-1} & v(\sqrt{u^2-v^2})^{-1} \\
 & \\
0 & 1 
\end{bmatrix} = -u(\sqrt{u^2 - v^2})^{-1}
$$

Then we have

$$
\begin{align*}
f_{U,V}(u,v) &= f_{Y_1,Y_2} (\sqrt{u^2-v^2},v) \vert \mathcal{J}_1 \vert + f_{Y_1,Y_2} (-\sqrt{u^2-v^2},v) \vert \mathcal{J}_2 \vert \\
&= \left( \frac{u}{\sqrt{u^2 - v^2} } \right) \left[ \frac{1}{2\pi} e^{-\frac{u^2}{2}} + \frac{1}{2\pi} e^{-\frac{u^2}{2}} \right].
\end{align*}
$$


And we have

$$
f_{U,V}(u,v) = \begin{cases} \displaystyle{\frac{ue^{-\frac{u^2}{2}}}{\pi \sqrt{u^2 - v^2}} :  \vert v \vert < u} \\ \\  \text{Does Not Exist}: \text{otherwise} \end{cases}


Now we will find the distribution restricted to $U$ only, and we have

$$
\begin{align*}
f_U(u) &= \int_{-\infty}^{+\infty} \frac{ue^{-\frac{u^2}{2}}}{\pi \sqrt{u^2 - v^2}} dv \\
& = \frac{u e^{_\frac{u^2}{2}}}{\pi} \int_{-u}^u \frac{1}{\sqrt{u^2 - v^2}} dv \\
& = \frac{1}{\pi} e^{-\frac{u^2}{2}} \int_{-\frac{\pi}{2}}^{+\frac{\pi}{2}} \frac{u \cos(\theta)d\theta}{\sqrt{1 - \sin^2(\theta)}} \\
& = ue^{-\frac{u^2}{2}}, u \geq 0
\end{align*}
$$


So we have

$$
f_U(u) = \begin{cases} ue^{-\frac{u^2}{2}}: u \geq 0 \\ 0 :\text{otherwise} \end{cases}.
$$
</div>

<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Suppose $X_1,X_2,X_3 \sim N(0,1)$ are independent standard normal random variables, and let $Y_1 = X_1+X_2+X_3, Y_2 = X_1-X_2, Y_3 = X_1-X_3$, find the joint density function of $Y_1,Y_2,Y_3$.

Solution: We have

$$
X_1 = \frac{Y_1+Y_2+Y_3}{3}, X_2 = \frac{Y_1-2Y_2+Y_3}{3}, X_3 = \frac{Y_1 + Y_2 - 2Y_3}{3}
$$

and thus the Jacobian of the transformation is given by

$$
\mathcal{J} := \det 
\begin{bmatrix}
\frac{1}{3} & \frac{1}{3} & \frac{1}{3} \\
\frac{1}{3} & -\frac{2}{3} & \frac{1}{3} \\
\frac{1}{3} & \frac{1}{3} & -\frac{2}{3}
\end{bmatrix}
$$

and we have

$$
\begin{align*}
f_{Y_1,Y_2,Y_3}(y_1,y_2,y_3) &= f_{X_1,X_2,X_3}  \left( \frac{Y_1+Y_2+Y_3}{3} , \frac{Y_1-2Y_2+Y_3}{3} , \frac{Y_1 + Y_2 - 2Y_3}{3} \right) \cdot \frac{1}{3} \\
&=\frac{1}{3 (2\pi)^{3/2}} e^{-Q(y_1,y_2,y_3) /2}
\end{align*}
$$

where

$$
Q(y_1,y_2,y_3) = \frac{y_1^2}{3} + \frac{2}{3}y_2^2 + \frac{2}{3}y_3^2 - \frac{2}{3}y_2y_3.
$$

</div>



<div style="border-left: 6px solid orange; background-color: #fff3e0; padding: 10px; margin: 15px 0;">
  <strong>Example.</strong>  Suppose $U_1,U_2$ are random variables uniformly distributed on $(0,1)$, find the distribution function for $X_1$ and $X_2$ where $X_1 = \sin(2 \pi U_2) \sqrt{-2\ln(U_1)}, X_2 = \cos(2\pi U_2) \sqrt{-2 \ln(U_1)}$.

Solution: We first find the "inverse" Jacobian:

$$
\begin{align*}
\mathcal{J}^{-1} & = \det
\begin{pmatrix}
\frac{\partial X_1}{\partial U_1} & \frac{\partial X_1}{\partial U_2} \\ & \\\frac{\partial X_2}{\partial U_1} & \frac{\partial X_2}{\partial U_2} 
\end{pmatrix} \\
\\
&= \det
\begin{pmatrix}
\displaystyle{-\frac{\sin(2\pi U_2)}{U_1 \sqrt{-2 \ln (U_1)}}} & 2\pi \cos(2\pi U_2) \sqrt{-2 \ln(U_1)} \\
 & \\
\displaystyle{-\frac{\cos(2\pi U_2)}{U_1 \sqrt{-2 \ln(U-1)}}} & -2\pi\sin(2 \pi U_2) \sqrt{-2 \ln(U_1)}
\end{pmatrix} \\
\\
&= \frac{2\pi \sin^2(2\pi u_2)}{U_1} + \frac{2\pi \cos^2(2\pi U_2)}{U_1}\\
& = \frac{2\pi}{U_1}
\end{align*}
$$

So the desired Jacobian is given by

$$
\mathcal{J} = \frac{1}{\mathcal{J}^{-1}} = \frac{U_1}{2\pi}
$$

Now according to the relations given, solve for $U_1,U_2$ in terms of $X_1,X_2$, we get:

$$
U_1 = e^{-\frac{X_1^2 + X_2^2}{2}}, U_2  =\frac{\arctan(X_1/X_2)}{2\pi}
$$

Now, we have

$$
f_{X_1,X_2}(x_1,x_2) = f_{U_1,U_2}(u_1(x_1,x_2) , u_2(x_1,x_2)) \cdot \Bigg\vert \frac{U_1}{2\pi} \Bigg\vert 
$$

where

$$
f_{U_1,U_2}(u_1,u_2) = 
\begin{cases}
1 : (u_1,u_2) \in (0,1)^2 \\
0 : \text{otherwise}
\end{cases},
$$

so we actually have

$$
\begin{align*}
f_{X_1,X_2}(x_1,x_2) &= 1 \cdot \frac{U_1}{2\pi} = \frac{1}{2\pi} e^{-\frac{x_1^2 + x_2^2}{2}} \\
& = \left( \frac{1}{\sqrt{2\pi}} e^{-x_1^2/2} \right)\left( \frac{1}{\sqrt{2\pi}} e^{-x_2^2/2} \right).
\end{align*}
$$

And thus we have $X_1, X_2 \sim N(0,1)$, the standard normal distribution.

</div>



















