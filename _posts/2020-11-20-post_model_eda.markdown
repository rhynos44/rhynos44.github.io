---
layout: post
title:      "Post Model EDA"
date:       2020-11-20 07:58:43 +0000
permalink:  post_model_eda
---


Machine Learning models are so useful in a data scientists toolbox.  The greatest facet of machine learning is the questions that can be answered.  For example, in a classification model, why were certain features more important than others?  What did the machine see in this feature that swayed data to be classified the way it was classified?  Diving into these questions can really help understand the data set and the model's results.

Take this for example, 

```
data = pd.DataFrame(data=values, index=keys, columns=["score"]).sort_values(by = "score", ascending=False)
data.plot(kind='barh')
```


![](https://i.stack.imgur.com/Iy33M.pnghttp://)

This chart shows the output of the feature importances from a data set.  Age is quite visibly a strong feature.  Would the model still be able to accurately classify without this feature? This would be a good question to explore, and it would be very easy to just drop the column and run the model again.  Then take a look at the feature importances again and interpret the results.

Another thing to look at is how age interacts with the other columns.  The data from the above example is from the traditional titanic dataset.  So did age have anything to do with the class of the passenger? Were there more of one gender in the different age groups? These kind of questions can really take dataset exploration to the next level, and they also really help interpret the model's results.

