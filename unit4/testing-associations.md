---
layout: default
title: Testing Associations
---

# Is There An Association Between Two (or More) Variables?

So far we have looked at solely categorical data ([Testing Ratios](http://www.intro2r.info/unit3/testing-ratios.html)) and continuous data taken from members of different groups or categories ([Testing Populations](http://www.intro2r.info/unit3/testing-populations.html)).

Here, we will look at methods to test whether two or more samples of continuous data are positively or negatively associated. We will also consider having multiple predictor variables. 


## Type of data

*Response/Dependent:* Integer or continuous

*Predictor/Independent*: Continuous (or Categorical)


## Choosing a test

(0. Response and predictor data are categorical: See [Testing Ratios](http://www.intro2r.info/unit3/testing-ratios.html), `chisq.test()`.)

1. Do the two continuous variables come from the same distribution? `ks.test()`. 

2. We assume no causal relationship between the continuous 'predictor' and the continuous 'response': correlation, `cor()`, `cor.test()`.

3. We are testing if the continuous/categorical predictor variables are causing some of the variation in the  continuous response data data from more than two groups and/or two predictors: linear regression, `lm()`.


## Figures

If we have continuous data  both side, we will most likely make some kind of scatter plot.

```
x <- rnorm(100)
y <- rnorm(100)
plot(y ~ x)
```

![](http://www.intro2r.info/unit4/img/scatterplot.png)



## 1. Do the two continuous variables come from the same distribution?

We can use a [Kolmogorov-Smirnov Test](https://en.wikipedia.org/wiki/Kolmogorov%E2%80%93Smirnov_test) to test whether two samples come from the same distribution.

### Functions

 -  `ks.test(x = , y = )`  performs a two-sample test of the null hypothesis that x and y were drawn from the same continuous distribution.

    + `x = ` and `y = ` are vectors of numeric data.

### Example

Generate 50 values drawn randomly from two different distributions: x is from a normal distribution and y from a uniform.

Thus, we *know* they are different ...

```
x <- rnorm(n = 50)
y <- runif(n = 50)
```

We can check this with histograms.

```
par(mfrow = c(1,2))
hist(x, breaks = 6)
hist(y, breaks = 6)
```

![](http://www.intro2r.info/unit4/img/ks-fig.png)


The `ks.test()` function takes `x = ` and `y = `. 

```
ks.test(x, y)
```

```
## 
##  Two-sample Kolmogorov-Smirnov test
## 
## data:  x and y
## D = 0.6, p-value = 1.062e-08
## alternative hypothesis: two-sided
```

The p-value less than 0.001 suggests that x and y are indeed drawn from different distributions (as we shushpected … ).


## Correlation

Whether we run correlation or a regression depends on how we think the two variables are related. If we think that there is no causal relationship between the two, then we would test for a correlation. If we think that there is a causal relationship between the two, then we would run a regressin.

As they saying goes ‘correlation does not imply causation’.

### Functions

 - `cor()`  returns the correlation coefficient of two variables

 - `cor.test()`  tests for association—correlation—between paired samples.  It returns the correlation coefficient and the p-value of the correlation.

#### Arguments

 - `x = ` a numeric vector the same length as `y`, 

 - `y = ` a numeric vector the same length as `x`,

 - `method = `  [Pearson’s](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient) product moment correlation coefficient (`method = 'pearson'`) is the parametric version used for normal data (and the default). [Kendall’s](https://en.wikipedia.org/wiki/Kendall_rank_correlation_coefficient) tau (`method = 'kendall'`) or [Spearman’s](https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient) rho (`method = 'spearman'`) are used for non-parametric data. The three methods each estimate the association between paired samples and compute a test of the value being zero (indicating no association).

#### Assumptions (Pearson)

 - normality (Shapiro-Wilks test, qqplots)

### Interpretation

The correlation coefficient can fall between -1 and 1.

 -  -1 (negative 1) means a strong negative correlation (x goes up and y goes down),

 -  0 means no association between x and y,

 -  1 means a strong positive correlation (x goes up and y goes up).



### An example

Let's look at the small sparrow dataset, and the relationship between the various measurements.

```
BirdData <- data.frame(
            Tarsus  = c(22.3, 19.7, 20.8, 20.3, 20.8, 21.5, 20.6, 21.5),
            Head    = c(31.2, 30.4, 30.6, 30.3, 30.3, 30.8, 32.5, 31.6),
            Weight  = c(9.5, 13.8, 14.8, 15.2, 15.5, 15.6, 15.6, 15.7),
            Wingcrd = c(59, 55, 53.5, 55, 52.5, 57.5, 53, 55),
            Species = c('A', 'A', 'A', 'A', 'A',  'B', 'B', 'B')
            )
```


We can use the `pairs()` function to plot all the variables against one another.

```
pairs(BirdData)
```

![](http://www.intro2r.info/unit4/img/birdplots.png)


We have no a priori reason to believe that any of these measurements of sparrows drives variation in the others. However, we can test whether they are correlated. For example, do sparrows with larger heads also have larger wings?

#### cor()

The function `cor()` returns the correlation coefficient of two variables. It requires an `x` and a `y`. Pearson's product moment correlation coefficient is the parametric version used for normal data; Kendall's tau or Spearman's rho for non-parametric data.

```
cor(x = BirdData$Tarsus, y = BirdData$Wingcrd, method = 'pearson')
```

```
## [1] 0.6409484
```

#### cor.test()

```
cor.test(x = BirdData$Tarsus, y = BirdData$Wingcrd, method = 'pearson')
```

```
## 
##  Pearson's product-moment correlation
## 
## data:  BirdData$Tarsus and BirdData$Wingcrd
## t = 2.0454, df = 6, p-value = 0.0868
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.1162134  0.9269541
## sample estimates:
##       cor 
## 0.6409484
```

### Interpreting the output

 - `t = 2.0454` is the t-test statistic value,

 - `df = 6` is the degrees of freedom,

 - `p-value = 0.0868` is the significance level of the t-test,

 - `95 percent confidence interval: -0.1162134  0.9269541` is the confidence interval of the correlation coefficient at 95%,

 - `sample estimates   cor   0.6409484` is the correlation coefficient.

The p-value of the test is 0.0868, not less than the usual alpha of 0.05; so we cannot reject the null hypothesis that Tarsus and Wing are not significantly correlated.

[More details](https://rstudio-pubs-static.s3.amazonaws.com/240657_5157ff98e8204c358b2118fa69162e18.html)


 - - -

## Linear Regression




















