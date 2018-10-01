---
layout: default
title: Analyzing Grouped Data
---

# Analyzing Grouped Data

In this unit, you will learn classical statistical tests and how to compare means between groups.

Follow the links to each lecture, lab, and reading.

Scroll down to download the SWIRL lessons.


## Lesson 1. How to choose a statistical test

Lecture: [Which test? Which assumptions?](/which-test.html)

Learning Goals:

 - Understand the different arrangements and distributions of data,
 - Understand what tests are appropriate for what questions and data,
 - Test assumptions such as normality, homogeneity of variance, outliers,
 - Plot data to examine distributions.

SWIRL: [Testing assumptions and exploring data](data-exploration.html)

Lab: [Unit 3: Lab 1](../unit3/labs.html)

Reading:

Functions: `qqplot()`, `ks.test()`, `shapiro.test()`, `bartlett.test()`


## Lesson 2. How to compare counts between groups

Lecture: [Testing ratios and tabulating data](/testing-ratios.html)

Learning Goals:

 - Use of `table()`,
 - Convert continuous data to groups,
 - Run simple sign, proportion, binomial, and Chi-square tests.

SWIRL: [Testing Ratios](testing-ratios.html)

Lab: [Unit 3: Lab 2](../unit3/labs.html)

Reading:

Functions: table(), prop.test(), binom.test(), chisq.test()

## Lesson 3. How to calculate group-level stats in dataframes

Lecture: [The Split-Apply-Combine approach](group-means.html)

Learning Goals:

 - Understand and use `tapply()`, `sapply()`, `lapply()`, `apply()`.
 - Calculate and plot group-level means and sd.

SWIRL: [The *apply() group of functions](/swirl/apply.html)

Lab: [Unit 3: Lab 3](/labs.html)

Reading:

Functions: `apply()`, `tapply()`, `sapply()`, `lapply()`


## Lesson 4. How to test for associations

Lecture: [t-tests and ANOVAS](/anova.html)

Best Practice:

Learning Goals:

 - Run t-tests and ANOVAs,
 - Test assumptions of normality, homogeneity of variance
 - Extract details from model output,
 - Plot these data with boxplots and barplots.

SWIRL: [Testing Populations](/swirl/testing-populations.html)

Lab: [Unit 3: Recap](../unit3/labs.html)

Reading:

Functions: `t.test()`, `aov()`,

 - - -
 
 Updated: 2018-10-01
 
