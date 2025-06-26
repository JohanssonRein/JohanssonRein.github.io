---
title: "Partial Fraction Decompositions"
collection: publications
category: calculus
permalink: /publication/pfd
excerpt: 'In this article we will investigate different ways to solve integrals which is a fraction of two polynomials'
date: 2024-04-05
venue: 'Summer'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024). Partial Fractions Decompositions'
---

In this section, we will learn how to solve integrals like 
$\displaystyle{\int \frac{P(x)}{Q(x)}dx}$ where $P(x),Q(x)$ are polynomials,
and $Q(x) \neq 0$. The method we use is called
Partial Fraction Decomposition (PFD), which is basically 
decompose a fraction into the sums of several fractions, such that 
for each single term we can integrate by using basic methods. A simple example 
is to integrate $\displaystyle{\int \frac{1}{x^2 - 1} dx}$, in this case we 
may use $x^2 - 1 = (x+1)(x-1)$ and decompose the integral as 

$$ \int \frac{1}{(x+1)(x-1)} dx =\frac{1}{2} \left( \int \frac{1}{x - 1}dx + \int \frac{1}{x + 1}dx \right)$$

Thus for each part we may integrate quickly, that is 

$$
\frac{1}{2} \left( \int \frac{1}{x - 1}dx + \int \frac{1}{x + 1}dx \right) =
\frac{1}{2} \left( \ln \vert x - 1 \vert + \ln \vert x + 1 \vert \right) + C
$$

We will learn all the methods to do such integral. In the whole section, we will assume that $\displaystyle{f(x) = \frac{P(x)}{Q(x)}}$

**Step 1 : Check if $f(x)$ is proper or not**

Suppose $P(x)$ has a maximum  degree of $n$ and $Q(x)$ has a maximum 
degree of $m$, then:


$\bullet$ $f(x)$ is proper, if $m > n$, such as $f(x) = \displaystyle{\frac{x^3 + 1}{x^4 + 2x}}$ is proper


$\bullet$ $f(x)$ is improper, if $m \leq n$, such as $f(x) = \displaystyle{\frac{x^3 + 1}{x^2 - 6}}$ is improper


Note that partial fraction decomposition only works for proper 
fractions. For improper fractions, we need to do long division
to simplify the polynomial. If $f(x)$ is improper, we may do:

$$
\displaystyle{f(x) = S(x) + \frac{R(x)}{Q(x)}}
$$

by long division, and 
the reminder $\displaystyle{\frac{R(x)}{Q(x)}}$ would always be proper. 


**Step 2 : When $f(x)$ is proper, apply PFD**


**Theorem**: Any polynomial $Q(x)$ can be factored into a product of factors.

In this course, the denominator will always be easy to factor, so you shouldn't
worry much about it. For example, to factor $Q(x) = x^4 - 16$, $M(x) = 
2x^3 + 3x^2 - 2x$.


**Step 3 : Identify the PFD**

$\bullet$ PFD Type 1 : We have **distinct, linear factors**
for the denominator.

A simple example is like $f(x) = 
\displaystyle{\frac{P(x)}{(a_1x_1 + b_1)(a_2x_2 + b_2)\cdots(a_nx_n+b_n)}}$
, where $f(x)$ is proper and each term is distinct. In this case, we have 
the following property:


$$
f(x) = 
\displaystyle{\frac{P(x)}{(a_1x_1 + b_1)(a_2x_2 + b_2)\cdots(a_nx_n+b_n)}
= \frac{C_1}{a_1x_1 + b_1} + \frac{C_2}{a_2x_2 + b_2} + \cdots + 
\frac{C_n}{a_nx_n + b_n}}
$$


Where $C_1,C_2,\cdots,C_n$ are all constants. Thus, we can solve 
$C_1$ to $C_n$. Then, we want to make the denominator to be the same for each term, so for each factor, we 
multiply the remaining terms on both the numerator and denominator, and sum the numerators up, we then have

