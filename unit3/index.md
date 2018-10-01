---
layout: default
title: Analyzing Grouped Data
---

# Analyzing Grouped Data

In this unit, you will learn classical statistical tests and how to compare means between groups.

Follow the links to each lecture, lab, and reading.

Scroll down to download the SWIRL lessons.


## Lesson 1. How to choose a statistical test

Lectures: 

[Which test? Which assumptions?](../unit3/which-test.html)

[Formulae](../unit3/formulae.html)

Learning Goals:

 - Understand the different arrangements and distributions of data,
 - Understand what tests are appropriate for what questions and data,
 - Test assumptions such as normality, homogeneity of variance, outliers,
 - Plot data to examine distributions.

SWIRL: [Testing assumptions and exploring data](../unit3/swirl/Testing_Assumptions_and_Exploring_Data.html)

Lab: [Unit 3: Lab 1](../unit3/labs.html)

Readings: 

Zuur et al. 2010. [A protocol for data exploration to avoid common statistical problems](https://www.dair.nl/wp-content/uploads/2017/03/Zuur_et_al-2010-Methods_in_Ecology_and_Evolution.pdf). *Methods in Ecology & Evolution* 1, 3–14.

Läärä, E. 2009. [Statistics: reasoning on uncertainty, and the insignificance of testing null](http://www.sekj.org/PDF/anz46-free/anz46-138.pdf). *Ann. Zool. Fennici* 46: 138–157. 

Functions: `qqplot()`, `ks.test()`, `shapiro.test()`, `bartlett.test()`


## Lesson 2. How to compare counts between groups

Lecture: [Testing ratios and tabulating data](../unit3/testing-ratios.html)

Learning Goals:

 - Use of `table()`,
 - Convert continuous data to groups,
 - Run simple sign, proportion, binomial, and Chi-square tests.

SWIRL: [Testing Ratios](../unit3/swirl/testing-ratios.html)

Lab: [Unit 3: Lab 2](../unit3/labs.html)

Reading:

Functions: `table()`, `prop.test()`, `binom.test()`, `chisq.test()`

## Lesson 3. How to calculate group-level stats in dataframes

Lecture: [The Split-Apply-Combine approach](../unit3/split-apply-combine.html)

Learning Goals:

 - Understand and use `tapply()`, `sapply()`, `lapply()`, `apply()`.
 - Calculate and plot group-level means and sd.

SWIRL: The *apply() group of functions:

 - [lapply and sapply](../unit3/swirl/lapply_and_sapply.html)
 
 - [vapply and tapply](../unit3/swirl/vapply_and_tapply.html)

Lab: [Unit 3: Lab 3](../unit3/labs.html)

Reading: Wickham, H. 2001. [The Split-Apply-Combine Strategy for Data Analysis](https://www.jstatsoft.org/article/view/v040i01/v40i01.pdf). *Journal of Statistical Software* 40. 

Functions: `apply()`, `tapply()`, `sapply()`, `lapply()`


## Lesson 4. How to compare means from different groups or populations

Lecture: [t-tests and ANOVAS](../unit3/testing-populations.html)

Best Practice:

Learning Goals:

 - Run t-tests and ANOVAs,
 - Test assumptions of normality, homogeneity of variance
 - Extract details from model output,
 - Plot these data with boxplots and barplots.

SWIRL: [Testing Populations](../unit3/swirl/testing-populations.html)

Lab: [Unit 3: Recap](../unit3/labs.html)

Reading:

Functions: `t.test()`, `aov()`,

 - - -
 
 Updated: 2018-10-01
 
