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
(ANOVA-representation):

$$\begin{split}
u(\xi)=u(\xi_1,\ldots,\xi_k) =
&u_0+ \sum_{i=1}^d u_i(\xi_i)+\sum_{i=1}^d \sum_{j=i+1}^d u_{i.j}(\xi_i,\xi_j)+\\
&\sum_{i=1}^d \sum_{j=i+1}^d \sum_{k=j+1}^d
u_{i,j,k}(\xi_i,\xi_j,\xi_k)+\cdots+u_{1,\ldots,d}(\xi_1,\ldots,\xi_d)
\end{split}$$

the total number of summands is $$2^n$$.


### Monte-Carlo estimate

The estimation of conditiona variance $$V(E(Y|X_i))$$ using brute-force
Monte-Carlo could be impractical. For example, $$E(Y|X_i)$$ need to be estimated
first with a set of Monte-Carlo points for a fixed value of $$X_i$$, and then
this process will be repeated for different $$X_i$$ values. $$10^6$$ simulations
will be needed if 1000 points were used to get a good estimate of the
conditional mean $$E(Y|X_i)$$, and the procedure were repeated 1000 times. 

1-st order sensitivity indices:

$$
 S_{\{i\}}(f) = \frac{\mathbb V[f_{\{i\}}]}{\mathbb V[f]} 
 = \frac{\mathbb V[\mathbb E[f|x_i]]}{\mathbb V[f]}
 = \frac{\mathbb E[\mathbb E[f|x_i]^2] -\mathbb E[\mathbb E[f|x_i]]^2}{\mathbb
 V[f]}
$$

Note that $$\mathbb E[\mathbb E[f|x_i]]=\mathbb E[f]$$ and $$\mathbb E[f]$$ and
$$\mathbb V[f]$$ can be estimated using Monte-Carlo approach. 
$$\mathbb E[\mathbb E[f|x_i]^2]$$ remains to be calculated.

$$\int_{U^{d+|i \sim|}} f(x_i,x_{i\sim})f(x_i,x_{i\sim}')dx_i
dx_{i\sim}dx_{i\sim}'
=\int_{U^{|\mathfrak i|}}dx_i \int_{U^{|i\sim|}} f(x_i,x_{i\sim})dx_{i\sim} 
\int_{U^{|i\sim|}} f(x_i,x_{i\sim}')dx_{i\sim}'
=\int_{U^|i|}dx_i[\int_{U^|i\sim|}f(x_i,x_{i\sim})dx_{i\sim}]^2
$$ 

$$
\mathbb E[\mathbb E[f|x_i]^2]=lim\limits_{M\rightarrow \infty}
\frac{1}{M}\sum\limits_{l=1}^M f(x_{\{i\}\sim}^{(l)},x_{\{i\}}^{(l)})f(\tilde x_{\{i\}\sim}^{(l)},x_{\{i\}}^{(l)})
$$

$$x_{\{i\}\sim}^{(l)},x_{\{i\}}^{(l)}\ \mbox{and}\ \tilde x_{\{i\}\sim}^{(l)}$$
are independent samples.

### Polynomila Chaos expansion estimate
