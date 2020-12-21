---
title: "Unsupervised & Supervised Machine Learning"
date: 2020-12-21
published: true
tags: [clustering, prediction, machine learning, dataviz, altair]
excerpt: "This is the description of cluster analysis and prediction models."
altair-loader:
  altair-chart-1: "charts/cluster1_plot.json"
  altair-chart-2: "charts/cluster2_plot.json"

toc: true
toc_sticky: true
---

In the previous posts, we have viewed and analyzed the global situations in the four aspects indlucing drinking water, sanitation, vaccination, and under-five mortality. In order to further anlayze the the impact of WASH on child health, this post shows how clustering analysis helps us understand the situations in different countries and how prediction models help us predict child mortality based on drinking water sources, sanitation, and vaccination.

## Clustering

Firstly, we calculate the mean values for each country during 2010-2019, and use K-Means Clustering to find the clusters. To determine the number of clusters (k), we calculate the silhouette value for each k from 2 to 9. As the results shown below, k=2 and k=3 have outstanding results. Therefore, we further compare k=2 and k=3.

### k=2 vs k=3
To have a better understanding and better visualization, we choose four indicators from the four aspects: 
* *Water_Improved*: 
* *Open_Defecation*:
* *DTP_Third*:
* *Child Mortality Rate*:
For each cluster, the mean values in these four aspects, together with cluster sizes, are calculated and compared. The results are as below:

When dividing into 2 clusters, it can be found that one cluster has very low child mortality rate, very high proportion of using improved drinking water sources, very low proportion of using open defecation, and very high proportion of receiving DTP vaccination. In the contrast, another cluster has the opposite situations. In general, these two clusters may represent developed countries and less developed countries. When dividing into 3 clusters, basically the less developed countries are further divided into two clusters.

<div id="altair-chart-1"></div>
<div id="altair-chart-2"></div>

To conclude, we think our dataset can be well divided into three clusters, and they may represent different levels of country's development.

## Prediction Models

### Feature selection


### Modeling

### Best model: Random forest

## Notes

- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2020/week-13/blob/master/lecture-13A.ipynb) for the code that produced these plots.
