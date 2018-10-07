---
layout: default
title: Testing Populations
---

# Do Samples Come From The Same Or Different Populations?

We use the following methods to test whether samples are drawn from populations with different means, or test whether one sample is drawn from a population with a mean different from some theoretical mean.

*Functions*: `t.test()`, `wilcox.test()`

*Type of data*: Integer or continuous in two or more groups.

We can continue to use the small bird data...

```r
BirdData <- data.frame(
            Tarsus  = c(22.3, 19.7, 20.8, 20.3, 20.8, 21.5, 20.6, 21.5),
            Head    = c(31.2, 30.4, 30.6, 30.3, 30.3, 30.8, 32.5, 31.6),
            Weight  = c(9.5, 13.8, 14.8, 15.2, 15.5, 15.6, 15.6, 15.7),
            Wingcrd = c(59, 55, 53.5, 55, 52.5, 57.5, 53, 55),
            Species = c('A', 'A', 'A', 'A', 'A',  'B', 'B', 'B')
            )
```
            
To display these data, we can use a histogram (*good for one sample*), barplot (*ok ...*), or boxplot (*better ... *), or a dotplot (*even better ...*), or a combined dot-boxplot or overlapping histograms (*the best!*).


            
            
## One sample
            
### t-test: `t.test(x = , mu = )`

First, we can test whether one sample is drawn from a population with a mean different from a theoretical mean, using a one-sample t-test.

