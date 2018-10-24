--- 
layout: default
title: Binomial data
---

# Binomial data

Many statistical problems involve binary response variables. For example, we could classify individuals as alive/dead, healthy/unwell, employ/unemployed, left/right, right/wrong, ... etc. A regression of binary data is possible if at least one of the predictors is continuous (otherwise you would use some kind of categorical test, such as a Chi-squared test).

## Type of data

*Response/Dependent:* Binomial (0/1)

*Predictor/Independent*: Continuous (and Categorical)


## Choosing a test

Do you have unique values of the predictors for each 0 and 1? 

1. Yes: Logistic regression, individual-level analysis.
 
2. No: Proportion data, group-level analysis.


The response variable contains only 0s and 1s (e.g., dead = 0, alive = 1) in a single vector. 

R treats such binary data is if each row came from a binomial trial with sample size 1. If the probability that an individual is dead is p, then the probability of obtaining y (where y is either dead or alive, 0 or 1) is given by an abbreviated form of the binomial distribution with n = 1, known as the Bernoulli distribution.

Binomial data can either be modelled at the individual (binary response) or group (proportion) level. If you have unique values of one or more explanatory variables for each and every individual case, then a model with a binary response variable will work. If not, you should aggregate the data until you do have such explanatory variables (e.g., at the level of the household, town, state, population, ...).

### Function

`glm(formuala = , data = , family = binomial)` 

 - `formula = ` A formula as normal. The response variable (column in the dataframe) is a binary factor (it does not need to be re-coded as 0/1).

 - `data = ` The dataframe.

 - `family = binomial ` A description of the error distribution and link function to be used in the model, usually a character string. In this case, 'binomial'.




## 1. Individual-level: binary response (0/1): logistic regression

At the individual level we can model each individual in terms of dead or alive (male/female, tall/short, green/red, ...), using logistic regression (or logit model). 

In the logit model, the log odds (logarithm of the odds) of the outcome is modeled as a linear combination of the predictor variables. If p is a probability, then p/(1 âˆ’ p) is the corresponding odds; the logit of the probability is the logarithm of the odds.

To model a binary response variable, we first need (or need to create) a single vector of 0 and 1s. We model this with glm() and family = 'binomial'. We can compare models using a test for a change in deviance with chi-squared. Overdispersion is not an issue with a binary response variable.

Let's look at the incidence (presence/absence) of a breeding bird on various islands ([data](http://www.intro2r.info/data/isolation.txt)).

```
isol <- read.table("http://www.intro2r.info/data/isolation.txt", header = TRUE)
head(isol)
```

```
##   incidence  area  distance
## 1         1 7.928     3.317
## 2         0 1.925     7.554
## 3         1 2.045     5.883
## 4         0 4.781     5.932
## 5         0 1.536     5.308
## 6         1 7.369     4.934
```

The data show the `$incidence` of the bird (present = 1, absent = 0) on islands of different sizes (`$area` in km2) and distance (`$distance` in km) from the mainland.

We begin by fitting a complex model involving an interaction between distance and area:

```
model1 <- glm(incidence ~ area * distance, family = binomial, data = isol)
```

Then we fit a simpler model with only main effects for distance and area:

```
model2 <- glm(incidence ~ area + distance, family = binomial, data = isol)
```

We now can compare the two models using `anova()`. In the case of binary data, we need to do a Chi-squared test.

```
anova(model1, model2, test = "Chi")
```

```
## Analysis of Deviance Table
## 
## Model 1: incidence ~ area * distance
## Model 2: incidence ~ area + distance
##   Resid. Df Resid. Dev Df Deviance Pr(>Chi)
## 1        46     28.252                     
## 2        47     28.402 -1 -0.15043   0.6981
```


The simpler model is not significantly worse, so we can go with that one.


### Fitting and interpreting the model

```
summary(model2)
```

