# From sudden success to long term fame: what is the secret?

## Abstract 

Viral videos dominate the always-changing landscape of Youtube trends and many channels go through a brief but explosive moment of fame. While some are able to turn this sudden success into long-term engagement, others quickly sink into oblivion. What is then the winning strategy of these first lucky creators (and do they even have any)? Are there specific contents for which is easier to ride the wave of fame after the fast spike in visibility? 
These and more questions will be answered by the study here presented. Indeed, channels in the YouNiverse dataset that have undergone a sudden increase in terms of views are identified and then split into the “keep-fame” and “lose-fame” populations. By defining and computing various metrics, employing feature engineering and logistic regression, the two populations can be compared in an observational study and their differences highlighted. 

## Research questions

Through our analysis we aim to gain meaningful insights on the strategies implemented by channels that gained sudden success and managed to keep their fame. 

Specifically, we want to answer the following questions:

* Is there a channel strategy that can consistently help keeping fame after becoming viral? In other words, can intrinsic data features explain the phenomenon of YouTube long term success or is it only related to other aspects (e.g. social trends, luck, creator's personality)?
* Are certain (sub)categories of videos prone to maintaining fame more than others? 
* Is content strategy relevant in keeping popularity? Are strategies different across categories? For instance, do successful channels vary their content before and after becoming viral (e.g. same or different subcategories)? 
* Apart from content, what other strategies can be adopted (frequency, length, publishing time of video)?

*Note:* We define subcategories as semantic clusters based on video titles and their tags. As the approach is purely data driven, videos of the same subcategory, may or may not belong to the same broad category (e.g. “Gaming”, “Howto & Style”). 

## Methods

In order to carry out our analysis, we first need to identify the two populations of interest: the channels that lost the gained popularity after a peak of views and those who managed to keep it. We will then perform an observational study on these two groups. 

**Step 1: Identification of the two populations.** Preprocessing and filtering of the `‘df_timeseries_en.tsv.gz’` and `‘df_channels_en.tsv.gz’` dataframes is done to create the two defined populations. Using timeseries data, different metrics are computed for this purpose, allowing identification of the channels of interest (for more information see `preprocessing_population_selection.ipynb`). Here, for each population, we show the cumulative views, views and delta_views for two representative channels obtained with this method: 
| ![channellose](https://user-images.githubusercontent.com/114160174/202800175-b7568d69-1e86-4fd7-b427-26d8f240c434.jpg) | 
|:--:| 
| Example of 'lose-fame' channel. We observe that after a sudden increase, the ‘views’ remain constant until the end of the observation period. |

| ![channelkeep](https://user-images.githubusercontent.com/114160174/202800178-76af65a3-6089-4226-9893-f10e7813f323.jpg) | 
|:--:| 
| Example of 'keep-fame' channel. For this channle, we detect loss of visualizations in the period following the rapid peak in views. |

**Step 2: Preliminary analysis.** Data exploration of the two populations to understand useful features that could be used to compute the propensity scores. Furthermore, textual features extraction and clustering of the `‘yt_metadata_en.jsonl.gz’` file are done to define subcategories of the videos which will be used in Step 4 (did in advance as it is computationally intensive). 

**Step 3: Observational study.** Feature engineering and computation of the propensity scores through logistic regression. Matching datapoints of the two populations using bipartite graphs will follow to define a dataframe with paired channels to do further analyses and comparisons. 

**Step 4: Final analysis.** Two tasks can be identified in this step. 

  **4.1** Exploration of the subcategories, specifically those related to the channels that belong to the two defined populations: some of the objectives here are to understand if some subcategories are more frequent in one of the two, and if channels changed and varied the content (subcategory) of videos after success. 
  
  **4.2** Comparisons among the two groups of publication strategies, such as the frequency of video publishing, the length of the videos, their title characteristics, and level of engagement, with the goal of detecting significant differences (if there are any). 

**Step 5**: GitHub site building and datastory redaction. 

## Proposed timeline

* **28/10/2022: P2 Release**
* *Week 1:* Selection of ideas and data exploration
* *Week 2:* Populations identification and clustering of video subcategories
* *Week 3:* Initial analysis and start of metric computation
* **29/11/2022: P2 Deadline**
* *Week 4-5:* Feature engineering 
* **02/12/2022: P3 Release**
* *Week 5-6:* Propensity scores computation and matching
* *Week 7:* Final analysis and data visualization
* *Week 8:* Building site and data story
* **23/12/2022: P3 Deadline**

## Organization within the team

We plan to organize the work equally between teammates and to work in pairs on every task. Specifically:
* Teammate 1 and 2: Step 1, 3
* Teammate 3 and 4: Step 2, 4
  
Everyone will work together on the GitHub site and on the datastory

## Scripts

We upload two preprocessing notebooks:
* `preprocessing_population_selection.ipynb`: code with the identification of the two populations and initial analysis
* `subcategories_preprocessing_and_clustering.ipynb`: code with the textual feature extraction and clustering set up 

