---
layout: post
title: Global Sensitivity Analysis 
tags: [Sensitivity,Sobol]
---

>Global Sensitivity Analysis (SA) aims to quantify the relative importance of
>each uncertain inputs to the uncertainty in the output of a model.

Most of the notations and concepts here are following Haario et al. 2001.

## Variance-based method 
Consider an square integrable function $$f(x)$$ in the form
(ANOVA-representation)

$$\begin{split}
u(\bm \xi)=u(\xi_1,\ldots,\xi_k) =
&u_0+ \sum_{i=1}^d u_i(\xi_i)+
        \sum_{i=1}^d \sum_{j=i+1}^d u_{i.j}(\xi_i,\xi_j)+\\
		        &\sum_{i=1}^d \sum_{j=i+1}^d \sum_{k=j+1}^d
				        u_{i,j,k}(\xi_i,\xi_j,\xi_k)+\cdots+u_{1,\ldots,d}(\xi_1,\ldots,\xi_d)
						\end{split}$$

the total number of summands is $$2^n$$.

Some defination of ANOVA-representation:

$$ u(\bm \xi)=\sum_{ \mathfrak i \subseteq \mathfrak D} u_{\mathfrak i}(\bm
         \xi_{\mathfrak i}), \qquad \mbox{where}\ \
		         \mathfrak D=\{1,\ldots,d\}$$

### Monte-Carlo estimate



### Polynomila Chaos expansion estimate
