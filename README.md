# From sudden success to long term fame: what is the secret?

## Abstract

Viral videos dominate the always-changing landscape of Youtube trends and many channels go through a brief but explosive moment of fame. While some are able to turn this sudden success into long-term engagement, others quickly sink into oblivion. What is then the winning strategy of these first lucky creators **(and do they even have any)**? Are there specific categories for which is easier to ride the wave of fame after the fast spike in visibility? Does consistency in posted content pay off? These and more questions will be answered by the study here presented. Indeed, channels in the YouNiverse dataset that have undergone a sudden increase in terms of views are identified through an extensive preproecssing and feature engineering. There are then split into the "keep-fame" and "lose-fame" populations. By employing logistic regression and propensity score matching and through other ADA tools, the two populations can be compared in an observational study and their differences can be highlighted.

## Research questions

Through our analysis we aim to gain meaningful insights on the strategies implemented by channels that gained sudden success and managed to keep their fame. Specifically, we want to answer the following questions:

* Is there a channel strategy that can consistently help keeping fame after becoming viral? **In other words, can intrinsic data features explain the phenomenon of YouTube long term success or is it only related to other aspects (e.g. social trends, luck, creator's personality)?**
* Are certain categories of videos prone to maintaining fame more than others?
* Are strategies different across categories? For instance, do successful channels vary their content before and after becoming viral (e.g. the same or different categories are represented in their videos)?
* Apart from content, what other strategies can be adopted (frequency of publication, videos length..)?

## Repository organization

All the notebooks delivered for milestone 3 are contained in the folder `milestone_3`, while the old ones from milestone 2 have been moved to `milestone_2`.  
In milestone 3, the notebooks are organized as follows:

* `data_exploration.ipynb` = dataset (timeseries, channel dataframes and metadata) exploration through varied visualizations;
* `preprocessing_step_1.ipynb` = fundamental step performed to extract new variables to enrich the dataset and allow for detailed filtering;
* `preprocessing_step_2.ipynb` = definition of various metrics (feature engineering) and extensive additional filtering to correctly identify the two populations. Logistic regression, propensity score matching.
* `analysis.ipynb` = observational study and in-depth analysis;
* `animation.ipynb` = notebook to display 1 animation in the data story;

## Additional notes

* As colourblindness is a quite spread condition (it affects about 1 in 10 males) most visualizations in these notebooks were made with appropriate palettes;
* We were planning to extract subcategories by processing semantic clustering on video titles and their tags in order to implement a more detailed content analysis. This had been started in the `subcategories_preprocessing_and_clustering.ipynb` notebook uploaded for milestone P2. However, even Friday, December 23, 2022 8:21 PM, after letting the computer run for a few days, only a small fraction of the data had been processed. As our model would not have been fitted properly, we had to resign from our initial idea. Still, we would like to point out to future studies that in conditions of more time and RAM space it would be an enriching analysis to carry out.

## Data story

The data story is available [here](https://epfl-ada.github.io/ada-2022-project-adangerousteam/) and it is also contained in the `docs` folder.

## Organization within the team

* Teammate 1 and 2: preprocessing and visualization
* Teammate 3 and 4: analysis and datastory
  
