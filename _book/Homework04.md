
---
title: "MATH 341 - Homework 04"
author: "Marjorie Blanco"
date: "January 29, 2018"
output:
  html_document:
    number_sections: yes
    toc: yes
    toc_float: yes
  pdf_document:
    toc: yes
  word_document:
    toc: yes
---



# Homework 4

## Problem 5.5 Coffee

### Propulation

The population is all the coffee manufacture by company.

### Confidence Interval at 95%


```r
sd.coffee <- 7.1       #mg
N <- 50                #units
mean.coffee <- 110     #mg

z <- qnorm(.025, lower.tail = FALSE)
z
#> [1] 1.96

error <- qnorm(.025, lower.tail = FALSE) * sd.coffee / sqrt(N)
lower <- mean.coffee - error
upper <- mean.coffee + error

error
#> [1] 1.97
lower
#> [1] 108
upper
#> [1] 112
```

The lower limit is 108.03.

The upper limit is 111.97.

If the sampling and estimation procedure is repeated many time, the confidence interval would include the population mean 95% of the time.

### Interpretation

We are 95% confident that the average caffeine content is between 108.03 and 111.97 milligrams.

## Prroblem 5.8 Mean Net Profit Margin

### Confidence Interval at 99%


```r
mean.netprofitmargin <- 0.072       
N <- 15                           
sd.netprofitmargin <- 0.125     

error <- qnorm(.005, lower.tail = FALSE) * sd.netprofitmargin / sqrt(N)

error <- qt(0.995,df=N-1)*  sd.netprofitmargin/sqrt(N)
lower <- mean.netprofitmargin - error
upper <- mean.netprofitmargin + error

error
#> [1] 0.0961
lower
#> [1] -0.0241
upper
#> [1] 0.168
```

### Interpretation

We are 99% confident that the mean gross profit margin of all small business in the city is between -2.41 % and 16.81 %

## Prroblem 5.13  Antibiotics


```r
sd.bacteria <- 13       #cm^2
e.bacteria <- 3         #cm^2
a <- 0.01

N <-  qnorm(a/2)^2 * sd.bacteria^2 / e.bacteria^2
N
#> [1] 125
```

The number of observations (cultures that must be developed and then tested) is 125.

## Prroblem 10.7 False Positive


```r
N <- 10000
p <- 591 / N
q <- 1 - p
p
#> [1] 0.0591
q
#> [1] 0.941


error <- qnorm(.005, lower.tail = FALSE) *  sqrt((p*q)/N)
lower <- p - error
upper <- p + error

error
#> [1] 0.00607
lower
#> [1] 0.053
upper
#> [1] 0.0652
```

### Interpretation

We are 99% confident that the interval 0.05 and 0.07 contains the true proportion of false positives.
