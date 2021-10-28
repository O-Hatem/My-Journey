---
toc: true
layout: post
description: Questions about ML problems like cleaning data, cross validation, etc
categories: [markdown]
title: ML Questions
---

# ML-related Questions

## What is Cross Validation and what is it used for?

Cross Validation is a statstical way to predict the accuracy of a machine learning model. It helps reduce the change of overfitting to the data and selection bias. it's used specially with small datasets where each data point may carry an important piece of information to help the machine learning model better predict.

### Types of Cross Validation:
Classification has two main broad types:
1. **non-Exhasutive Methods**. non-Exhaustive method doesn't compute all the ways of splitting data.

    1. **Holdout method**. this method word by dividing the data into two sets, training and testing sets. Usually the percentage is 80:20 or 75:25 for training and testing respcetivly.
    
    2. **K fold cross validation**. it's an improvment to the holdout method. it works by dividing the data into k folds, where training is performed on k-1 folds and testing is performed on 1 fold. then it chooses a different fold for testing while the rest for training, and so for till all folds are used as a testing fold once. Finally, it takes the average of all combination.
    
    3. **Stratified K fold cross validation**. There maybe a problem when using k fold CV when working on a classifcation problem. Where one fold can have a majority of a class resulting in selection bias for a particular fold. to prevent that stratified k CV is used to ensure that every fold consists balanced data between the class to avoid any bias in the data.

1. **Exhaustive Methods**. these are methods where is split the data into every possible combination of training and test sets.
    
    1. **Leave-P-out Method**. it works by having p data points as the test set and (n-p) as the training set. where p will be every combination of the data points in the original dataset. The higher the p, the more combinations there are, the more processing power needed.

    2. **Leave-one-out method**. it is a variance of the Leave-p-out method where p is equal to 1. it is much less exhaustive where the number of combinations is euqal to n.

3. **Rolling Cross validation**. Rolling cross validation is used for time series datasets. It makes sure the golden rule of time series probelms ("look at the past to predict the future") is not broken. it divides the data by a time frame and then train each split sequentially. e.g. 

```python
Training set: [1], test set: [2]
Training set: [1, 2], test set: [3]
Training set: [1, 2, 3], test set: [4]
.
.
Training set: [1, 2, 3, ..., n-1], test set: [n]
```


