# Kaggle Bike Sharing Demand Challenge

For this challenge, I used a Jupyter notebook running on Python 3. 

I started by plotting the training data in order to better understand the data, as well as to build intuition regarding the data's behavior. Part of this included looking at the plotted timeseries with varying levels of granularity, and plotting the "dependent" variable (counts of bikes rented every hour) against the various "independent" variables provided (workday, weather, etc...) Looking at the plotted data revealed that counts increase throughout the two years, and confirmed that certain patterns emerge depending on the hour of the day. This led to the creation of two new "features" to include in the model: hour (which represents the hour of the day) and year (to grossly account for the increase in rental counts from 2011 to 2012).

Once I felt satisfied with this, I split the training data into a pure training set and a control set to use in measuring model accuracy. I used scikit-learn to first create a linear regression model, as a first attempt, then moved on to a ridge regressor, another linear model that normalizes features that may be correlated. Finally, I chose a random forest regressor since it's a reliable tool for cases like this. I explored a few different parameter settings, focusing on number of estimators, max depth, and minimum number of samples required before a split, and selected the model with the best r^2 score (closest to 1) in order to predict the test data's rental counts and save them to predicted.csv.

The Kaggle challenge can be found at: https://www.kaggle.com/c/bike-sharing-demand

