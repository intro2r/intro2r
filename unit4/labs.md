---
layout: default
title: Unit 4: Labs
---


# Unit 4. Analyzing Continuous Data: Labs

These labs test and build on the material presented in the SWIRL lessons.

Scroll down or click [here](../unit4/labs.html#how-to-submit-your-labs) to to check how to submit them.

## Due Dates

Lab 1 and 2: 2018-10-26 23:58

Lab 3 and recap: 2018-11-02 23:58


 - - -
 
## Lab 1

Read in the housing value [data set](http://www.intro2r.info/data/) for questions 1-3.

### 1. Plot the entire data set.
  
  a. Which variables appear correlated with housing value?

  b. Find the correlation coefficients between housing value and those variables identified in a.
 
### 2. Perform a simple linear regression with one predictor and housing value as your response variable (your y).
    
  a. Plot this relationship, and be sure to add your regression line to the plot.

  b. How well does your model fit? Plot the residuals against the fitted values, and identify any possible issues if they exist.

  c. Check the normality of your residuals, another key assumption.
 
### 3. Plot the data set again.
  
  a. Are there any apparent relationships with housing values that aren’t linear?
  
  b. Identify one, and do the following:
  
  i. Try to linearize the relationship by applying a transformation to the predictor. Common transformations include log, square root, and square. Make two plots, one of housing value against the untransformed predictor, and the other against the transformed predictor.
    
  ii. Make two models, where you predictor is either transformed vs untransformed.

  iii. Check the model summaries. Which has a better R-squared value (a measure of model fit)?
 
### 4. Enter the following data and answer the following questions

```
pirate <- data.frame(Temp = c(14.2, 14.4, 14.55, 14.8, 15.25, 15.5, 15.85),
                     Npirates = c(35000, 45000, 20000, 15000, 5000, 400, 17),
                     Year = c(1820, 1860, 1880, 1920, 1940, 1980, 2000))
```

  a. Plot the relationship between temperature and number of pirates.
  
  b. Test this relationship statistically. Why did you choose this test?
 

 
## Lab 2

### 1. Access the Orange data set and answer the following questions.

```
data(Orange)
?Orange
```

  a. Plot circumference as a function of age.

  b. Test for an effect of age on circumference.

  c. Is this relationship the same for all Trees? Run a model to test this.

  d. Add fitted lines for each Tree to the figure.
 


Read in the housing value data set for question 2.

### 2. Perform 3 separate multiple regressions with housing value as your response, combining predictors in any way you see fit. 

You can include as many predictors as you think are important for each model, with a minimum of 2, including any interactions you think might exist.
    
  a. Ensure your predictors aren’t collinear in each model.

  b. Which of your models best fits the data? Test this statistically. 




## Lab 3


## Recap




 
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


