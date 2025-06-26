---
title: "Conditional Probability and Bayes Theorem"
collection: publications
category: probability
permalink: /publication/bayes
excerpt: 'We will investigate conditional probability and Bayes theorem.'
date: 2024-10-01
venue: 'Fall'
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
#paperurl: 'http://academicpages.github.io/files/paper3.pdf'
citation: 'Jiajun Zhang, (2024) Conditional Probability and Bayes Theorem'
---

# Conditional Probability

**Definition**
Let $(\Omega,\mathcal{F})$ be the sample space, $A,H \in \Omega$, then we define $\P(A \vert H)$ to be the probability of $A$ given that $H$ occurs, known as the conditional probability of $A$ given $H$.


**Example:** We may think of rolling a fair dice: If no condition is given, then the probability that number $3$ will face up is just $\displaystyle{\frac{1}{6}}$, but what if we given the condition that the number face up is odd? Then based on this assumption, the probability that number $3$ will face up is $\displaystyle{\frac{1}{3}}$.\\

But how do we actually compute $\P(A \vert H)$? Think about this: By the construction of conditional probability, $\P(A \vert H)$ should somehow proportional to $\P(A \cap H)$, because $\P(A \vert H)$ is an event in $\P(A \cap H)$. We denote by $\P(A \vert H) = k \P(A \cap H)$ for some $k$, now consider $\P(H \vert H) = k \P(H \cap H)$, we conclude that $1 = k \P(H)$, so we have $k = \displaystyle{\frac{1}{\P(H)}}$.\\

**Theorem
Let $(\Omega,\mathcal{F})$ be the sample space, $A,H \in \Omega$, then the conditional probability of $A$ given $H$ is given by

$$
\P(A \vert H) = \frac{\P(A \cap H)}{\P(H)}
$$


If $\P(A \vert H) = \P(A)$, by theorem 8 we can further conclude $\P(A \cap H) = \P(A) \P(H)$.\\

Conditional probability is also a probability measure, it satisfies all the axioms of a probability measure.\\

**Corollary
Let $B$, $\{ H_n \}_{n=1}^{+\infty}$ be events, then\\

1. $\P(B | B) = 1$;\\

2. $\P(H | B) = 1 - \P(H^C | B)$;\\

3. If $H_1,H_2,\cdots$ are disjoint, then $\displaystyle{\P \left( \bigcup_{n=1}^{+\infty} H_n \Bigg\vert B\right) = \sum_{i=1}^n \P(H_n | B) }$.


**Definition
Let $(\Omega,\mathcal{F})$ be the sample space, $A,H \in \Omega$, then we say $A,H$ are independent, if $\P(A \cap H) = \P(A) \P(H)$, i.e, the occurence of $A$ does not depend on $H$.


**Corollary
Let $(\Omega,\mathcal{F})$ be the sample space, and $A_1,A_2,\cdots,A_n \in \Omega$, then

$$
\P\left( \bigcap_{j=1}^n A_j \right) = \prod_{i=1}^n \P \left( A_i \Bigg\vert \bigcap_{j=1}^{i-1} A_j \right)
$$


\**Proof
We have

$$
\P \left( \bigcap_{j=1}^n A_j \right) = \P \left( A_j \bigcap \left( \bigcap_{i=1}^{j-1} A_i \right) \right) = \P \left( \bigcap_{i=1}^{n-1} A_j \right) \P \left( A_j \Bigg\vert \bigcap_{i=1}^{j-1} A_i \right),
$$

and we may perform the same step on $ \P \left( \bigcap_{i=1}^{n-1} A_j \right)$, and we will eventually reach

$$
\P\left( \bigcap_{j=1}^n A_j \right) = \prod_{i=1}^n \P \left( A_i \Bigg\vert \bigcap_{j=1}^{i-1} A_j \right)
$$

**QED.

**Definition
A sequence  $\{ H_n \}$ of events in $\mathcal{F}$ is called a partition of $\Omega$ if $H_i \cap H_j = \varnothing, i \neq j$ and $\displaystyle{\bigcup_{n=1}^{\infty} H_n = \Omega}$.



**Theorem
(Law of Total Probability)
Let $\{H_n \}$ be a partition of $\Omega$, $\P(H_i) \geq 0$, then $\forall B \in \mathcal{F}$, we have

$$
\P(B) = \sum_{n=1}^{\infty} \P(B \vert H_n) \P(H_n)
$$


**Proof
We know that $B = B \cap \Omega = B \cap \bigcup_{n=1}^{\infty} H_n = \bigcup_{n=1}^{\infty} B \cap H_n$, thus