$$
\displaystyle{ \sum_{i = 1}^{n} C_i \left(\prod_{j \neq i}^{n}(a_jx_j + b_j)\right) = P(x)}
$$

Now, depending on the degree of $P(x)$, we may have different numbers 
of equations. But the point is that if two polynomials are equal, then 
the coefficients for each degree must be the same, so we only need to 
compare the coefficients and then we have a systems of linear equations with 
unknowns $C_1,\cdots,C_n$. And in this course, we can always assume that 
there is a unique solution, otherwise we can't integrate. 



Example 1 : Evaluate $\displaystyle{\int \frac{1}{x^2 - 1}dx}$


First, we need to check if it is proper or not, and it is obvious that
    $f(x)$ is proper. So we may do the second step, and factor the term 
    $x^2-1 = (x+1)(x-1)$, then notice that each factor is unique, so 
    it belongs to type 1, thus we write 
    
$$
    \displaystyle{\int \frac{1}{x^2 - 1}dx = \int\left(
        \frac{C_1}{x + 1} + \frac{C_2}{x - 1}
    \right)dx}
$$ 
    
 And we try to make the denominator the same for each factor, we do:
 
$$
    \int \left( \frac{C_1(x-1)}{(x+1)(x-1)} + \frac{C_2(x+1)}{(x+1)(x-1)}\right)dx 
$$ 
   
So, the sum of the numerators are $C_1x + C_2x + C_2 - C_1$, which is 
    $(C_1 + C_2)x + (C_2 - C_1)$, this should be the same as $P(x)$, which is 
    $1$, so we have $(C_1 + C_2)x + (C_2 - C_1) = 1$, and as we have mentioned 
    above, the coefficients for each degree must be the same, hence we have 
    $C_1 + C_2 = 0; C_2 - C_1 = 1$, we get 
    $\displaystyle{C_1 = -\frac{1}{2}, C_2 = \frac{1}{2}}$, and that's why 
    we get 
    
$$
    \frac{1}{2} \left( \int \frac{1}{x - 1}dx + \int \frac{1}{x + 1}dx \right) =
    \frac{1}{2} \left( \ln \vert x - 1 \vert + \ln \vert x + 1 \vert \right) + C
$$



Exercise 1 : Evaluate $ \displaystyle{\int \frac{x + 5}{x^2 + x -2}dx}$


Exercise 2 : Evaluate $ \displaystyle{\int \frac{x^2 + 2x - 1}{2x^3 + 3x^2 - 2x}dx}$




**Two techniques for faster integration : (Optional Material)**


$\bullet$ Factoring quadratic terms like $x^2 - 5x + 6$

I would like to call this method *cross product* , though it is different from the real cross product in vector calculus,
the process is to decompose the coefficients for $x^2$ and constant terms to be the product of two integers. Say we have 
$ax^2 + bx + c$, if $a = p_1p_2$ and $c = q_1q_2$, where each number is an integer. Then we take the sum of the 
cross of $a$ and $c$, that is we calculate $p_1q_2 + p_2q_1$, if we have $p_1q_2 + p_2q_1 = b$, then we can factor the 
quadratic term into the product of two linear terms, namely $(p_1x + q_1)(p_2x+q_2)$. In the example $x^2 - 5x + 6$, we 
have $x = 1\times 1$, thus $p_1 = p_2 = 1$, and we have $6 = -2 \times (-3)$, thus $q_1 = -2, q_2 = -3$, and we have 
$p_1q_2 + p_2q_1 = -3 + (-2) = -5$, the coefficient of $x$ term. Thus we can write $x^2 - 5x + 6 = (x-2)(x-3)$.
But notice that this method only applies for some quadratic polynomials, and we might need to try many ways of factorization
to find the solution, or we might not be able to factor at all.


$\bullet$ Solving systems of linear equations using matrices

