---
layout: post
title:      "XGBoost and Classification"
date:       2020-11-19 21:54:10 +0000
permalink:  xgboost_and_classification
---


Supervised learning classifications are a great machine learning tool.  Training the machine to look for the characteristics of a data set that make it a certain classification can really highlight the features of the dataset that sway the classification one way or the other.  There are many parameters and strategies that go into making these classifications work.  An extremely effecient tool to explore and handle these different strategies and parameters is XGBoost, which is Extreme Gradient Boosting.

Gradient Boosting is an ensemble method that creates a stronger classifier by identifying weak classifiers.  The data set is going to have correlations between the learners and the target variable.  Some of those correlations are going to be stronger the others.  Gradient boosting focuses more on the weaker correlations.  These weaker correlations cause errors in the iterative models and they help promote more correct predictors in the next iteration.  

XGBoost is the best and easiest to use.  It regularly provides great results from the training data set to the testing data set.  It is very simple to set all the parameters that are very similar to the parameters for decision trees.  This is because XGBoost uses decision trees as the ensemble method.  Here is a quick example on what the paramters are:
```
param = {
    'max_depth': 3,  # the maximum depth of each tree
    'eta': 0.3,  # the training step for each iteration
    'silent': 1,  # logging mode - quiet
    'objective': 'multi:softprob',  # error evaluation for multiclass training
    'num_class': 3}  # the number of classes that exist in this datset
```

Using GridSearch is a great accompaniment to XGBoost.  It is very simple to tune all the different hyperparameters to find the optimal settings that produce the results that can be determined as "best."  This leads to such a great facet of ensemble methods and XGBoost.  The feature importances report help visualize which learners were the strongest in classifying.  This not only helps in understanding how well the engineered features performed, but also could help in an EDA scenario when trying to see which features are important or not.  Since XGBoost is simple and efficient to run, a lot of time can be saved by using the classifier and checking feature importances to determine which columns of data should be further inspected.  

One scenario could be columns that are score very high in feature importance.  This can raise certain questions like, why is this feature so important? How does it relate to the target varaible?  If this column was dropped from the model , which columns would generate more feature importance?

This is such a great tool to have when really trying to, not only understand the data set, but also how the model is splitting the data into the classification target.