$$
\begin{align*}
\P(B) &= \P \left( \bigcup_{n=1}^{\infty} B \cap H_n \right)\\
& = \sum_{n=1}^{\infty} \P(B \cap H_n), \text{since $B\cap H_n$'s are disjoint} \\
& = \sum_{n=1}^{\infty} \P(B \vert H_n) \P(H_n)
\end{align*}
$$

**QED.

**Theorem
(Bayes Theorem) Let $\{ H_n \}$ be a partition of $\Omega$, $\P(H_n) > 0$. Suppose $B \in \mathcal{F}$ with $P(B) > 0$, then

$$
\P(H_k \vert B) = \frac{\displaystyle{\P(H_k)P(B \vert H_k)}}{\displaystyle{\sum_{i=1}^{\infty} P(H_i) \P(B \vert H_i)}}
$$


\**Proof
We know that
$$
\begin{align*}
\P(H_k \vert B) &= \frac{\P(H_k \cap B)}{\P(B)}\\
&= \frac{\P(B \vert H_k ) \P(H_k)}{\P(B)},
\end{align*}
$$

and this follows from the result in theorem 9.
**QED.


\textbf{Example:} A certain disease affects about $1$ out of $10,000$ people. There is a test to check whether the person has the disease. The test is quite accurate, in particular we know that :

$\bullet$ The probability that the test result is positive (suggests that the person has the disease), given that the person does not have the disease is only $0.02$;

$\bullet$ The probability that the test result is negative (suggests that the person does not have the disease), given that the person has the disease is only $0.01$.

Now a random person gets tested for the disease and the result is positive. What is the probability that the person has the disease?


**Solution:** Let $A$ to be the event that the person has the disease and we know that $\P(A) = 0.0001$ and $\P(A^C) = 0.9999$ (The person does not have the disease); Let $H$ to be the event that the test is positive, ($H^C)$ to be the event that the test is negative). Based on what the problem is given, we know that

$$
\P( H \vert A^C) = 0.02 ; \P(H^C \vert A) = 0.01
$$

and we aim to find $\P( A \vert H)$, thus using Bayes theorem, we have

$$
\begin{align*}
\P(A \vert H) =& \frac{\P(H \vert A) \P(A)}{\P(H \vert A) \P(A) + \P(H \vert A^C) \P(A^C)}\\
& = \frac{(1-0.01) \times 0.0001}{(1-0.01) \times 0.0001 + 0.02 \times (1-0.0001)} \\
& = 0.0049.
\end{align*}
$$

**Example:** In Bob's town, it's rainy one thirds of the days. Given that it is rainy, there will be a heavy traffic with probability $0.5$, and given that it is not rainy, there will be heavy traffic with probability $0.25$. If it is rainy and there is heavy traffic, Bob will arrive late for work with probability $0.5$. on the other hand (not rainy and no heavy traffic), then the probability of being late is reduced to $0.125$. In other situations (rainy with no heavy traffic or not rainy with heavy traffic), the probability of being late is $0.25$. Then pick a random day, Find:

(a) The probability that it is not raining and there is heavy traffic and Bob is not late for work;

(b) The probability that Bob is late for work;

(c) Given that Bob is late for work, the probability that it rained  that day.


**Solution:**
To start with, we define: $R$ to be the event that it is rainy; $T$ to be the event that there will be heavy traffic; $L$ to be the event that Bob is late for work. 


(a) We aim to find

$$
\P(R^C \cap T \cap L^C)
$$

Then, 

$$
\P(R^C \cap T \cap L^C) = \frac{2}{3} \times \frac{1}{4} \times \frac{3}{4} = \frac{1}{8}.
$$

(b) Denote $\P(L)$ to be the probability that Bob will be late, then we may apply the law of total probability:

$$
\P(L) = \P(L \vert R \cap T) \P(R \cap T) + \P(L \vert R^c \cap T^C) \P(R^C \cap T^C) + \P(L \vert R^C \vert T) \P(R^C \cap T) + \P(L \vert R \cap T^C) \P(R \cap T^C)
$$

And we are given that

$$
\P(L \vert R \cap T) = \frac{1}{2} ; \P(L \vert R^C \cap T^C ) = \frac{1}{8} ; \P(L \vert R^C \cap T) = \P(L \vert R \cap T^C) = \frac{1}{4}
$$

Also we may use conditional probability to solve that

$$
\begin{align*}
\P(R \cap T) &= \P(T \vert R) \P(R) = \frac{1}{2} \times \frac{1}{3} = \frac{1}{6} \\
\P(R^C \cap T^C) &= \P(T^C \vert R^C) \P(R^C)= (1-\P(T \vert R^C))\P(R^C) = \frac{3}{4} \times \frac{2}{3} = \frac{1}{2}\\
\P(R^C \cap T) &= \P(T \vert R^C) \P(R^C) = \frac{1}{4} \times \frac{2}{3} = \frac{1}{6}\\
\P(R \cap T^C) &= \P(T^C \vert R) \P(R) = (1 - \P(T \vert R))\P(R) = \frac{1}{2} \times \frac{1}{3} = \frac{1}{6} 
\end{align*}
$$

Thus we have
$$
\P(L) = \frac{1}{2} \times \frac{1}{6} + \frac{1}{8} \times \frac{1}{2} + \frac{1}{4} \times \frac{1}{6} + \frac{1}{4} \times \frac{1}{6} \approx 0.2292.
$$


