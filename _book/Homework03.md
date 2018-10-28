
---
title: "Homework 03"
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



# Homework 3

## Problem 4.69 - Travel Voucher Processing

### P(x > 30)

$$P(x > 30) = P (z > \frac{30 - 36}{3})$$

P(x > 30) = P(z > -2) = 0.98


```r
pnorm(30, m=36, s=3, lower.tail = FALSE)
#> [1] 0.977
```

![](img/Figure4-69a.PNG)

### P(x > 55)

$$P(x > 55) = P (z >\frac{55 - 36}{3})$$

P(x > 55) =  P(z > 6.333) = 0


```r
pnorm(55, m=36, s=3, lower.tail = FALSE)
#> [1] 1.2e-10
```

![](img/Figure4-69b.PNG)

Since the probability is extremly low, the conclusion is that the travel voucher was misplaced or lost.

## Problem 4.72 - Honor Society

### P(z > 1.65) = 0.95 

$$1.65 = \frac{X - 513}{130}$$ 

P(z > 0.05) =  726.8

X = 727.5

![](img/Figure4-72a.PNG)


### P(z < 0.675 ) = 0.25

$$ -0.675 = \frac{X - 513}{130}$$ 

P(z < 0.25) =  425.3

X = 425.25

![](img/Figure4-72b.PNG)


## Problem 4.79 - Retardation Score

### P(900 > x > 960)

P(900 > x > 960) =  


![](img/Figure4-79a.PNG)


### P(x > 960)

$$P(x > 960) = P (z >\frac{960 - 930}{20})$$

P(x > 960) =  0.2

![](img/Figure4-79b.PNG)


### P(z > 1.28)

P(x > 960) =  967.3

![](img/Figure4-79c.PNG)

## Problem 4.82 TV Watching Time

The results are not consistent.

### P(x > 7)

$$P(x > 5.5) = P (z > \frac{7 - 5}{1.3})$$
P(x > 5.5) = P(z > 0.385) 

P(x > 7) =  0.1

![](img/Figure4-82a.PNG)

### P(x > 5.5)


P(x > 5.5) = P(z > 8.6) 

P(x > 5.5) =  0

![](img/Figure4-82b.PNG)

