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
**Immunization** is one of the most cost-effective public health interventions to date, averting an estimated 2 to 3 million deaths every year ([UNICEF](https://data.unicef.org/topic/child-health/immunization/)). Vaccination is another important perspective to be considered when we tried to compare the health status of children around the world. According to [WHO](https://www.who.int/news-room/fact-sheets/detail/immunization-coverage), there are a series of recommended basic vaccination types, including Haemophilus influenzae type b (Hib), Meningitis A, Human papillomavirus (HPV), Hepatitis B (Hep_B), measles, polio and tetanus and pertussis vaccine (DTP). Out of these vaccination types, the UNICEF data includes the percentage of surviving infants who receive the third dose of **Hib**, **Hep_B**, **DTP (DTP-3)**, and **polio** and the coverage of the first dose of **measles**. 

## Year Trend: World Average Vaccination Rates for Infants

The chart below shows the world average vaccination rate for infants. In general, more than 80% of infants across the world can receive the recommended immunization. The coverage rates for DTP and polio are higher than other types.

<div id="hv-chart-2"></div>

The interactive plot below shows the percentage of surviving infants who were vaccinated, grouped by the type of vaccine and you can use the widgets to change the continent. The cross-continent disparity in infant immunization is quite large, for example, about 90% of infants can receive immunizations in Europe and north America while only 80% of infants are immunized in Africa. The most common immunization types also differ across regions, DTP-3 which is regarded as the main indicator of immunization service quality by [UNICEF](https://data.unicef.org/topic/child-health/immunization/) is not the most common immunization in South America (measles is the most common).

<div id="hv-chart-1"></div>


## DTP-3 as the main indicator: Vaccination rate of DTP-3 across countries, 2019

Using DTP-3 as the main indicator of immunization service quality, we want to further explore the infant vaccination situation in each country. The chart below shows the earliest (2019) vaccination rate of DTP-3 across countries. Each circle represents one country, which is colored by continents, located according to the centroid coordinate, and sized by the percentage lower than 2019 world average. Large circles appear in Arica, Central and South America, Eastern Europe, Western and South Asia, and Oceania, which means that these areas' DTP-3 coverage rates are far lower than the world average level.

<div id="altair-chart-1"></div>

