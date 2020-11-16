---
layout: post
title:      "Recommender Systems and Collaborative Filtering"
date:       2020-11-16 14:06:36 +0000
permalink:  recommender_systems_and_collaborative_filtering
---


Collaborative Filtering is so special in how it utilizes users previous ratings to provide feedback to new users.  If user A rates  certain content highly, and user B rates that same content similarily, then a new user, user C will be recommended to that content if they rate a piece of that content similarily to A and B.

Its so simple to implement as well.  All that is really needed is a matrix that has the user, the item, and the rating.  It's very little data to clean, provided that there aren't any missing values or incorrect data types.  

Sparsity is widely considered an issue with Colloborative Filtering, however, using Singular Value Decomposition in the Matrix Factorization approach, sparsity does not become an issue.  This is accomplished by extracting latent factors.

Matrix Factorization sounds complex but is actually a simple tool to use when dealing with sparsity.  There is always going to be sparsity in the recommender system database.  If every user rated every item, then there would be no need for any recommendations.  Since there will be sparsity, dimensionality reduction methods like SVD help deal with sparsity.

SVD essentially takes any matrix and factorizes it into 3 matrices, known as the left singular vectors, the singular values, and the right singular vectors.  This means that each user and item is mapped into a latent space that has a lower dimension, making the relationships between user and item more directly comparable.  
