---
layout: default
---

# Why Youtube?

Viral videos dominate the always-changing landscape of Youtube trends and many channels go through a brief but explosive moment of fame. While some are able to turn this sudden success into long-term engagement, others quickly sink into oblivion. What is then the winning strategy of these first lucky creators (and do they even have any)? Are there specific contents for which is easier to ride the wave of fame after the fast spike in visibility? These and more questions will be answered by the study here presented, based on the [**YouNiverse**](https://github.com/epfl-dlab/YouNiverses) dataset, a large collection of channel and video metadata from English-language YouTube. A first introduction to the dataset, as well as the exploratory analysis is available in [its dedicated page](dataset.html).

<figure>
  <img src="assets\img\cover.jpg" style="width:100%">
  <figcaption align = "center">
    <b>YouTube viral videos</b>
  </figcaption>
</figure>

[observational](./observational.html)
[observational](./dataset.html)

Youtube is the most popular video sharing platform in the world, with over 2 billion users and 500 hours of video uploaded every minute. It is also the second most popular search engine, after Google. Therefore it’s deemed as a great starting point to understand how creators can exploit sudden and exponential growth. We worked on the file `df_channels_en.tsv.gz` and the `df_timeseries_en.csv.gz`. The first contains data related to the channels, the second contains data related to time series. We have a data point for each channel and each week.

From YouNiverse, we extracted channels that have undergone a sudden increase in terms of views and then split these into the **“keep-fame”** and **“lose-fame”** populations.

## How did we proceed?

Firstly, in order perform our analysis, important preprocessing steps had to be carried out in order to extract new variables to enrich the dataset and allow for detailed filtering. This step is described in detail in the [preprocessing](./preprocessing.html) section.

Moreover, through feature engineering, we defined various metrics with the goal to detect 
channels that had undergone a sudden success and later to draw apart the two desired 
populations. The antecedent preprocessing revealed itself as fundamental, since it allowed us to 
assign to each channel the maximum growth rate and the associated timepoint at which the 
views peaked. The defined metrics are described in detail in the [metrics](./metrics.html) section.

We later defined thresholds to only select those channels that had a very steep sudden growth 
and then discarded all the ones that before growing rapidly displayed an abrupt decrease in 
views. 
Finally, we were able to distinguish the two populations by thresholding upon the growth value 
and discarding all the channels that had lost or gained fame again before the end of the 
observation period. 
At this point, having removed all the examples that could have biased our experiment, we were 
now able to perform propensity score matching. We picked out all the column variables to be used as regressors:
* "subscribers_cc";
*  "videos_cc";
*  "subscriber_rank_sb";
*  "weights";
*   "growth_rate";
*    "variability"; 
* "growth_steepness".

We later standardized them. Moreover, we converted the 
categorical variables into dummy indicators. We computed the propensity scores and added 
them to the identified keep_fame and lose_fame populations. This led to 75 matched pairs to be 
used for the ensuing analysis.

It must be highlighted that for the final analysis we selected various features and then performed 

 creators stay consistent with their content or try to adapt it to the interests of their 
newly-found large audience? To answer this question, we analysed the features of each channel 
before and after going viral. To avoid bias, we only selected the channels that had videos before 
and after their peak. We therefore ended up with 65 and 63 channels for each population

## What did we find?


Text can be **bold**, _italic_, or ~~strikethrough~~.

['Link to another page](./another-page.html).


```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
