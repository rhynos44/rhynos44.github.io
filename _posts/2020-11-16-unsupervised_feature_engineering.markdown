---
layout: post
title:      "Unsupervised Feature Engineering"
date:       2020-11-16 19:58:58 +0000
permalink:  unsupervised_feature_engineering
---


For the capstone project, I wanted to look at mortgage data and see if I can classify it into simple mortgage products.  This classification would enable me to look at the features that were most useful in the model.  The dataset consisted of multiple categorical variables that proved to be quite the bother when dimensionality is concerned.  This is what sparked the idea to use unsupervised learning to help with engineering features to enhance a supervised learning model.


### Dimensionality with Categorical data

Right off the bat, in the initial inspection of the data, it was quite noticeable how much categorical data was present.  The first few columns consisted of codes that related to geographical data.  These codes could be used to look up the state, county, and even census tract that the mortgage property was located.  The states also included US territories, so there were more than just 50 unique codes.  The codes were assigned alphabetically so Alabama was code 01, Alaska code 02 .....etc. In order to assist the machine in deciphering this code system I decided to create dummy variables that simpy denoted a 1 if that mortgage property was in that state and a 0 if it was not.  This was the simplest approach to the problem, and it created over 50 additional columns.

This is where I thought to employ KMeans to try and get an optimal amount of clusters to group the data.  I was skeptical about how well this would work since the matrix would contain mostly zeros and very few 1 values.  How would KMeans be able to measure distances with such low magnitudes? Overall, I was able to get 9 clusters just from the state code.  That means that I reduced the dimensionality from over 50 columns to just 9.  

Once this was passed through the classifier, the feature importances determined that this wasn't that useful of a feature relative to the other features.  I think this is because the KMeans was unable to discern any meaningful distances between all the state codes.  KMeans was able to cluster successfully, but it didn't have any value to the model.  This led me to believe that the geographical data itself wasn't valuable to the classification problem and that in itself made it worth the effort.

## Final thoughts

Dimensionality with categorical data is always going to present a problem in large supervised learning problems.  Using unsupervised learning is an excellent way to attempt to attack this problem.  In the future, when presented with a similar problem, I think I will always try to cluster and then run in a simple baseline model to determine its usefulness.  