Notice that in this part, we will only discuss the form where $A \vec x = \vec y$ has **one unique solution**, 
and we will not discuss the cases when there are no solutions or multiple solutions (infinity many). This method is 
extremely helpful to solve for $C_1,\cdots,C_n$ as we had seen before. After we match the coefficients with $P(x)$ on each term, 
suppose we have the following equation:

$$
a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1
$$
$$
a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2
$$
$$
\vdots
$$
$$
a_{n1}x_1 + a_{n2}x_2 + \cdots + a_{nn}x_n = b_n 
$$

We call this Systems of Linear Equations of $n$ unknowns ($x_1,x_2 \cdots x_n$), where $a_{ij}$ are coefficients, and 
$b_i$ are the results.for example, a system of linear equations 
of $3$ unknowns can be:

$$
\begin{cases}
2x + y + 2z = 1\\
3x + 2y - z = 2\\
-2x + 0y + 0z = -1
\end{cases}
$$

We may write this equation into the matrix form, which is 

$$
\begin{bmatrix}
2 & &1 & &2 &| &1\\
3 & &2 & &-1 &| &2\\
-2 & &0 & &0 &| &-1
\end{bmatrix}

$$
In this form, we do not write the unknowns, as it is easier to perform operations, we only write the coefficients. On each row,
it represents one equation, and the coefficients are ordered, column $i$ represents the coefficients for $x_i$ and 
row $j$ represents the $j$th equation. On the left of the vertical bar are the coefficients, namely $a_{ij}$ and on the right 
of the vertical bar are the results for each equation, $b_{i}$. Our goal is to perform different operations on each column and rows 
such that in the end we will get the identity matrices like:

$$
\begin{bmatrix}
1 & &0 & &0 &| &a\\
0 & &1 & &0 &| &b\\
0 & &0 & &1 &| &c
\end{bmatrix}
$$

Only the diagonal has elements $1$, and $0$ for all other positions. In this case, we shall easily see that 
$x_1 = a, x_2 = b, x_3 = c$ and thus we have solved the equations. In order to achieve that, we will perform the 
following operations:


**Theorem**: In the matrix form of a systems of linear equations, we can perform the following operation, and the result will not be affected.

OPERATION 1 : Interchanging any two rows / columns

OPERATION 2 : Multiplying one row with a constant

OPERATION 3 : Adding the corresponding elements from one row to another row



Now, let's solve the matrix we have seen before by using OPERATION 1,2,3. The common method is to start from
column 1, and then move to column 2, and so on. So after the operation on the first column, we should get:

$$
\begin{bmatrix}
2 & &1 & &2 &| &1\\
3 & &2 & &-1 &| &2\\
-2 & &0 & &0 &| &-1
\end{bmatrix} \xrightarrow{\text{After Some Operations}}
\begin{bmatrix}
1 & &a_{12} & &a_{13} &| &b_1\\
0 & &a_{22} & &a_{23} &| &b_2\\
0 & &a_{32} & &a_{33} &| &b_3
\end{bmatrix}
$$

So, to make $a_{21} = a_{31} = 0$, we see that on the third column, we have $a_{31} = -2 = -a_{11}$, so we may add row 1 to 
row 3 to make $a_{31} = 0$, thus this is what we do:

$$
\begin{bmatrix}
2 & &1 & &2 &| &1\\
3 & &2 & &-1 &| &2\\
-2 & &0 & &0 &| &-1
\end{bmatrix} \xrightarrow{\text{$R_3 + R_1$}}
\begin{bmatrix}
2 & &1 & &2 &| &1\\
3 & &2 & &-1 &| &2\\
0 & &1 & &2 &| &0
\end{bmatrix}
$$

Then, for row 2, we can do $2 \times R_2 - 3 \times R_1$, since $2 a_{21} = 6 , 3 a_{11} = 6$, thus: 

$$
\begin{bmatrix}
2 & &1 & &2 &| &1\\
3 & &2 & &-1 &| &2\\
-2 & &0 & &0 &| &-1
\end{bmatrix} \xrightarrow{\text{$ 2R_2 - 3R_1$}}
\begin{bmatrix}
6 & &3 & &6 &| &3\\
0 & &1 & &-8 &| &1\\
0 & &1 & &2 &| &0
\end{bmatrix}
$$

