PROGRESS REPORT 10/07/18

The dataset contains over 11,000 observations of storm phenomena in the US occuring from 2000 up to 2017, that caused at least 50K of economic damage.

The predictors are spatial and temporal information, as well as description of the type of storm event and its magnitude. I engineered further features such as the duration of the events and the distance the storm traveled.

The dataset had some missing spatial information that I was able to retrieve by comparing the observation with the missing information to the closest one. There were also mistakes in longitude and latitude values that I spotted (commas in the wrong places), that I fixed.

The temporal data don't show any trend over the 17 years. Although it is evident that most part of the storm phenomena happened in the summer, with a peak in June. As far as the time of the day is concerned, most storms start in the afternoon around 5PM, a considerably smaller number of observations take place early in the morning. Most events don't last more than one hour.

Texas is the State that suffered more storms and highest cumulated economic damage, by far. In terms of casualties though, Alabama is the State with highest number of direct deaths since 2000.

First, I am trying to build a model that predicts the economic damage caused by a storm event.
I started modeling by choosing a Random Forest regression that gave me a 0.89 value of $R^2$ on the train set, but almost 0 on the test set. There is definitely an issue of multicollinearity among my predictors, but besides that, this is probably not the right model to go with.
I started modeling a neural network that definitely gives me more consistent results between train and test set, but there is a lot of tuning to do still. I intend to gridsearch to find the best value of my hyperparameters. In my next steps, I will also use a NN to predict the number of casualties and injuries.