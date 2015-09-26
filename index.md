---
title       : Iris Species Prediction
subtitle    : A web applet to predict Iris species by metric attributes
author      : Ronit Rudra
job         : Budding Data Scientist
framework   : io2012       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## About the Applet

The Iris plant is a type of plant characterized by showy and colorful flowers. This applet was designed to help easily identify the species by relating to the size and shape of the petals and sepals. A very simple prediction model is the backend of this applet and requires the dimensions of the aforementioned petals and sepals. The applet is available [Here](https://ronnie1995.shinyapps.io/simple_prediction) 

--- .class #id 

## The Dataset

The model is trained using `Anderson's Iris data`.

```
## 'data.frame':	150 obs. of  5 variables:
##  $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
##  $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
##  $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
##  $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
##  $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...
```
The data has the following characteristics:
<ul>
    <li> There are 4 numeric vairables encompassing the sepal and petal dimensions </li>
    <li> The last variable is the species containing 3 classes namely `Setosa`, `Versicolor` and `Virginica` </li>
    <li> Each class has 50 instances and will be the output variable </li>
    <li> The numeric variables will act as the predictors </li>
</ul>

--- .class #id

## Model
The `Random Forest` algorithm is used as the prediction model and is perfect for such classification problems.

```r
model <- train(Species~.,data=iris,method="rf")
model$finalModel
```

```
## 
## Call:
##  randomForest(x = x, y = y, mtry = param$mtry) 
##                Type of random forest: classification
##                      Number of trees: 500
## No. of variables tried at each split: 2
## 
##         OOB estimate of  error rate: 4%
## Confusion matrix:
##            setosa versicolor virginica class.error
## setosa         50          0         0        0.00
## versicolor      0         47         3        0.06
## virginica       0          3        47        0.06
```
The model summary reiterates the fact that the errors in classification are in experimental limits.




--- .class #id
## Where would you use it?

This is a very rudimentary prediction application owing to the lack of large and diverse dataset on the same. A more complex and robust model can be built taking this app as a foundation.

So, If you are in a forest, come across a plant of the Iris family and you have the sudden urge to find out the correct species with no botanist in sight then don't worry. Just whip out your smartphone (provided you get a signal) and click [here](https://ronnie1995.shinyapps.io/simple_prediction)