```
## 
## Call:
## glm(formula = incidence ~ area + distance, family = binomial, 
##     data = isol)
## 
## Deviance Residuals: 
##     Min       1Q   Median       3Q      Max  
## -1.8189  -0.3089   0.0490   0.3635   2.1192  
## 
## Coefficients:
##             Estimate Std. Error z value Pr(>|z|)   
## (Intercept)   6.6417     2.9218   2.273  0.02302 * 
## area          0.5807     0.2478   2.344  0.01909 * 
## distance    -1.3719     0.4769  -2.877  0.00401 **
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 1)
## 
##     Null deviance: 68.029  on 49  degrees of freedom
## Residual deviance: 28.402  on 47  degrees of freedom
## AIC: 34.402
## 
## Number of Fisher Scoring iterations: 6
```

As normal, we have the formula, the deviance residuals (a measure of model fit), then the coefficient estimates, their standard errors, the z-statistic (sometimes called a Wald z-statistic), and p-values.

However, in contrast to a regular linear model with Normal errors, the coefficient estimates give the change in the log odds (the logarithm of the odds, or logit) for a 1-unit change in *x*:


### Logit/log odds

The logistic regression coefficients give the change in the log odds (the logarithm of the odds, or *logit*).

For continuous predictors, the coefficients give the change in the log odds of the outcome for a one unit increase in the predictor variable. For example, for every 1km2 increase in area, the log odds of the bird being present (versus absent) increases by 0.58 and the log odds of the bird being present decreases by 1.37 (i.e., -1.37) for every km of distance from the mainland.

For categorical predictors, the coefficient estimate describes the change in the log odds for each level compared to the base level.

Confidence intervals around the logits can be calculated with `confint()`.

```
confint(model2)
```

```
## Waiting for profiling to be done...

##                  2.5 %    97.5 %
## (Intercept)  1.8390115 13.735103
## area         0.1636582  1.176611
## distance     -2.5953657 -0.639140
```

Logits (log odds) are just one way of describing the model. We can easily convert the logits either to odds ratios or predicted probabilities.



### Odds ratios

