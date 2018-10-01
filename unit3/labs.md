---
layout: default
title: Unit 3: Labs
---


# Unit 3. Analyzing Grouped Data: Labs

These labs test and build on the material presented in the SWIRL lessons.

Scroll down or click [here](../unit3/labs.html#how-to-submit-your-labs) to to check how to submit them.

## Due Dates

Lab 1 and 2: 2018-10-05 23:58

Lab 3 and recap: 2018-10-12 23:58

(no best practice lab)

 - - -
 

## Lab 1

### 1) Choose and justify a statistical test for the following scenarios.

  a. We have counts for three tree species before and after a fire, and want to know whether the fire changed their relative abundance.

  b. We have data on total lifetime income and age of mortality, and want to know whether there is a relationship between the two.

  c. We sampled soil organic nitrogen content in 30 random plots across 4 different sites, and want to know whether average soil nitrogen differs between each site.

  d. Our survey respondents answered either `yes` or `no` when asked whether they believed in anthropogenic climate change, and we want to know whether their age has an effect.

 

### 2) Read in the class survey data and answer the following questions.

  a. Which variables are continuous?

  b. Which variables are categorical? Are any binomial?

  c. Check the distribution of class height and number of Harry Potter books read. Do they appear normally distributed? Note that you can use the `breaks` argument in hist() if you want to decrease the bin size of your histogram.

  d. Plot ideal temperature. Are there any outliers?

 

### 3) Read in your cleaned Michigan tree species data.

  a. We want to compare mean diameter at breast height (dbh) between each species. Assess visually whether DBH is normally distributed.

  b. Assess visually whether there is equal variance in DBH between each species.

  c. Based on these tests, do you think an ANOVA is an appropriate test comparing average dbh in each species?

  d. Enter the following code: ` m1 <- aov(dbh ~ species, data = data_name)` where data_name is the name of your data frame. You just performed an ANOVA!

  e. Plot the model residuals as a function of the fitted values (remember `~` from the lesson). Does it seem like our model fit the data? 
  
  - - -


## Lab 2

1. Binomial tests for flowering trees example

2. Chi sq tests
  a. Fish data
  b. Bird data

3. Use survey data to answer a question (it will be helpful to make use of the table() function here)
  a. Tea to coffee is it 50/50
  b. Your TA Andrew loves pineapple on his pizza – prior to this class, he was the only one we knew about. Using class responses, test whether Andrew is truly the only one who likes pineapple on his pizza.
  c. Do people with shoe sizes over 10 prefer pineapple?


## Lab 3


1. Michigan Tree Plot data. You may need to use google or the R help files…

2. New Haven road race data

3. Survey data

 - - -


## Lab 4

Use the sparrow data

1. Read in and evaluate data
  a. Check assumptions/for data abnormalities
  b. Make histograms

2. Answer the following questions
  a. Is there a skewed gender ratio, and make a plot to visualize
  b. Are there equal number of adults and juveniles, and make a plot to visualize

3. Answer the following questions
  a. Tarsus in females vs males, show with boxplot and barplot
  b. Head size in adults vs juveniles, show with boxplot and barplot
  c. Wing size by observer, post hoc tests to identify problem observers
  d. Anatomy measuring by both species and sex, is there an interaction and what is it telling you
  e. Compare means of the four combinations of variables


 
 - - -
 
# How to submit your labs

## How to write up your lab answers

You will need to write R code to answer each of the questions.

Please format your answers as follows:

 - Copy and paste each question, commented out. This ensures that we know which answer corresponds to which question.

  - Write your R code answer below each question.

It should look something like this:

```
# LAB: Unit 1. Lab 1
# Your Name #  Put your name here

# 1. Add 7 and 3,456.
7 + 3456

# 2. Assign this value to an object
x <- 7 + 3456
```

## How to submit your lab answers on Canvas

 - Log into Canvas.

 - Go to the Assignments page.

 - Under ‘Labs’, you should find the correct assignment.

 - Copy and paste your R code into the text box.

 - Click ‘Submit Assignment’.

You are permitted to submit your answers as many times as you like within each Unit.

Answers will be graded two or three times a week and re-opened if you submit early.

Each lab will close at its respective deadline (see Canvas).

Final grades for each lab will be computed and entered into the Canvas gradebook at the end of each Unit.


