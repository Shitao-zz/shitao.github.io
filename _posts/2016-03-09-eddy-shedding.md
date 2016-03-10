---
layout: post
title: A feature-based loop current shedding prediction using logistic regression
tags: [Loop-current, eddy-shedding, logistic-regression]
---

> Loop current eddy is tracked using 17cm SSH contour. An classification algorithm 
> of the eddy shedding process is developed by tracking the SSH contour. For the 
> future loop current shedding event, an simple model based on logistic
> regression is presented.

### SSH contour tracking

<img src="/images/eddy-shedding/shedding_track.png" class="floatpic">
The first step of SSH contour tracking is to obtain the data that defines the
contour lines. 
{%hightlight matlab%}
[C h] = contour()
{%hight%}

Next, initializing the contour tracking from some point (around 21N in this
case). Searching the closest new point (only less than 10 points are searched) 
and repeating this searching process. Recording the searching points.

The thin black contour is the 17cm SSH contour line and the blue stars are the
recorded searching points. The eddy shedding event is defined as the searching
points do not go over 25.5N.

### Results from a training set
<img src="/images/eddy-shedding/shedding_statistics.png" class="floatpic">

### Logistic regression for prediction 




