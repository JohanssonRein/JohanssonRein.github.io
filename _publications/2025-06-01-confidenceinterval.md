---
title: "Statistics: Confidence Interval"
collection: publications
category: manuscripts
permalink: /publication/2025-06-01-confidenceinterval
excerpt: 'In this article we will talk about confidence interval'
date: 2025-06-01
venue: '01'
slidesurl: 'http://academicpages.github.io/files/slides1.pdf'
paperurl: 'http://academicpages.github.io/files/paper1.pdf'
bibtexurl: 'http://academicpages.github.io/files/bibtex1.bib'
citation: 'Jiajun Zhang, You. (2025), part of my notes in Honors Statistics taught by Prof. Abbas Khalili'
---

The contents above will be part of a list of publications, if the user clicks the link for the publication than the contents of section will be rendered as a full page, allowing you to provide more information about the paper for the reader. When publications are displayed as a single page, the contents of the above "citation" field will automatically be included below this section in a smaller font. 


Let $L(\vec X), U(\vec X)$ be two statistics such that $L(\vec x) \leq U(\vec x), \forall x\in\mathcal{X}$. A random interval $(L(\vec X),U(\vec X))$ is called an interval estimator or confidence interval with confidence level $1-\alpha, \alpha \in (0,1)$ if $P(L(\vec X) \leq \theta \leq U(\vec X)) = 1-\alpha$.


Note that it is wrong to say that $(L(\vec x), U(\vec x))$ (post-experimental data) captures $\theta$ with probability $1-\alpha$. The interpretation is that this interval estimator either includes $\theta$ or not, basically it captures $\theta$ with probability $0$ or $1$. if we were to repeat the experiment and compute similar confidence intervals for $\theta$, we expect that $100(1-\alpha)\%$ of those post-experimental intervals to capture $\theta$.


(Pivot Quantity)\\

A random function $Q(\vec x,\theta)$ is called a pivot quantity (PQ) iff its distribution does not depend on the parameter $\theta$, and $Q$ is a function of $\vec X$ and $\theta$ only.


Note that the function $Q$ might include $\theta$, but its overall distribution $Q(\vec x,\theta)$ is free of any parameters! For example if $X \sim N(0,\theta^2)$, then $Q(x,\theta) = \frac{1}{\theta} X \sim N(0,1)$, which is free of any parameter and it is a known distribution!\\

Once we have a PQ, and the confidence level $1-\alpha$ is given, we may find constants $c_1,c_2$ such that $$ P(c_1 \leq Q(\vec x,\theta) \leq c_2) = 1-\alpha $$

then having $c_1,c_2$ we can solve in terms of $\theta$ to get
$$
P(L(\vec X) \leq \theta \leq U(\vec X)) = 1-\alpha.
$$

Mostly, the PQ is chosen based on a sufficient statistic.

Below are common random samples and their corresponding PQ and  confidence intervals:\\
