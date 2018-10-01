---
layout: default
title: Testing Ratios
---

# Do Data Match An Expected Ratio?

*Functions*: `binom.test()`, `prop.test()`, `chisq.test()`, `fisher.test()`

*Type of Data*: Discrete, categorical (counts or frequencies)


## One variable

### The probabilty of success in a Bernoulli/binomial experiment

The [binomial test](https://en.wikipedia.org/wiki/Binomial_test) is a test of the statistical significance of deviations from a theoretically expected distribution of observations into two categories: e.g., does our count of heads:tails differ from a 1:1 ratio, when tossing a coin?

For example, if we toss a coin 10 times and get 8 heads, is it likely that this coin is biased?

We can specify *x* the number of failures (or successes) out of *n* number of trials.

```r
binom.test(x = 8, n = 10)
```

```
##  Exact binomial test
## 
## data:  8 and 10
## number of successes = 8, number of trials = 10, p-value = 0.1094
## alternative hypothesis: true probability of success is not equal to 0.5
## 95 percent confidence interval:
##  0.4439045 0.9747893
## sample estimates:
## probability of success 
##                    0.8
```
With such a small sample, it's hard to tell. What if we tossed the coin 10 more times?


```r
binom.test(16, 20)
```

```
##  Exact binomial test
## 
## data:  16 and 20
## number of successes = 16, number of trials = 20, p-value = 0.01182
## alternative hypothesis: true probability of success is not equal to 0.5
## 95 percent confidence interval:
##  0.563386 0.942666
## sample estimates:
## probability of success 
##                    0.8
```

For an alpha of 0.05, it suggests that this coin, or the way it is being flipped, needs some attention!

We can also use this test to ask other questions about the probabilty of two outcomes (including counts of things that do not at first seem to be counts of only two things). For example, we can ask if a six-sided die is biased to throw more 6's than we would expect.

If fair, the dice would roll a 6 one in six times (1/6). If we rolled 51 6's in a total of 235 rolls, what can we say?

To fit this into a binomial test, we do the following.

```r
binom.test(x = 51, n = 235, p = 1/6, alternative = 'greater')
```


```
##  Exact binomial test
## 
## data:  51 and 235
## number of successes = 51, number of trials = 235, p-value =
## 0.02654
## alternative hypothesis: true probability of success is greater than 0.1666667
## 95 percent confidence interval:
##  0.1735253 1.0000000
## sample estimates:
## probability of success 
##              0.2170213
```


The number of successes (`x`) is 51. The number of trials (`n`) is 235. The probability (null hypothesis) we expect (`p`) is 1/6. And the alternative hypothesis is that we roll 51 or more 6's (`alternative = 'greater'`)---this is a one-tailed test.

We would use a two-tailed test if we wanted to know whether the die rolled too many or too few 6's (`alternative = 'two.sided'`).


### Comparing direction: the sign test

We can also use this same test to compare outcomes that we can see but cannot (or do not) measure, when it is called the [sign test]9https://en.wikipedia.org/wiki/Sign_test). The sign test is essentially a special case of the binomial test where the probability of success under the null hypothesis is p = 0.5.

It is often used to compare paired samples before and after some intervention, for example we could ask whether people felt better or worse after taking some cold medicine.

Say that 8 of 9 people felt better after taking our new medicine.

```r
binom.test(x = 8, n = 9)
```


```
##  Exact binomial test
## 
## data:  8 and 9
## number of successes = 8, number of trials = 9, p-value = 0.03906
## alternative hypothesis: true probability of success is not equal to 0.5
## 95 percent confidence interval:
##  0.5175035 0.9971909
## sample estimates:
## probability of success 
##              0.8888889
```

The p of 0.04 suggests that this medicine works.


### Comparing counts or proportions: chisq.test()

We can use the `chisq.test()` function to perform a [goodness-of-fit](https://en.wikipedia.org/wiki/Pearson%27s_chi-squared_test) test (testing whether the observed data differs from a theoretical distribution).

If we supply `chisq.test()` with a single vector (i.e., a one-dimensional contingency table) of non-negative integers, the hypothesis tested is whether the population probabilities equal those in `p`, or are all equal if `p` is not given. (You must provide a probabilty for each element of `x` and `p` must sum to 1).

Is 50:50 different from a 1:1 ratio?

```r
# These two give the same answer
chisq.test(x = c(50, 50))
```

```
## 
##  Chi-squared test for given probabilities
## 
## data:  c(50, 50)
## X-squared = 0, df = 1, p-value = 1
```


```r
# But here we explicitly state the probability
chisq.test(x = c(50, 50), p = c(0.5, 0.5) )
```

```
## 
##  Chi-squared test for given probabilities
## 
## data:  c(50, 50)
## X-squared = 0, df = 1, p-value = 1
```

No, 50:50 is not different to 1:1.

Is 50:50 different from a 3:1 ratio?

```r
chisq.test(x = c(50,50), p = c(3/4, 1/4))
```

```
## 
##  Chi-squared test for given probabilities
## 
## data:  c(50, 50)
## X-squared = 33.333, df = 1, p-value = 7.764e-09
```

Yes.


## Two variables
### Testing associations, proportion test: prop.test()


We can compare if the counts of things in different groups is the same between those groups.

For example, do males and females like spinach equally?

Here, the `prop.test()` function requires x a vector of the number of successes in each group, `n` a vector of the number of trials in each group. `x` could also be a matrix or table of 2 columns with successes and failures (in which case you don't need `n`).

For example, here we measure 4/40 males who like spinach and 196/3270 females who like spinach.

```r
prop.test(c(4, 196), c(40, 3270))
```

```
## Warning in prop.test(c(4, 196), c(40, 3270)): Chi-squared approximation may
## be incorrect

## 
##  2-sample test for equality of proportions with continuity
##  correction
## 
## data:  c(4, 196) out of c(40, 3270)
## X-squared = 0.52289, df = 1, p-value = 0.4696
## alternative hypothesis: two.sided
## 95 percent confidence interval:
##  -0.06591631  0.14603864
## sample estimates:
##     prop 1     prop 2 
## 0.10000000 0.05993884
```

So, no. There is no difference in the proportion of males and females who like spinach.

Rather than test whether all groups are equal, we can also specify `p` to say what probabilities we expect each group to have.


### Testing associations, Chi square: chisq.test()

We have used `chisq.test()` to test the goodness-of-fit of a one-dimensional contingency table. If we have a table of at least two rows and two columns, the function interprets this as a two-dimensional contingency table: A Pearson's chi-squared test is performed of the null hypothesis that the joint distribution of the cell counts in a 2-dimensional contingency table is the product of the row and column marginals.

The data we have are our *observed* (O) data. The *expected* (E) data are calculated from the contingency table for each cell using the formula (Row Total x Column Total) / sum of all rows and columns.

The chi-square value is then the sum of [ (O - E)^2 / E ] for each cell.

For example, we might ask whether people who prefer gnocchi to pasta are the same as those who prefer grass to peas

```r
count <- matrix(c(38, 14, 11, 51), nrow = 2, 
                dimnames = list(c('gnocchi', 'pasta'), c('grass', 'peas')))
count
```

```
##         grass peas
## gnocchi    38   11
## pasta      14   51
```

```r
chisq.test(count)
```

```
## 
##  Pearson's Chi-squared test with Yates' continuity correction
## 
## data:  count
## X-squared = 33.112, df = 1, p-value = 8.7e-09
```


The results suggest an association between those who like both grass and gnocchi, and those who like both peas and pasta.

What's the difference between `prop.test()` and `chisq.test()`?

For a 2x2 table, they are essentially the same. See [here](https://stats.stackexchange.com/questions/2391/what-is-the-relationship-between-a-chi-squared-test-and-test-of-equal-proportion).

### Testing associations, Fisher's Exact Test: fisher.test()

[Fisher's Exact Test](https://en.wikipedia.org/wiki/Fisher%27s_exact_test) is similarly used in the analysis of contingency tables. Fisher is said to have devised it after hearing that a colleague could tell whether the [milk or tea was poured into the cup first](https://en.wikipedia.org/wiki/Lady_tasting_tea).

To test this claim, she was given 8 cups of tea, in four of which milk was added first. The null hypothesis is that there is no association between the true order of pouring and the woman's guess, the alternative that there is a positive association (that the odds ratio is greater than 1).


```r
TeaTasting <-
matrix(c(3, 1, 1, 3),
       nrow = 2,
       dimnames = list(Guess = c("Milk", "Tea"),
                       Truth = c("Milk", "Tea")))

TeaTasting
```

```
##       Truth
## Guess  Milk Tea
##   Milk    3   1
##   Tea     1   3
```

```r
fisher.test(TeaTasting, alternative = "greater")
```

```
## 
##  Fisher's Exact Test for Count Data
## 
## data:  TeaTasting
## p-value = 0.2429
## alternative hypothesis: true odds ratio is greater than 1
## 95 percent confidence interval:
##  0.3135693       Inf
## sample estimates:
## odds ratio 
##   6.408309
```

The p = 0.2429 tells us that the association could not be established.


 - - -

Further Reading

Agresti, A. 2002. Categorical Data Analysis. Wiley. [Amazon](https://www.amazon.com/Categorical-Analysis-Agresti-Alan-Hardcover/dp/B008YSYQCS), [Wiley](http://onlinelibrary.wiley.com/book/10.1002/0471249688)

Thompson, L. 2006. S-Plus (and R) *Manual to Accompany Agresti's Categorical Data Analysis *(2002) [2nd edition](http://statweb.stanford.edu/~owen/courses/306a/Splusdiscrete2.pdf).

