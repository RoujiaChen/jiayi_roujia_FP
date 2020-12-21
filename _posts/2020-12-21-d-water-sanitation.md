---
title: "Drinking Water & Sanitation"
date: 2020-12-21
published: true
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "This is the description of drinking water sources and sanitation facilities."
altair-loader:
  altair-chart-1: "charts/chart_wat1.json"
  altair-chart-2: "charts/chart_wat2.json"
  altair-chart-3: "charts/chart_sani1.json"
  altair-chart-4: "charts/chart_sani2.json"
hv-loader:
  hv-chart-1: ["charts/choropleth_wat5yrAF.html", "600"]
  hv-chart-2: ["charts/choropleth_sani5yr.html", "600"] 
toc: true
toc_sticky: true
---

## Overview: Drinking Water and Sanitation Facilities

Given the goal of exploring the relationship between WASH and child health, this page will show the description of WASH across the world in the past 10 years.   

## Drinking Water

### Average Proportion of Population Using Different Drinking Water Sources

The stacked bar chart below shows the distribution of population in each continent using different drinking water sources. Luckily, most people around the world have access to improved drinking water facilities. However, there are about 25% of the population use unimproved drinking water sources, even surface water. 

<div id="altair-chart-1"></div>

### Time Trend and Population using Improved Water Resources by year/continent
The top line plot shows the change of average percentage of population using improved water resources in each continent through 2010 to 2017 (the data for 2018 & 2019 are still pending for updates). Europe has the highest percentage while Africa has the lowest. However, the percentage has been increasing from 2010 in Africa - more people can get access to improved drinking water there.

In addition to the percentage of population, we are also interested in the absolute amount of population affected by WASH. Thus the bar chart below shows the total population (in million persons) for the selected time period from the top line plot. Even though Asia doesn't have the highest proportion of population, it has the most amount of people drink water from improved sources.

<div id="altair-chart-2"></div>

### Choropleth of Improved Drinking Water Sources in Africa
Based on our previous analysis, Africa is the palce that shows an increase in the proportion of people using improved water sources. Then, we are curious about the geographical distribution of this index in this continent. Are there any cross-country differences?

<div id="hv-chart-1"></div>

Yes! Countries in the north and south have more access to improved drinking water sources, such as 99% in Egypt and 92% in South Africa. However, countries near the equator like Congo (Democratic Republic of) has limited access (only 51% of people).

## Sanitation

### Average Proportion of Population Living with Different Sanitation Facilities

The stacked bar chart below shows the distribution of population in each continent living different sanitation facilities. On average, most (over 50%) people around the world have access to improved sanitation facilities. However, it is thrilling to see about 20% of people in Africa still practise open defecation.

<div id="altair-chart-3"></div>

### Time Trend and Population Practising Open Defecation by year/continent

The top line plot shows the change of average percentage of population using practising open defecation in each continent through 2010 to 2017 (the data for 2018 & 2019 are still pending for updates). Africa has the highest percentage while Europe has the lowest. However, the percentage has been decreasing from 2010 in Africa - more people have got ride of open defecation from 2010 to 2017.

As for the absolute amount of population, the bar chart below shows the total population practising open defecation (in million persons) in the selected time period from the top line plot. Even though Asia doesn't have the highest proportion of population, it has the most amount of people living with the worst sanitation condition - in 2017, 420 million people.

<div id="altair-chart-4"></div>

### Choropleth of Improved Drinking Water Sources in Africa

Based on our previous analysis, Africa is the palce that shows an obvious decline in the proportion of people practising open defecation. The interactive choropleth below shows the geographical distribution of the proportion for each African country from 2010-2015. Are there any cross-country differences?

<div id="hv-chart-2"></div>

Compare the chropleth with the terrain of Africa (retrieved from google map), countries located in desert areas are more likely to have higher proportion of people practising open defectation, such as Niger and Chad.

<img src="charts/africa.png" alt="" width="338" height="340"></div>
