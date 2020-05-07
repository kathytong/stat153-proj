---
title: "STAT 153: Project Blog"
author: "Group: Kathy Tong (ID: 3031797536)"
date: "May 6th, 2020"
output: 
  pdf_document:
    number_sections: true
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
library(dplyr)
library(astsa)
```


# Introduction

With the explosion of COVID-19 internationally in the past few months, we'd like to look at some of the previous data for total COVID-19 infections per day and use that to forecast into the future how many people we predict to be infected with COVID-19 in the next 10 days.


# The Model

Looking at the data, the number of infected each day seems to grow exponentially. This means that not only are the number of infections growing each day, but the very rate at which the infections grow is also growing. 

```{r chunk1, echo=FALSE, fig.height = 4, fig.width = 7}
data = read.csv("covid.csv")
covid = as.vector(data$Count)
time = as.vector(data$Day)
plot.ts(covid, main="Total Detected COVID-19 Cases Count", xlab="Day", ylab="Detected COVID-19 Cases")
```

After removing the exponential growth rate by taking the logarithm of our data, we can use a statistical model called ARIMA to further fit the data. Using this ARIMA model, we can predict the infection numbers for the days we were provided in the actual data, and then look at how close our predictions are to the actual data to check how good our model is. 

```{r chunk5, echo=FALSE, fig.height = 4, fig.width = 7}
# find the residuals from parametric model fitting exponential trend
arima_model = arima(log(covid), c(1, 2, 1))
plot.ts(residuals(arima_model), main="Residuals of COVID-19 Cases Counts Modeled with ARIMA", xlab="Day", ylab="Detected COVID-19 Cases")
```



# Predictions

# Limitations