Thus, we are finished on column 1, now we shall move on to column 2. This times, we want to make $a_{22}$ non-zero and the rest to be all zero. Since row 1 is a multiple of 3, we may divide by 3. We get 

$$
\begin{bmatrix}
6 & &3 & &6 &| &3\\
0 & &1 & &-8 &| &2\\
0 & &1 & &2 &| &0
\end{bmatrix} \xrightarrow{\text{$ R_1 / 3$}}
\begin{bmatrix}
2 & &1 & &2 &| &1\\
0 & &1 & &-8 &| &1\\
0 & &1 & &2 &| &0
\end{bmatrix}
$$

Then, we can do $R_1 - R_2$ and $R_3 - R_2$ to cancel out the $1$ on the position $a_{12},a_{32}$, and we will get:

$$
\begin{bmatrix}
2 & &1 & &2 &| &1\\
0 & &1 & &-8 &| &1\\
0 & &1 & &2 &| &0
\end{bmatrix}
 \xrightarrow{\text{$ R_1 - R_2 ; R_3 - R_2$}}
\begin{bmatrix}
2 & &0 & &10 &| &0\\
0 & &1 & &-8 &| &1\\
0 & &0 & &10 &| &-1
\end{bmatrix}
$$

You see the advantage of starting from column 1? In this case we will not create any extra non-zero values on the terms we had 
done before, so only in this way we can make our results easier. Now we come to the third column, and we want to keep
$a_{33}$ non zero while cancelling out $a_{13},a_{23}$. Thus we do :

$$
\begin{bmatrix}
2 & &0 & &10 &| &0\\
0 & &1 & &-8 &| &1\\
0 & &0 & &10 &| &-1
\end{bmatrix}  \xrightarrow{\text{$ R_1 - R_3 ; 10R_2 + 8R_3$}}
\begin{bmatrix}
2 & &0 & &0 &| &1\\
0 & &10 & &0 &| &2\\
0 & &0 & &10 &| &-1
\end{bmatrix}
$$

Lastly, we make the elements on the diagonal to be 1, so our last step is:
$$
\begin{bmatrix}
2 & &0 & &0 &| &1\\
0 & &10 & &0 &| &2\\
0 & &0 & &10 &| &-1
\end{bmatrix}
 \xrightarrow{\text{$ R_1 / 2; R_2 / 10 ; R_3 / 10$}}
\begin{bmatrix}
1 & &0 & &0 &| &\displaystyle{\frac{1}{2}}\\
0 & &1 & &0 &| &\displaystyle{\frac{1}{5}}\\
0 & &0 & &1 &| &\displaystyle{-\frac{1}{10}}
\end{bmatrix}
$$

So, the result we get is $\displaystyle{a = \frac{1}{2}, b = \frac{1}{5}, c = -\frac{1}{10}}$. Again, I want to state that we cannot always find a solution to such a linear system, but in this course, in this technique, one can always assume that there 
will be exactly one unique solution. The discussion on cases where there won't be solutions are beyond the slope of this course. If the rows and columns don't match (not the same number), we will discuss later. Please see my notes on Linear Algebra for if the reader would like to know more about it.



$\bullet$ Practice Exercises

1. Try to factor the quadratic terms below into the product of two linear terms. 

(1) $x^2 + 11x - 10$  (2) $3x^2 + 4x + 1$  (3) $-6x^2 - 3x + 3$


2. Try to solve the following systems of linear equations, using Gauss - Elimination.
$$
\begin{cases}
x + y + z &= 2\\
x + y + 2z & = 1\\
2x + y - z & = 4
\end{cases}
$$
$$
\begin{cases}}
x + y - 2z &= -3\\
2x + y + 2z & = 0\\
-x - y + 4z & = 4
\end{cases}
$$


