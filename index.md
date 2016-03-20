---
title       : Coursera Developing Data Products - Predicting Vehicle MPG
author      : Michael Cho
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

The shiny app under development allows a user to enter some basic information about their vehicle, and obtain a prediction for its MPG.  The app relies on a simple GLM algorithm and a data set "auto MPG" from the UCI Machine Learning Repository located [here](http://bit.ly/1sgiKaS). 

--- .class #id

## Algorithm

```r
library(RCurl)
library(caret)
mpg <- read.csv('mpg.csv')
modFit <- train(mpg ~ cyl + disp + horse + weight + accel + year + origin, method="glm", data=mpg)
```

--- .class #id

## Algorithm Predictions

![plot of fit plot](./assets/img/fit.png)



The relative 45 degree line shape of this simple plot of actual vs. predicted MPG values demonstrates the simple GLM's decent fit.

--- .class #id

## Shiny App

![alt text](./assets/img/Capture.png)



This is a screenshot of the deployed shiny app.  It was tested and worked for various combinations of numeric inputs. It is available [here](https://chosun1.shinyapps.io/ExData_Plotting1/).



