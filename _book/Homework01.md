

---
title: "MATH 341 - Homework 01"
author: "Marjorie Blanco"
date: "January 3, 2018"
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

# Homework 1



## Problem 3.14

### Read data set


```r
prob <- read_excel("Excel/CH03/ex3-14.xlsx")
prob$data <- as.numeric(prob$data)
```

### EDA 


```r
ggplot(data=prob, aes(x=data)) +
  geom_histogram() +
  labs(title = "Histogram of Data") +
  labs(caption = "(Source: Statistical Methods & Data Analysis)") 
#> `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

<img src="Homework01_files/figure-html/unnamed-chunk-4-1.png" width="70%" style="display: block; margin: auto;" />

### Compute Mean, Median, Mode



The mean of the data set is: 60.65

The median of the data set is: 32.5

The mode of the data set is: 29

![](img/Figure3-14.PNG)


## Problem 3.31

### Read data set


```r
prob <- read_excel("Excel/CH03/ex3-31.xlsx")
prob$LuxuryHotel <- as.numeric(prob$LuxuryHotel)
prob$BudgetHotel <- as.numeric(prob$BudgetHotel)
prob$LuxuryHotel <- as.numeric(prob$LuxuryHotel)
prob$BudgetHotel <- as.numeric(prob$BudgetHotel)
```

### Compute mean and standard deviation of the room rate for luxury hotels

The mean of the data set is: 145

The standard deviation of the data set is: 27.57


```r
mean(prob$LuxuryHotel, na.rm=TRUE)
#> [1] 145
sd(prob$LuxuryHotel, na.rm=TRUE)
#> [1] 27.6
```

### Compute mean and standard deviation of the room rate for budget hotels


The mean of the data set is: 46.11

The standard deviation of the data set is: 5.13


```r
mean(prob$BudgetHotel, na.rm=TRUE)
#> [1] 46.1
sd(prob$BudgetHotel, na.rm=TRUE)
#> [1] 5.13
```

![](img/Figure3-31a.PNG)

### Variance

The variance of the data set is: 760

The variance of the data set is: 26.36

![](img/Figure3-31b.PNG)


```r
ggplot(data=prob, aes(x="Luxury", y=prob$LuxuryHotel)) +
  geom_boxplot() +
  xlab("") +
  ylab("Luxury Hotel Price")
#> Warning: Removed 3 rows containing non-finite values (stat_boxplot).
ggplot(data=prob, aes(x="Budget", y=prob$BudgetHotel)) +
  geom_boxplot() +
  xlab("") +
  ylab("Budget Hotel Price")
```

<img src="Homework01_files/figure-html/unnamed-chunk-9-1.png" width="70%" style="display: block; margin: auto;" /><img src="Homework01_files/figure-html/unnamed-chunk-9-2.png" width="70%" style="display: block; margin: auto;" />

![](img/Figure3-31b1.PNG)

### Variablity Reason

The coefficient of variation for Luxury hotel is 19.01

The coefficient of variation for Budget hotel is 11.13

### Measure of Variablity

The dataset for budget hotels and luxury hotels are from two different populations so standard deviation does not provide a good comparison of the variability. Coefficient of variability (CV) does provide a better comparison because it takes into account the larger difference in the means between both budget and luxury hotels.

## Problem 3.33

### Read data set


```r
prob <- read_excel("Excel/CH03/ex3-33.xlsx")
prob$Data <- as.numeric(prob$Data)
```

### Boxplot


```r
ggplot(data=prob, aes(x="", y=prob$Data)) +
  geom_boxplot() +
  labs(title = "Boxplot of Data") +
  labs(caption = "(Source: Statistical Methods & Data Analysis)") +
  xlab("") +
  ylab("Measurement")
```

<img src="Homework01_files/figure-html/unnamed-chunk-11-1.png" width="70%" style="display: block; margin: auto;" />

## Problem 4.16

### Read data set


```r
prob <- read_excel("Excel/CH04/ex4-16.xlsx")
prob
#> # A tibble: 4 x 5
#>   Race           O     A     B    AB
#>   <chr>      <dbl> <dbl> <dbl> <dbl>
#> 1 White      0.36  0.322 0.088 0.032
#> 2 Black      0.07  0.029 0.025 0.005
#> 3 Asian      0.017 0.012 0.01  0.003
#> 4 All others 0.015 0.008 0.003 0.001
```

#### P(Asian) U P(Type A)

The probability is 1.2 %

```r
prob[3,3] * 100
#>     A
#> 1 1.2
```

#### P(White) - (P(White) U P(Type A))

The probability is 48 %

```r
(sum(prob[1,2:5]) - prob[1,3]) * 100
#>    A
#> 1 48
```

#### P(Asian) U P(Type A) + P(Asian) U P(Type B)

The probability 2.2 %

```r
sum(prob[3,3:4]) * 100
#> [1] 2.2
```

#### P(Type O) + P(Type B)

The probability 58.8 %

```r
(sum(prob[,2]) + sum(prob[,4])) * 100
#> [1] 58.8
```

## Problem 4.30


```r
#Let D = event that loan defaulted
#Let !D = event that loan did not defaulted

#Let R1 = applicant has poor risk
#Let R2 = applicant has fair risk
#Let R3 = applicant has good risk

#P(D)
default <- .01
#P(!D)
non_default <- 1 - default

#P(R1|D)
default_poor_risk <- .3
#P(R2|D)
default_fair_risk <- .4
#P(R3|D)
default_good_risk <- .3

#P(R1|!D)  
nondefault_poor_risk <- .1
#P(R2|!D)  
nondefault_fair_risk <- .4
#P(R3|!D)  
dnonefault_good_risk <- .5


## Posterior probality of default given a fair risk 
#P(D | R2) 

x <- default_fair_risk * default
y1 <- default_fair_risk * default
y2 <- nondefault_fair_risk * non_default

result <- x / (y1 + y2)
result
#> [1] 0.01

## Prior probality of default
#P(D)
default
#> [1] 0.01
```