[Odds ratios](https://en.wikipedia.org/wiki/Odds_ratio) are a relative measure of effect, which allows the comparison of two groups. It is a popular way of presenting results in medicine, especially of controlled trials. Here, the odds of one group (usually the control) is divided by the odds of another (the treatment) to give a ratio. In this case, if the odds of both groups are the same, the ratio will be 1, suggesting there is no difference. If the OR is > 1 the control is better than the other level. If the OR is < 1 the treatment is better than the control.

However, in R, we are presented with *differences* or the *change* in log odds between groups (for categorical variables) or the change in log odds between *x* and *x + 1* (for continuous variables). The directionality is the opposite to the example above because R effectively compares the 'treatment' to the 'control'.

Thus, for **categorical predictors**, an odds ratio:

 - > 1 suggests a positive difference between levels and the base level (the exponential of a positive number is greater than 1), i.e., the base level has a lower odds and the level has a higher odds,

 - < 1 suggests a negative difference (the exponential of a negative number lies between 0 and 1).


For **continuous predictors**, the odds ratio is the odds of *x + 1* over *x* (i.e., the odds ratio for a unit increase in the continuous x predictor variable), and the interpretation is the same as for categorical.

We can calculate the odds ratios by exponentiating the coefficient estimates.

```
exp(coef(model2))
```

```
## (Intercept)        area    distance 
## 766.3669575   1.7873322   0.2536142
```

See http://www.ats.ucla.edu/stat/mult_pkg/faq/general/odds_ratio.htm for more details.



### Predicted probabilities

We can generate predicted probabilities for continuous and categorical variables.

We can generate predicted probabilities for each row in the original dataset, by calling the `predict()` function (more details below).

Setting `type = 'link'` returns the logits; setting `type = 'response'` returns the predicted probabilities.

```
isol$logit <- predict(model2, type = 'link')
isol$p <- predict(model2, type = 'response')
```

However, to better plot these relationships, we should input a specific range of x's that we predict y's for.





### Generating fitted lines for binary response data: predict()

To plot the fitted line of a generalized linear model, we generally have to use the `predict()` function, because the model, although linear, is not a straight line that can be plotted with either an intercept or slope, as we used for `lm()` and `abline()`.

The function `predict()` is a general wrapper for more specific functions, in this case `predict.glm()`. We have to specify:

 - `object = ` the object (i.e., the fitted model), 

 - `newdata = ` the values of x for which we want predictions, named identically to the predictors in the object

 - `response = ` the type of prediction required (either on the scale of the linear predictors ('link') or on the scale of the response variable ('response').


There are, as usual, at least two ways we could do this: (i) use the original model, (ii) generate new logistic models for each predictor.


#### (i). Use the original model

We can use `model2` and generate values for the range of `$area` contingent on the mean value of `$distance`, and vice versa.

First, generate a sequence of x's from which to make predictions. Because area and distance are on similar scales, we can use the same sequence for both.

```
x.seq <- seq(from = 0, to = 9, by = 0.1)
```

# Make a new dataframe, of x.seq for area and x.seq for distance, along with the mean of the corresponding column

```
xv3 <- data.frame(area = c(x.seq, rep(mean(isol$area), times = length(x.seq))), 
                  distance = c(rep(mean(isol$distance), times = length(x.seq)), 
                  x.seq)
                 ) 
head(xv3)
```

Now use `predict()` with the new dataframe.

```
xv3$y <- predict(model2, newdata = xv3, type = 'response')

head(xv3)
```

```
##   area  distance         y
## 1  0.0    5.8563 0.1989551
## 2  0.1    5.8563 0.2083722
## 3  0.2    5.8563 0.2181137
## 4  0.3    5.8563 0.2281793
## 5  0.4    5.8563 0.2385677
## 6  0.5    5.8563 0.2492763
```


We could then plot y on area and y on distance, as illustrated below. 



#### (ii). Generate two separate logistic regressions

Alternatively, we can make two separate individual logistic regressions and make predictions from those.

First, run two models, one for area and one for distance.

```
modela <- glm(incidence ~ area,      family = binomial, data = isol)
modeli <- glm(incidence ~ distance,  family = binomial, data = isol)
```

We then need to make a sequence of x (e.g., $area) values from which to predict the y (predicted probability of $incidence).

In this case, because we are passing a single vector (rather than a dataframe (=list)) to the newdata argument of `predict()`, we need to put it inside a call to `list()`.

```
# create a sequence of x values  
xv <- seq(from = 0, to = 9, by = 0.01)

# y values 
yv <- predict(object = modela, newdata = list(area = xv), type = "response")
```

Now we have two vectors, `xv` and `yv`, that we can use to plot the fitted line.

```
# set up a two-panel plotting area
par(mfrow = c(1, 2))

 ## 1. area  
 # plot the raw data
   plot(isol$area, isol$incidence)

 # use the lines function to add the fitted lines
   lines(xv, yv)

  ## 2. Now, repeat for distance
  xv2 <- seq(0, 10, 0.1)
  yv2 <- predict(modeli, list(distance = xv2),type = "response")
  plot(isol$distance, isol$incidence)
  lines(xv2, yv2)
```

![](http://www.intro2r.info/unit4/img/isol.png)



## 2. Group-level: Proportion data

At the group level, we look at the proportion of successes and failures (or male/famale, tall/short, dem/rep, ...) in groups/populations/sites. 

In all these cases, we know both numbers ... those of successes and those of failures (in contrast to Poisson regression where we just have counts of successes).

In the past, the way this data was modelled was to use a single percentage as the response variable. However, this causes problems because:

 - The errors are not normally distributed,

 - The variance is not constant,

 - The response is bounded (by 1 above and by 0 below),

 - We lose information on the size of the sample, n, from which the proportion was estimated.


In the GLM framework, we can model proportion data directly. 

R carries out weighted regression, using the individual sample sizes as weights, and the logit link function to ensure linearity.


### Overdispersion

Overdispersion occurs in regression of proportion data when the residual deviance is larger than the residual degrees of freedom. There are two possibilities: either the model is misspecified, or the probability of success, p, is not constant within a given treatment level.

To deal with overdispersion, we can set `family = quasibinomial` rather than `family = binomial`


### Fitting the model

As above, we use `glm()` with `family = 'binomial'`. 

In contrast to the binomial response, in the case of proportion data, our response data is a matrix of two columns, one column of successes and one of failures. 

This matrix must be single object. We will use `cbind()` to stick two columns together.

In this case, we have the number of males and females in a range of populations. Our question is: Does sex ratio vary with population size?

```
numbers <- read.table("http://www.intro2r.info/data/sexratio.txt", header = TRUE)
head(numbers)
```

```
##   density females males
## 1       1       1     0
## 2       4       3     1
## 3      10       7     3
## 4      22      18     4
## 5      55      22    33
## 6     121      41    80
```


To model proportion data, R requires a unique form of the response variable - a matrix of two columns of successes and failures, in this case males and females.

```
numbers$p <- numbers$males/(numbers$males + numbers$females)
y <- cbind(numbers$males, numbers$females)
y
```

```
##      [,1] [,2]
## [1,]    0    1
## [2,]    1    3
## [3,]    3    7
## [4,]    4   18
## [5,]   33   22
## [6,]   80   41
## [7,]  158   52
## [8,]  365   79
```

We specifiy the model as follows.

```
m1 <- glm(y ~ numbers$density, family = binomial)
summary(m1)
```

```
## 
## Call:
## glm(formula = y ~ numbers$density, family = binomial)
## 
## Deviance Residuals: 
##     Min       1Q   Median       3Q      Max  
## -3.4619  -1.2760  -0.9911   0.5742   1.8795  
## 
## Coefficients:
##                  Estimate Std. Error z value Pr(>|z|)    
## (Intercept)     0.0807368  0.1550376   0.521    0.603    
## numbers$density 0.0035101  0.0005116   6.862 6.81e-12 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 1)
## 
##     Null deviance: 71.159  on 7  degrees of freedom
## Residual deviance: 22.091  on 6  degrees of freedom
## AIC: 54.618
## 
## Number of Fisher Scoring iterations: 4
```

The output is familar. For this continuous predictor, we get an intercept and slope, and the p-values indicate whether they are significantly different from 0.

For categorical variables, we get, as usual, the base level mean, then differences between means. Furthermore, the coefficient estimates are in logits (ln(p/(1 - p)). To calculate a proportion (p) from a logit (x), you need to calculate 1/(1 + 1/(exp(x))).

However, we have substantial overdispersion (residual deviance = 22.091 is much greater than residual d.f. = 6). One reason for overdispersion is if the model is misspecified. Let's try log(density).

```
m2 <- glm(y ~ log(density), family = binomial, data = numbers)
summary(m2)
```

```
## 
## Call:
## glm(formula = y ~ log(density), family = binomial, data = numbers)
## 
## Deviance Residuals: 
##     Min       1Q   Median       3Q      Max  
## -1.9697  -0.3411   0.1499   0.4019   1.0372  
## 
## Coefficients:
##              Estimate Std. Error z value Pr(>|z|)    
## (Intercept)  -2.65927    0.48758  -5.454 4.92e-08 ***
## log(density)  0.69410    0.09056   7.665 1.80e-14 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 1)
## 
##     Null deviance: 71.1593  on 7  degrees of freedom
## Residual deviance:  5.6739  on 6  degrees of freedom
## AIC: 38.201
## 
## Number of Fisher Scoring iterations: 4
```


There is no evidence of overdispersion (residual deviance = 5.67 on 6 d.f.) in this new model.

We can conclude that the proportion of males increases significantly with increasing density, and that the logistic model is linearized by logarithmic transformation of the explanatory variable (population density).


### Plotting proportion data

Rather than the raw values, we can plot one of the proportions, in this case the proportion of males.

We need to use `predict()` as above.

```
# make sequence of x
xv <- seq(from = 0, to = 6, by = 0.01)

# predict values of y from xv and m2
yv <- predict(m2, list(density = exp(xv)), type = "response")

# plot the proportion of males as a function of density
plot(x = log(numbers$density), y = numbers$p, ylab = "Proportion male", 
     pch = 16, col = "blue", lwd = 2)

# add the fitted line
lines(xv, yv, col = "red", lwd = 2)
```

![](http://www.intro2r.info/unit4/img/seratio.png)



### Considerations

Some kinds of proportion data are better analysed differently.

**Percentage cover** is best analysed using conventional linear models (assuming normal errors and constant variance) following arcsine transformation.

**Percentage change** in some continuous measurement (e.g., weight, tree diameter) is best modelled either as an ANCOVA of the final measurement with the initial measurement as a covariate, or by specifying the response as a relative change: log(final/initial), both of which should be linear models with normal errors.



