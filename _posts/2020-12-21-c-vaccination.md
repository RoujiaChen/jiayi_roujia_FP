---
title: "Vaccination"
date: 2020-12-21
published: true
tags: [dataviz, altair, hvplot, holoviews, vaccination, health]
excerpt: "This is the description of vaccination rates."
altair-loader:
  altair-chart-1: "charts/chart_vac2.json"
hv-loader:
  hv-chart-1: ["charts/chart_vac1.html", "400"] # second argument is the height
  hv-chart-2: ["charts/chart_vac3.html", "400"]
toc: true
toc_sticky: true
---
## Overview: Vaccination for Infants
**Immunization** is one of the most cost-effective public health interventions to date, averting an estimated 2 to 3 million deaths every year ([UNICEF](https://data.unicef.org/topic/child-health/immunization/)). Vaccination is another important perspective to be considered when we tried to compare the health status of children around the world. According to [WHO] (https://www.who.int/news-room/fact-sheets/detail/immunization-coverage), there are a series of recommended basic vaccination types, including Haemophilus influenzae type b (Hib), Meningitis A, Human papillomavirus (HPV), Hepatitis B (Hep_B), measles, polio and tetanus and pertussis vaccine (DTP). Out of these vaccination types, the UNICEF data includes the percentage of surviving infants who receive the third dose of **Hib**, **Hep_B, **DTP**, and **polio** and the coverage of the first dose of **measles**. 

## Year Trend: Average Vaccination Rates by Continent

The interactive plot below shows the percentage of surviving infants who were vaccinated, grouped by the type of vaccine and you can use the widgets to change the continent.

<div id="hv-chart-1"></div>

<div id="hv-chart-2"></div>


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
