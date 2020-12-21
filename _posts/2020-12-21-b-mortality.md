---
title: "Under-Five Mortality"
date: 2020-12-21
published: true
tags: [dataviz, altair, hvplot, holoviews,child_mortality]
excerpt: "This is the description of stillbirth, neonatal, infant, and child mortality rates."
altair-loader:
  altair-chart-1: "charts/chart_mor2.json"
altair-loader:
  altair-chart-2:"charts/chart_mor3.json"
hv-loader:
  hv-chart-1: ["charts/chart_mor1.html", "500"] # second argument is the height
toc: true
toc_sticky: true
---

## Overview: Under-five Mortality

According to [NUICEF](https://data.unicef.org/topic/child-survival/under-five-mortality/):
The global under-five mortality rate declined by 59 per cent, from 93 deaths per 1,000 live births in 1990 to 38 in 2019. Despite this considerable progress, improving child survival remains a matter of urgent concern. In 2019 alone, roughly 14,000 under-five deaths occurred every day, an intolerably high number of largely preventable child deaths. 

In this post, we divided the under-five mortality into [4 categories](https://data.unicef.org/topic/child-survival/neonatal-mortality/#:~:text=Definitions%20of%20indicators&text=Infant%20mortality%20rate%3A%20Probability%20of,expressed%20per%201%2C000%20live%20births.): 
* stillbirth (death before/during delivery) 
* neonatal mortality (deaths between birth and exactly 1 year of age)
* infant mortality (deaths during the first 28 days of life)
* child mortality (deaths during 1 year to 4 year of age)

All the mortality rates are in the unit of "deaths per 1000 living births".

## Year Trend for World Average Mortality Rates 

The chart below shows the cross-year change in world average mortality rates from 2010 to 2019. All rates present a decreasing trend, which means less infants and children have suffered from early-death. 
<div id="hv-chart-1"></div>


## Averages Mortality Rates in Different Continents

Even though the world average shows a decreasing trend, there might be a huge disparity across regions. Thus, the stacked bar chart below agregates the under-five motality rate by categories. It's obvious that Arican families suffered the most from child mortality and about 120 babies will die before the age of five. It's not suprising to see that European countries have the lowest under-five mortality compared to others.

<div id="chart_mor2.json"></div>

## Notes

- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2020/week-13/blob/master/lecture-13A.ipynb) for the code that produced these plots.