$\bullet$ PDF Type 2 : Linear Terms with Repetitions

Compared to type 1, the only difference is that we have **some multiples** of a linear term after we factored the denominator. Say 
we have :

$$
f(x) = \frac{P(x)}{(a_1x+b_1)^{r_1}(a_2x + b_2)^{r_2} \cdots (a_kx + b_k)^{r_k}}
$$

Where we will restrict $r_1,\cdots,r_n$ to be positive integers. Then, we can decompose it into $r_1 + r_2 + \cdots + r_n$
terms, and for each $(a_ix + b_i)^{r_i}$, we have:

$$
\frac{Q_i(x)}{(a_ix+b_i)^{r_i}} = \frac{A_{i1}}{(a_ix+b)} + \frac{A_{i2}}{(a_ix+b)^2} + \cdots + \frac{A_{i{r_i-1}}}{(a_ix+b_i)^{r_i-1}} + \frac{A_{ir}}{(a_ix+b_i)^{r_i}}
$$

A simple example would be :

$$
\frac{x^3 - x + 1}{x^2(x-1)^3} = \frac{A_1}{x} + \frac{A_2}{x^2} + \frac{A_3}{(x-1)}
+ \frac{A_4}{(x-1)^2} + \frac{A_5}{(x-1)^3}
$$

Where we may use the same strategy as we did in type 1, We try to make the denominator the same for each term, then we add the numerator together and refactor them into different terms, compare with the coefficients, and solve the systems of linear equations.

$\bullet$ PFD Type 3 : Factors with Irreducible Terms

In this case, we will deal with some terms that will not be factored into linear terms. Like $\displaystyle{
\frac{x}{(x^2 + 1)(x^2 + 4)}
}$. A quadratic term $ax^2 + bx + c$ is irreducible if $b^2 - 4ac < 0$. In this case, we may decompose the whole term, but somehow we need to add a linear term to the numerator, like

$$
\frac{x}{(x^2 + 1)(x^2 + 4)} = \frac{Ax + B}{(x^2 + 1)} + \frac{Cx + D}{(x^2 + 4)}
$$

Then, by using the same method we can solve for unknowns $A,B,C,D$ and thus solve the integral. In cases where there are 
repetitions like we had seen in type 2, we can also decompose multiple terms from it with different degrees, like

$$
\frac{x^3 + x + 1}{(x^2 + x + 1)(x^2 + 1)^3} = \frac{Ax + B}{x^2 + x + 1} + 
\frac{Cx + D}{(x^2 + 1)} + \frac{Dx + E}{(x^2 + 1)^2} + \frac{Fx + G}{(x^2 + 1)^3}
$$

And we can use the same strategy like we did before. 


$\bullet$ Rationalizing Substitution

In terms of $f(x) = \sqrt[n]{g(x)}$, we will do rationalizing substitution, that is, by making 
$ u = \sqrt[n]{g(x)}$, it will be more effective. 



$\bullet$ Example 2 : Evaluate $\displaystyle{\int \frac{x^3-4x + 1}{x^2-3x+2}dx}$


Note that this fraction is improper, thus we will do the long division first and thus, we can rewrite the integral as

$$
\displaystyle{\int \frac{x^3-4x + 1}{x^2-3x+2}dx} = \int \left( x + 3 + \frac{3x - 5}{x^2 - 3x + 2}\right)dx
$$

By the properties of the integral, we can do the following:

$$
\displaystyle{\int \left(x + 3 + \frac{3x-5}{x^2-3x+2} \right) dx} = \int (x + 3)dx + \int \frac{3x - 5}{(x-1)(x-2)} dx
$$

For the fraction part, we observe that this is of \textit{Type 1}, so we decompose the fraction as 

$$
\frac{3x-5}{(x-1)(x-2)} = \frac{C_1}{(x-1)} + \frac{C_2}{(x-2)}
$$

