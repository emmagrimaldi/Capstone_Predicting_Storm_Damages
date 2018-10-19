

# EXECUTIVE SUMMARY 10/19/2018


## PROBLEM STATEMENT

As weather phenomen are getting stronger in nature because of the rising temperatures, I thought it was interesting to work on a business problem involving storm events and related economic damage. 

The purpose of this study is, in fact, to build a model able to predict the economic damage caused by a storm event in the US. The predictors would be: location, date, time of the day, magnitude, duration and spatial distance covered by the storm (info that weather forecast usually knows before the event actually takes place). 

## DATA

Observations of storm events in the US from 2000 up to June 2018 have been sourced from the National Climatic Data Center website (https://www1.ncdc.noaa.gov/pub/data/swdi/stormevents/csvfiles/). 
There were missing geographical information that I was able to retrieve through latitude and longitude. However, around 700 observations contained wrong latitude and longitude values, that I was able to spot and fix thanks to other geospatial information available.
Other features such as duration or distance traveled by the phenomenon have been engineered.


## PRELIMINARY FINDINGS

There is no temporal trend in such phenomena over the years, however most of them happen in summer months, from June to August. As far as the time of the day is concerned, we see a trend of storms happening in the afternoon hours, with a peak around 4 and 5PM. Most phenomena last less than 1 hour, and despite Iowa is the State that has observed the greates number of phenomena, Texas is the State that has suffered the greatest cumulated economic damage since 2000. The economic damage distribution goes from 0 (not included) to $1.8B for the hails, and from  0 (not included) to $750M for thunderstorms. In both cases the distribution is dramaticaly left-skewed, for this reason I have transformed my target variable to be the logarithm of the damage, in order to obtain a distribution closer to Normal.

## METRICS AND FINDINGS

Two neural networks have been built so far, to predict the damage caused by either hails or thinderstorm winds, since the magnitude parameter has different measurement units for the two cases. Since these are regression problems, the metric I am using is the R^2. The hyperparameters are being optimized through a GridSearch

With ~6,000 observations, it seems easier to predict hails damage, but the model is still  overfitting my train set.
The model that's predicting thunderstorms damage is training on over 26,000 observations and in this case it is still overfitting, and it is performing worse than the hail model. 

The reason why it is not easy to predict such target, is caused by many reasons. Tha variance of the target is huge, and there is no direct correlation between any of the predictors and the such target. On top of that, the economic damage caused by a storm depends on many other things that are not registered in my observations. For example: what is the distance between the storm and the closest populated area? What is the status of the infrastructure where the storm happened? Were people alerted before it happened? There are so many other things to consider when evaluating these phenomena that have a huge impact, besides the parameter characterizing the storm itself.

## NEXT STEPS

For this reason, in the next few days I will try to improve my model and rather than trying to predict the exact amout of the economic damage, I will transform this into a classification problem. I will create ranges for the economic damage and will try to predict which bin every observation falls into. This way, rather than predict the exact amount, I can probably more accurately predict what "class" of damage is going to occurr after a weather event like this.

## REPOSITORY

The code can be found in the Capstone_code notebook. The Capstone_interactive_plot notebook includes the code to generate an interactive plot, the result can be found at this link: https://plot.ly/~emmagrimaldi/2/storm-events/

