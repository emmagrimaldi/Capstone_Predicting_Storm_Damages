

# EXECUTIVE SUMMARY 10/19/2018


## PROBLEM STATEMENT

The purpose of this study is to build a model able to predict the economic damage caused by a storm event in the US. The predictors would be: location, date, time of the day, magnitude, duration and spatial distance covered by the storm (info that weather forecast usually knows before the event actually takes place). 

## DATA

Observations of storm events in the US from 2000 up to June 2018 have been sourced from the National Climatic Data Center website (https://www1.ncdc.noaa.gov/pub/data/swdi/stormevents/csvfiles/). 
There were missing geographical information that I was able to retrieve through latitude and longitude. However, around 700 observations contained wrong lat and long values, that I was able to spot and fix thanks to other geospatial information available

## PRELIMINARY FINDINGS

There is no temporal trend in such phenomena over the years, however most of them happen in summer months, from June to August. As far as the time of the day is concerned, we see a trend of storms happening in the afternoon hours, with a peak around 4 and 5PM. Most phenomena last less than 1 hour, and despite Iowa is the State that has observed the greates number of phenomena, Texas is the State that has suffered the greatest cumulated economic damage since 2000. The economic damage distribution goes from 0 (not included) to $1.8B for the hails, and from  0 (not included) to $750M for thunderstorms. In both cases the distribution is dramaticaly left-skewed, for this reason I have transformed my target variable to be the logarithm of the damage, in order to obtain a distribution closer to Normal.

## METRICS AND FINDINGS

Two neural networks have been built, to predict the damage caused by either hails or thinderstorm winds, since the magnitude parameter has different measurement units for the two cases. Since in both cases I have a regression problem, the metric I am using is the R^2. 





