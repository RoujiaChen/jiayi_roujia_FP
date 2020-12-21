---
title: "Unsupervised & Supervised Machine Learning"
date: 2020-12-21
published: true
tags: [clustering, prediction, machine learning, dataviz, altair]
excerpt: "This is the description of cluster analysis and prediction models."
altair-loader:
  altair-chart-1: "charts/cluster2_plot.json"
  altair-chart-2: "charts/cluster3_plot.json"

toc: true
toc_sticky: true
---

In the previous posts, we have viewed and analyzed the global situations in the four aspects indlucing drinking water sources, sanitation, vaccination, and under-five mortality. In order to further anlayze the the impact of WASH on child health, this post shows how clustering analysis helps us understand the situations in different countries and how prediction models help us predict child mortality based on drinking water sources, sanitation, and vaccination.

## Clustering

Firstly, we calculate the mean values for each country during 2010-2019, and use K-Means Clustering to find the clusters. To determine the number of clusters (k), we calculate the silhouette value for each k from 2 to 9. As the results shown below, k=2 and k=3 have outstanding results. Therefore, we further compare k=2 and k=3.

### k=2 vs k=3
To have a better understanding, we choose four indicators from the four aspects: 
* **Water_Improved**: Proportion of population using improved drinking water sources
* **Open_Defecation**: Proportion of population practising open defecation
* **DTP_Third**: Percentage of surviving infants received the third dose of DTP-containing vaccine
* **Child Mortality Rate**: Deaths (aged 1-4 years) per 1,000 live births

For each cluster, the mean values in these four aspects, together with cluster sizes, are calculated and compared. The results are as below:

When dividing into 2 clusters, it can be found that one cluster has very low child mortality rate, very high proportion of using improved drinking water sources, very low proportion of practising open defecation, and very high proportion of receiving DTP vaccination. In the contrast, another cluster has the opposite situations. In general, these two clusters may represent developed countries and less developed countries. When dividing into 3 clusters, basically the less developed countries are further divided into two clusters.

<div id="altair-chart-1"></div>
<div id="altair-chart-2"></div>

To conclude, we think our dataset can be well divided into three clusters, and they may represent different levels of country's development.

## Prediction Models
In this part, we use prediction models to perform supervised machine learning, trying to predict child mortality. Models include linear regression, decision tree, and random forest. Their performances are evaluated and compared by 10-fold cross-validation. 20% of the dataset is the test set, the remaining 80% is further divided into 90% training set and 10% validation set. The metrics used are R-squared and Mean Squared Error. Note: Here we use self-defined functions instead of GridSearchCV to speed up the calculations.

Initially, we plot the correlation matrix for all features. Since variables in the same aspect are highly correlated, we choose one indicator for each aspect


### Best model: Random forest
Among our three models, Random Forest has the best performance (R-squared = 0.8526 on the 20% test set). On the training set, R-squared for Random Forest is around 0.8 while it is around 0.7 on Decision Tree and 0.5 on Linear Regression. Among the features, drinking water sources is the most imfluencial feature.

<img src="charts/feature_importance.png" class="charts" alt=""> </div>
<img src="https://github.com/RoujiaChen/jiayi_roujia_FP/blob/master/charts/feature_importance.png" alt="">

![feature_importance]({{ site.url }}{{ site.baseurl }}/chartsfeature_importance.png)

### Conclusion
To conclude, we can use indicators in drinking water sources, sanitation, and vaccination to predict child mortality, and the accuracy is high. In particular, drinking water is the most important feature influencing the child mortality. To improve the living standards in less developed regions, especially for child health, better drinking water sources is essential.

## Notes

- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2020/week-13/blob/master/lecture-13A.ipynb) for the code that produced these plots.
