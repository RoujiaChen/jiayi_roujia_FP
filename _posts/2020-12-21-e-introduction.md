---
title: "Introduction"
date: 2020-12-21
published: true
tags: [dataviz, pandas, python, UNICEF, WASH]
excerpt: "This is the introduction of WASH and this project."
toc: true
toc_sticky: true
---


## Incentive and Background

Evidence has shown that Water, Sanitation, and Hygiene (WASH) has a huge impact on  diarrhoea, nutrition, complementary food hygiene, female psychosocial stress, violence,
maternal and newborn health, menstrual hygiene management, school attendance, oral vaccine performance, and neglected tropical diseases. Together, these areas cover the most significant sector outcomes associated with the distinct life course phases that  the United Nations Children’s Fund (UNICEF) seeks to help to address through its WASH activities. 

![unicef]({{ site.url }}{{ site.baseurl }}/assets/images/unicef.png)

The purpose of this project is to:

* 01. Describe the time trend and cross-contient & cross-country differences in WASH (using indicators of drinking water and sanitation facility quality);
* 02. Describe an indicator of child health: under-five mortality;
* 03. Include and describe the other factor that might influence child health: infant immunization coverage;
* 04. Use unsupervised and supervised machine learning to study the interaction between child mortality, immunization, and WASH.


## Data Source

There are several data sources used in this project:

* WASH, immunization, mortality data from [UNICEF Data Warehouse](https://data.unicef.org/dv_index/)
* World map geometry data from [datahub](https://datahub.io/core/geo-countries/r/countries.geojson)
* World population data from [World Bank](https://data.worldbank.org/indicator/SP.POP.TOTL)
* Country code data from [UN](https://unstats.un.org/unsd/tradekb/knowledgebase/country-code)


## Data Processing

### Data cleaning

The raw dataset from UNICEF has 723330 rows in long format. We started by making the data type consistent for 'year' and keep those years of our interest (2010 and onward, because earlier years contain many missings). Next, we convert the dataframe to a wide format, with country and year as the index and all indicators are in seperate columns. One big challenge was the missing values in the raw dataset were suprisingly numerous. We treated the missing value by droping columns with 30% or more missing values. 

### GeoDataFrame
For the purpose of analyzing the geospatial features of variables, we wanted to merge in the geometries for each country. However, one difficulty was the country names in the UNICEF data is slightly different from the names in the geometry data (this is a common issue when doing country data). Thus, we found another table of country name and country code from UN's dataset (the country names should be consistent with ones in the UNICEF data), and merged in the country code to the cleaned dataset. Lastly, geometries were added by merging the geo-dataframe with the cleaned dataframe using the country code as the key.

### Feature selection
As discussed in the first part, after dropping columns that are too imcomplete to be analyzed, we have to determine our interested variables based on the data available. We found that remaining indicators on child mortality, immunization, and WASH-related variables show an acceptable non-missing value proportion and also matches our initial research interest. Thus, we renamed columns in this dataframe (a geo dataframe with country geometries) to be more succint and now it is ready for visualization and machine learning.

```python
col_list = ['Region', 'Year', 'geometry', 'Continent_Name',
           'Stillbirth rateTotal', 'Neonatal mortality rateTotal', 'Infant mortality rateTotal',
           'Child mortality rate (aged 1-4 years)Total',
           'Proportion of population using improved drinking water sourcesTotal',
           'Proportion of population using unimproved drinking water sourcesTotal',
           'Proportion of population using surface waterTotal',
           'Proportion of population practising open defecationTotal',
           'Proportion of population using improved sanitation facilitiesTotal',
           'Proportion of population using unimproved sanitation facilitesTotal',
           'Percentage of surviving infants who received the first dose of measles-containing vaccineTotal',
           'Percentage of surviving infants who received the third dose of DTP-containing vaccineTotal',
           'Percentage of surviving infants who received the third dose of Hib-containing vaccineTotal',
           'Percentage of surviving infants who received the third dose of hep B-containing vaccineTotal',
           'Percentage of surviving infants who received the third dose of inactivated polio-containing vaccineTotal']
df_final = df_countries[col_list]

# Rename the columns
df_final.columns = ['Country', 'Year', 'geometry', 'Continent', 
                   'Stillbirth_Mor', 'Neonatal_Mor', 'Infant_Mor', 'Child_Mor',
                   'Water_Improved', 'Water_Unimproved', 'Water_Surface',
                   'Open_Defecation', 'Sanitation_Improved', 'Sanitation_Unimproved',
                   'Measles_First', 'DTP_Third', 'Hib_Third', 'Hep_B_Third', 'Polio_Third']
```
