---
title: "Drinking Water & Sanitation"
date: 2020-12-21
published: true
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "This is the description of drinking water sources and sanitation facilities."
altair-loader:
  altair-chart-1: "charts/chart_sani1.json"
  altair-chart-2: "charts/chart_sani2.json"
  altair-chart-3: "charts/chart_wat1.json"
  altair-chart-4: "charts/chart_wat2.json"
hv-loader:
  hv-chart-1: ["charts/choropleth_sani5yr.html", "500"] # second argument is the height
  hv-chart-2: ["charts/choropleth_wat5yrAF.html", "500"]
toc: true
toc_sticky: true
---

### Overview: Drinking Water and Sanitation Facilities

Given the goal of exploring the relationship between WASH and child health, this page will show the description of WASH across the world in the past 10 years.   

### Drinking Water

## Average Proportion of Population Using Different Drinking Water Sources

The stacked bar chart below

<div id="altair-chart-1"></div>

This was produced using Altair and embedded in this static web page. Note that you can also display Python code on this page:

```python
import altair as alt
alt.renderers.enable('notebook')
```

## HvPlot Example

Lastly, the measles incidence produced using the HvPlot package:

<div id="hv-chart-1"></div>

## Notes

- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2020/week-13/blob/master/lecture-13A.ipynb) for the code that produced these plots.
