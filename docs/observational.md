---
layout: default
title: Propensity score matching
description: Observational study
---
The **YouNiverse** dataset is composed of what we call "found data": data that was collected for another purpose and that we are using for our analysis. As this is a very common practice in data science, and it is often the case that the data is not perfectly suited for the task at hand. In our analysis we want to compare two distinct populations (**keep fame** and **lose fame**) of channels, and we want to understand what are the features that distinguish them. Since we want to determine which factors have an impact on the ability of a channel to maintain its fame and because the data does not originate from a controlled experiment (i.e. we cannot control the factors that influence the fame of a channel), we need techniques suited for observational studies to do our analysis. In particular we need to make sure that the two populations are comparable and that the data is not biased. This is where the propensity score matching comes in. The following causal diagram illustrates the problem we are trying to solve:

![causal diagram](./images/causal_diagram.png)

We identified (xyz) as confounders that could bias our analysis. To solve (or better, mitigate) this problem, we calculated the channel's propensity score: a measure of the likelihood of a channel to receive the treatment (i.e. to be in the **keep fame** population). To compute the propensity scores we used a logistic regression model trained on a balanced subsample of the two populations obtained after preprocessing and filtering. Using the similarity as a measure of the connection weight between two channels in a potential pairing, we created a bipartite graph (see figure) that connected each channel in the **lose fame** population to all the channels in the **keep fame** group that belong to the same channel category. This way we can be sure that the two populations are comparable, and that the data is not biased by the confounding factors considered. The following figure illustrates the process of propensity score matching:

[back](./)