The [one-sample t-test](https://en.wikipedia.org/wiki/Student%27s_t-test#One-sample_t-test) asks whether our data are drawn from a population whose true mean is some value we specify.

In this case, we can ask whether the sparrow's tarsus data is drawn from a population that has a mean (`mu = `) of 20.

```r
t.test(BirdData$Tarsus, mu = 20)
```
            
```           
## 
##  One Sample t-test
## 
## data:  BirdData$Tarsus
## t = 3.2786, df = 7, p-value = 0.01351
## alternative hypothesis: true mean is not equal to 20
## 95 percent confidence interval:
##  20.26135 21.61365
## sample estimates:
## mean of x 
##   20.9375
```
            
The `p = 0.01351` suggests that our sparrows are different.
            
            
## Two samples

### Independent two-sample t-test: `t.test(x = , y = )`

Two compare the means of two samples that were taken independently, we can use `t.test()`. By default, R assumes that variances are not equal, and adjusts for this by running a Welch t-test.

```r
t.test(x = BirdData$Tarsus[BirdData$Species == 'A'], 
       y = BirdData$Tarsus[BirdData$Species == 'B'])
```
            
```
## 
##  Welch Two Sample t-test
## 
## data:  BirdData$Tarsus[BirdData$Species == "A"] and BirdData$Tarsus[BirdData$Species == "B"]
## t = -0.80033, df = 5.9988, p-value = 0.454
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -1.7041641  0.8641641
## sample estimates:
## mean of x mean of y 
##     20.78     21.20
```

Species A and B have similar tarsus lengths.

To run the Student's t-test, that does assume equal variance, set `var.equal = TRUE`.

```r
t.test(x = BirdData$Tarsus[BirdData$Species == 'A'], 
       y = BirdData$Tarsus[BirdData$Species == 'B'],
       var.equal = TRUE)
```
            
```
## 
##  Two Sample t-test
## 
## data:  BirdData$Tarsus[BirdData$Species == "A"] and BirdData$Tarsus[BirdData$Species == "B"]
## t = -0.68349, df = 6, p-value = 0.5198
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -1.923607  1.083607
## sample estimates:
## mean of x mean of y 
##     20.78     21.20
```
 
### Paired t-test: `t.test(x = , y = , paired = TRUE)`

If we have observations before and after a treatment, or of two matched subjects with different treatments, we can run a paired t-test. R relies on the relative position to determine the pairing, so make sure that this is correct.

Pairing the data gives us more statistical power, because random inbetween subject variation has been eliminated. But, we lose degrees of freedom because each pair is now the test unit, rather than the individual.

```r
before <- c(20, 15, 10, 5, 20, 15, 10, 5, 20, 15, 10, 5, 20, 15, 10, 5)
after <- c(23, 16, 10, 4, 22, 15, 12, 7, 21, 16, 11, 5, 22, 14, 10, 6)

t.test(before, after)
```
         
```
## 
##  Welch Two Sample t-test
## 
## data:  before and after
## t = -0.40876, df = 29.755, p-value = 0.6856
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -5.248256  3.498256
## sample estimates:
## mean of x mean of y 
##    12.500    13.375
```
         
```r
t.test(before, after, paired = TRUE)
```
         
```
## 
##  Paired t-test
## 
## data:  before and after
## t = -3.0502, df = 15, p-value = 0.0081
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -1.4864388 -0.2635612
## sample estimates:
## mean of the differences 
##                  -0.875
```

In the above cases, we have specified `x` and `y`. Depending how you have your data organised, a formula can also be used.

The paired t-test is equivalent to testing whether difference between each pair of observations has a population mean of 0.

```r
t.test(x = before - after, mu = 0, var.equal = TRUE)
```
         
```
## 
##  One Sample t-test
## 
## data:  before - after
## t = -3.0502, df = 15, p-value = 0.0081
## alternative hypothesis: true mean is not equal to 0
## 95 percent confidence interval:
##  -1.4864388 -0.2635612
## sample estimates:
## mean of x 
##    -0.875
```

The t-test assumes that the data for each group or sample follow a normal distribution and were sampled independently from the two populations. The Student's t-test assume equal variances, but is robust if sample sizes are equal; Welch's t-test is robust to unequal variance even if sample sizes are different.

### Non-parametric: `wilcox.test()`

As with `t.test()`, the `wilcox.test()` function can be modified for one or two samples, paired or unpaired.

For independent (unpaired) samples, it is called the [Mann-Whitney U test](https://en.wikipedia.org/wiki/Mann%E2%80%93Whitney_U_test).
         For paired samples, it is known as the [Wilcoxon signed-rank](https://en.wikipedia.org/wiki/Wilcoxon_signed-rank_test) test.

```r
wilcox.test(x = BirdData$Tarsus[BirdData$Species == 'A'], 
            y = BirdData$Tarsus[BirdData$Species == 'B'])
```
         
```
## Warning in wilcox.test.default(x = BirdData$Tarsus[BirdData$Species ==
## "A"], : cannot compute exact p-value with ties

## 
##  Wilcoxon rank sum test with continuity correction
## 
## data:  BirdData$Tarsus[BirdData$Species == "A"] and BirdData$Tarsus[BirdData$Species == "B"]
## W = 5, p-value = 0.5462
## alternative hypothesis: true location shift is not equal to 0
```
         
## More than two samples
         
### Analysis of Variance

In its simplest form, ANOVA is a statistical test of whether or not the means of several groups are equal, and therefore generalizes the t-test to more than two groups. It is akin to running multiple two-sample t-tests.

ANOVA has the following assumptions.

 - Independence of observations,
  
 - Normality - the distributions of the residuals are normal,
 
 - Equality (or "homogeneity") of variances (called homoscedasticity) - the variance of data in groups should be the same.

### One-way ANOVA: `aov()`

One-way analysis of variance (ANOVA) is used to determine whether there are any statistically significant differences between the means of three or more independent (unrelated) groups.

It tests the null hypothesis that the means of all groups are equal. Details of the specifics of ANOVA are described here

If it returns a statistically significant result, we accept the alternative hypothesis: At least two group means are statistically significantly different from each other.

However, ANOVA cannot tell you which specific group/s is significantly different from which other. To determine this, a post-hoc test must be carried out.

We will illustrate this using the sparrow data set.

```r
dat <- read.table(file = "http://www.simonqueenborough.info/R/data/sparrows.txt", header = TRUE)
```

We want to make sure that the observers who collected the data were not biased in any way, i.e., there was no observer that consistently measured low or high. If sparrows were assigned at random to observers, we would not expect any difference between the observers in the sparrow measurements.

We can test this question with a one-way ANOVA.

First, it will make our lives a tiny bit easier to convert Observer to a factor.

```r
dat$fObserver <- as.factor(dat$Observer)
```
                 
                
Then, we can plot the data (two different ways, of course!).

```r
par(mfrow = c(1, 2), lwd = 2, las = 1)

# 1. First a boxplot
boxplot(dat$Tarsus ~ dat$fObserver,
       xlab = 'Observer')

# 2. Then, a barplot:
## use tapply() to get means and sd
MeanTarsus <- tapply(dat$Tarsus, dat$fObserver, mean)
SDTarsus   <- tapply(dat$Tarsus, dat$fObserver, sd) 
              
## calculate mid-points of bars, to plot error bars
MidPoints <- barplot(MeanTarsus, plot = FALSE)

barplot(MeanTarsus, ylim = c(0, 30),
       xlab = 'Observer')
segments(x0 = MidPoints, x1 = MidPoints,
         y0 = MeanTarsus + SDTarsus, y1 = MeanTarsus - SDTarsus)
```

![]()
*Differences in Tarsus length measured by different Observers*

The function `aov()` runs the ANOVA model. We need to provide a `formula = ` argument, and can also give a `data = `.

```r
m_obs <- aov(Tarsus ~ fObserver, data = dat)
summary(m_obs)
```
         
```
##              Df Sum Sq Mean Sq F value   Pr(>F)    
## fObserver     6   19.1   3.181   3.793 0.000966 ***
## Residuals   972  815.3   0.839                     
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```
            
The p = 0.000966 tells us that there are significant differences among observers. 
We will need to do a post-hoc test to identify which ones (see below).

In reality, `aov()` is a wrapper to `lm()` (i.e., the function aov calls the function lm) for fitting linear models 
to balanced or unbalanced experimental designs. The main difference from `lm()` is in the way `print()`, `summary()` 
and so on handle the fit: this is expressed in the traditional language of the analysis of variance 
rather than that of linear models. This also means that it is easy to include both categorical and 
continuous variables as predictors in a model (we will come to this later).

Note: `aov()` is designed for balanced designs, and the results can be hard to interpret without balance: 
beware that missing values in the response(s) will likely lose the balance.
            

#### Non-parametric one-way ANOVA: Kruskal-Wallis Test

If the data do not meet the assumptions of a parametric ANOVA, we can use a non-parametric alternative. 
In this case, the Kruskal-Wallis Test, or one-way ANOVA on ranks. It extends the Mann-Whitney U Test to more than two groups.

```r
kruskal.test(Tarsus ~ fObserver, data = dat)
```
```
## 
##  Kruskal-Wallis rank sum test
## 
## data:  Tarsus by fObserver
## Kruskal-Wallis chi-squared = 38.875, df = 6, p-value = 7.574e-07
```
            
### Two-way ANOVA: `aov()`

A two-way ANOVA models the response as a function of two categorical variables, 
and can also include an interaction between them. (So that we keep using the same 
sparrow data, we will look at how Tarsus length varies between the different species and sexes, 
although there are only two levels of each).

First, we run the simple additive model. This model is testing for differences between species 
and between the sexes pooled over species.

```r
m_additive <- aov(Tarsus ~ Species + Sex, data = dat)
summary(m_additive)
```
```
##              Df Sum Sq Mean Sq F value Pr(>F)    
## Species       1  391.7   391.7  1022.2 <2e-16 ***
## Sex           1   68.8    68.8   179.5 <2e-16 ***
## Residuals   976  374.0     0.4                   
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```
            
P < 0.05 for both Species and Sex, suggesting that tarsus length differs significantly in both.

To test whether the differences between the sexes are different in each species 
(i.e., is there an interaction between sex and species), we modify the model with `*`.

```r
m_interaction <- aov(Tarsus ~ Species * Sex, data = dat)
summary(m_interaction)
```
```
##              Df Sum Sq Mean Sq  F value Pr(>F)    
## Species       1  391.7   391.7 1021.912 <2e-16 ***
## Sex           1   68.8    68.8  179.492 <2e-16 ***
## Species:Sex   1    0.3     0.3    0.709    0.4    
## Residuals   975  373.7     0.4                    
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```
            
Here, P = 0.4, suggesting that the difference in Tarsus length between males and females does not vary between the species.

A more detailed calculation of ANOVA in R is provided here
  
            
            
## Post-hoc tests: TukeyHSD

To compare the significant difference across all the group means 
[Tukeys Honest Significant Differences](https://en.wikipedia.org/wiki/Tukey%27s_range_test) 
test is often used. Tukey's test is essentially a t-test, except that it corrects for the 
fact that you are making multiple comparisons (when making multiple comparisons, the chance of
making a Type I error---a false positive---increases). Tukey's test corrects for that, so is 
more suitable single test for multiple comparisons than a running multiple t-tests.

First, we look at the one-way ANOVA, differences between observers.   
            
            
```r
            posthoc <- TukeyHSD(m_obs)
posthoc
```
```
##   Tukey multiple comparisons of means
##     95% family-wise confidence level
## 
## Fit: aov(formula = Tarsus ~ fObserver, data = dat)
## 
## $fObserver
##             diff         lwr         upr     p adj
## 3-2  0.266804979  0.03220683  0.50140313 0.0141868
## 4-2  0.009638554 -0.32632698  0.34560409 1.0000000
## 5-2  0.133333333 -0.29952798  0.56619464 0.9710133
## 6-2 -0.068831169 -0.33753254  0.19987020 0.9887784
## 7-2  0.346000000 -0.06763922  0.75963922 0.1709119
## 8-2 -0.029357798 -0.33239207  0.27367647 0.9999552
## 4-3 -0.257166425 -0.60155215  0.08721930 0.2929550
## 5-3 -0.133471646 -0.57290036  0.30595707 0.9729768
## 6-3 -0.335636148 -0.61479401 -0.05647829 0.0073020
## 7-3  0.079195021 -0.34131192  0.49970196 0.9979097
## 8-3 -0.296162777 -0.60850626  0.01618071 0.0762933
## 5-4  0.123694779 -0.37723849  0.62462805 0.9907668
## 6-4 -0.078469723 -0.44693364  0.28999419 0.9958615
## 7-4  0.336361446 -0.14805845  0.82078134 0.3828507
## 8-4 -0.038996352 -0.43319808  0.35520537 0.9999493
## 6-5 -0.202164502 -0.66070756  0.25637855 0.8508450
## 7-5  0.212666667 -0.34335375  0.76868709 0.9188436
## 8-5 -0.162691131 -0.64216071  0.31677844 0.9534703
## 7-6  0.414831169 -0.02561204  0.85527438 0.0801807
## 8-6  0.039473371 -0.29923386  0.37818060 0.9998674
## 8-7 -0.375357798 -0.83754776  0.08683216 0.1997785
```
                       
Here, looking down the list of P values, only two comparisons are significant: 3-2 and 6-3.

Then, the two-way ANOVA.

```r
posthoc <- TukeyHSD(m_additive)
posthoc
```
```
##   Tukey multiple comparisons of means
##     95% family-wise confidence level
## 
## Fit: aov(formula = Tarsus ~ Species + Sex, data = dat)
## 
## $Species
##                diff       lwr       upr p adj
## SSTS-SESP -1.942702 -2.061942 -1.823462     0
## 
## $Sex
##                  diff       lwr       upr p adj
## Male-Female 0.5802367 0.4951247 0.6653487     0                       
```                       
                       
 - - -
            
            
                       
