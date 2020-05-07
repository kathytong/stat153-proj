


# STAT 153: Project Blog
Group: Kathy Tong (ID: 3031797536) \
Date: May 6th, 2020 

## Introduction

With the explosion of COVID-19 internationally in the past few months, we'd like to look at some of the previous data for total COVID-19 infections per day and use that to forecast into the future how many people we predict to be infected with COVID-19 in the next 10 days.


## The Model

Looking at the data, the number of infected each day seems to grow exponentially. This means that not only are the number of infections growing each day, but the very rate at which the infections grow is also growing. 

![plot of chunk chunk1](figure/chunk1-1.png)

By removing the exponential growth rate by taking the logarithm of our data, we can then use a statistical model called ARIMA to further fit the data. Using this ARIMA model, we can predict the infection numbers for the days we were provided in the actual data, and then look at how close our predictions are to the actual data to check how good our model is. Looking at the differences between our predictions and the actual data, there doesn't seem to be any noticeable pattern that could further be fitted.

![plot of chunk chunk5](figure/chunk5-1.png)


## Predictions

With this model, we can forecast into the future to predict what the numbers are going to look like for the next few days. 

```
## Time Series:
## Start = 67 
## End = 76 
## Frequency = 1 
##  [1]  34985.68  40615.76  47171.27  54770.91  63604.94  73856.60  85765.77  99591.54 115648.75 134292.96
```

## Limitations

Exponential growth can't possibly grow forever. Sooner or later, the numbers are going to have to plateau, whether it's because society is slowing down and people are following the proper social distancing protocols, and people stop getting infected, or whether it's because enough people get infected and we manifest herd immunity. As such, the further out into the future these we try to predict, the less accurate these predictions will likely be.



