---
layout: default
title: Preprocessing
description: Painful but necessary
---
Firstly, we discarded all the channels that had an observation period shorter than one year. 
Then,through a sliding window of 5 datapoints we were able to define a metric called **"growth_rate"**. This metric was used later to identify the channels with the fastest growth and the date of their fame gain. It captures the rate of increase (or decrease) in terms of growth for each channel during the 5 weeks considered within the window. A high "growth_rate" means that the datapoint considered is associated to a rapid increase in the previous month, while a negative value to a fast decrease. For its calculation, we compared the views curve to a linear interpolation between the ends of the window by computing the area between the two curves. Normalization was then applied in order to make comparisons possible. It's relevant to note that the first 12 and the last 14 datapoints of each channel period of observation were not considered for the computation of this metric, as they could have coincided with the beginning or the end of the channel's life, which is meaningless for our analysis.


[back](./)

