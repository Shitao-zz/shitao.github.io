---
layout: post
title: A feature-based loop current shedding prediction using logistic regression
tags: [Loop-current, eddy-shedding, logistic-regression]
---

> Loop current eddy is tracked using 17cm SSH contour. A classification algorithm 
> of the eddy shedding process is developed by tracking the SSH contour. For the 
> future loop current shedding event, an simple model based on logistic
> regression is presented.

## SSH contour tracking

<img src="/images/eddy-shedding/shedding_track.png">

The thin black contour is the 17cm SSH contour line and the blue stars are the
recorded searching points. The eddy shedding event is defined as the realization
in which the searching points do not go over 25.5N.

### Tracking steps

-Step1: Obtaining the data that defines the contour lines. 
-Step2: Initializing the contour tracking from some point (around 21N in this case). 
-Step3: Searching the closest new point (only less than 10 close points are searched) 
and repeating this searching process. Recording all the searched points.

### Results from a training set
798 HYCOM simulations with different initial conditions and wind forcings
are used as our training set. The simulating period is from May 1, 2010 to May
30, 2010. 4 initial condition EOF modes and 4 wind forcing EOF modes are
perturbed in this trainning set.

<img src="/images/eddy-shedding/shedding_statistics.png">

Caption: The cumulative number of eddy detached realizations as a function of time. 

<img src="/images/eddy-shedding/perturbation.png">

Caption: Histograms of each perturbation in the eddy detached realizations at
different time. The axis label for all boxes in the figure is on top right. 

## Logistic regression for prediction 
The objective of this analysis is to construct a simple model which estimates
the probability of an eddy shedding event given the initial perturbations.  Whether the eddy
detached in a specific simulation is a binary problem that can be expressed in 0
or 1. Here, we build a simple logistic regression model, also called generalized
linear models, to achieve this goal.

At a specific day, a 1\*798 binary vector (whether eddy detachment occurs in the
trainning set) and a 8\*798 perturbation vector are used to calculate the optimal
coefficients for logistic regression model.

We can estimate the probability of eddy shedding event from a specific
perturbation setup when the optimal coefficients are available.

<img src="/images/eddy-shedding/logistic_regression.png">

Caption: Marginal probability of eddy shedding event associated with different
initial perturbations derived from a trained logistic regression model.