And we have the systems of linear equations $C_1(x-2) + C_2(x-1) = 3x - 5$, which is 
$(C_1 + C_2)x - (2C_1 + C_2) = 3x - 5$, by making the corresponding coefficients the same, we then have
$C_1 + C_2 = 3, 2C_1 + C_2 = 5$, hence $C_1 = 2, C_2 = 1$, so the integral we are evaluating is actually

$$
\int (x + 3) dx + \int \left( \frac{2}{x-1} + \frac{1}{x-2} \right) dx
$$

Which is

$$
\frac{1}{2}x^2 + 3x + 2\ln \vert x - 1 \vert + \ln \vert x - 2 \vert + C
$$



$\bullet$ Example 3 : Evaluate $\displaystyle{\int \frac{2x^2 - x + 4}{x^3 + 4x} dx}$


In this fraction, we see that it is proper, so there is no need to do long division. We may factor the 
denominator like

$$
\int \frac{2x^2 - x + 4}{x^3 + 4x} dx = \int \frac{2x^2 - x + 4}{x (x^2 + 4)} dx
$$

Notice that $(x^2 + 4)$ is irreducible, because $b^2 - 4ac = 0 - 16 = -16 < 0$, so we see that is it of 
\textit{Type 3}, thus we decompose the fraction as

$$
\frac{2x^2 - x + 4}{x (x^2 + 4)} = \frac{A}{x} + \frac{Bx + C}{x^2 + 4}
$$

Then, by making the denominator the same, we get the equation $A(x^2+4) + x(Bx + C)$ for the numerator.
Then compare it with the original fraction, we have $2x^2 - x + 4 = 
(A + B)x^2 + Cx + 4A$, i.e e have the following systems of linear equations.

$$
\begin{cases}
A + B &= 2\\
C & = -1\\
4A &= 4
\end{cases}
$$

We can solve it using Gauss-Elimination in the matrix form or by other methods, in the end we will get
$A = 1, B = 1, C = -1$, then we have the integral 

$$
\int \left( \frac{1}{x} + \frac{x - 1}{x^2 + 4} \right) dx = 
\int \frac{1}{x} dx + \int \frac{x}{x^2 + 4} dx + \int \frac{-1}{x^2 + 4} dx
$$

We may perform a u-Substitution on the second term, let $u = x^2 + 4$, thus we have
$du = 2xdx$, then we have

$$
\int \frac{1}{x} dx +  \frac{1}{2} \int \frac{1}{u} du + \int \frac{-1}{x^2 + 4} dx
$$

Thus, the final result is given by

$$
\int \frac{1}{x} dx +  \frac{1}{2} \int \frac{1}{u} du + \int \frac{-1}{x^2 + 4} dx = 
\ln \vert x \vert + \frac{1}{2}\ln \vert x^2 + 4 \vert - \frac{1}{2} \arctan (\frac{x}{2}) + C
$$


Notice that there is a very important formula used in this problem:

$$
\boxed{\int \frac{1}{x^2 + a^2} dx = \frac{1}{a}\arctan \left( \frac{x}{a} \right)+ C}
$$


I also listed some useful tricks: The standard method to prove them is by Trig - Sub using the equality $1 + \tan^2 x = \sec^2 x$.

$$
\boxed{\int \frac{1}{x^2 - a^2} dx = \frac{1}{2a} \ln \Bigg| \frac{x + a}{x - a} \Bigg| + C}
$$

$$
\boxed{\int \frac{1}{\sqrt{x^2 - a^2}} dx =  \ln \Big| x + \sqrt{x^2 - a^2} \Big| + C}
$$

$$
\boxed{\int \frac{\sqrt{x^2 - a^2}}{x} dx = \sqrt{x^2 - a^2} - a \arccos \left( \frac{a}{x} \right)+ C}
$$

$$
\boxed{\int \frac{1}{x^2 \sqrt{x^2 + a^2}} dx = -\frac{\sqrt{x^2 + a^2}}{a^2x} + C}
$$






















