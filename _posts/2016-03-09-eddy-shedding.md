---
layout: post
title: A feature-based loop current shedding prediction using logistic regression
tags: [Loop-current, eddy-shedding, logistic-regression]
---

> Loop current eddy is tracked using 17cm SSH contour. An classification algorithm 
> of the eddy shedding process is developed by tracking the SSH contour. For the 
> future loop current shedding event, an simple model based on logistic
> regression is presented.

## SSH contour tracking

<img src="/images/eddy-shedding/shedding_track.png">
The thin black contour is the 17cm SSH contour line and the blue stars are the
recorded searching points. The eddy shedding event is defined as the searching
points do not go over 25.5N.

### Tracking steps
Step1:  Obtaining the data that defines the contour lines. The following Matlab function will helps.
{%highlight matlab%}
[C h] = contour()
{%endhighlight%}

Step2:  initializing the contour tracking from some point (around 21N in this
case). 

Step3: Searching the closest new point (only less than 10 close points are searched) 
and repeating this searching process. Recording all the searched points.


### Results from a training set
798 HYCOM simulations with different initial conditions and wind forcings
are used as our training set. The simulating period is from May 1, 2010 to May
30, 2010. 4 initial condition EOF modes and 4 wind forcing EOF modes are
perturbed in this trainning set.

<img src="/images/eddy-shedding/shedding_statistics.png">
Caption: the number of eddy detached realizations out of the entire training
set. 

<img src="/images/eddy-shedding/shedding_statistics.png">
Caption: Histogram of each perturbation in the eddy detached realizations on
different day. The axis label for all boxes in the figure is on top right. 

### Logistic regression for prediction 




