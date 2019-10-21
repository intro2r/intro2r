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
    
  a. Plot this relationship, and be sure to add your regression line to the plot. Add axis labels.

  b. How well does your model fit? Plot the residuals against the fitted values, and identify any possible issues if they exist.

  c. Check the normality of your residuals, another key assumption.
 
### 3. Plot the data set again.
  
  a. Are there any apparent relationships with housing values that aren’t linear?
  
  b. Identify one, and do the following:
  
  i. Try to linearize the relationship by applying a transformation to the predictor. Common transformations include log, square root, and square. Make two plots, one of housing value against the untransformed predictor, and the other against the transformed predictor. Add axis labels.
    
  ii. Make two models, where your predictor is either transformed vs untransformed.

  iii. Check the model summaries. Which has a better R-squared value (a measure of model fit)?
 
### 4. Enter the following data and answer the following questions

```
pirate <- data.frame(Temp = c(14.2, 14.4, 14.55, 14.8, 15.25, 15.5, 15.85),
                     Npirates = c(35000, 45000, 20000, 15000, 5000, 400, 17),
                     Year = c(1820, 1860, 1880, 1920, 1940, 1980, 2000))
```

  a. Plot the relationship between temperature and number of pirates. Add axis labels.
  
  b. Test this relationship statistically. Why did you choose this test?
 

 
## Lab 2

### 1. Access the Orange data set and answer the following questions.

```
data(Orange)
?Orange
```

  a. Plot circumference as a function of age. Add axis labels.

  b. Test for an effect of age on circumference.

  c. Is this relationship the same for all Trees? Run a model to test this.

  d. Add fitted lines for each Tree to the figure.
 




### 2. Read in the housing value data set for question 2.

    
  a. Perform 3 separate multiple regressions with housing value as your response, combining predictors in any way you see fit. You can include as many predictors as you think are important for each model, with a minimum of 2, including any interactions you think might exist.

  b. Ensure your predictors aren’t collinear in each model.
  
  c. Which of your models best fits the data? Test this statistically. 




## Lab 3

### 1. Flowering trees

Read in the data

```
dat <- read.table(file = "http://www.intro2r.info/data/flowering.txt", 
                  header = TRUE, sep = '\t')
```

This dataset contains information on flowering of 1500 Myrsticaceae trees in 2002 in the Yasuni Forest Dynamics Plot, a tropical lowland rain forest in Ecuador. 

There are data on seven species (`$SpCode`), their size (`$dbh`), their sex (`$Sex`: 0, F, M), if they flowered that year (`$Flowers`: 1/0), and an index of light availability in the canopy (`$CII`:, 0-5, with 0 being no light and 5 being full overhead and side light).

  a. Examine the structure of the data.

  b. Look at the first 7 rows.

  c. Is the ratio of flowering to non-flowering trees different from 1:1 (over all species)?

  d. Is the ratio of M to F trees different from 1:1 (over all species)?

  e. Size is likely a key factor affecting the chance of flowering in one year. Model the probability of flowering as a function of size for the species iryapa.

  f. Plot the data and the predicted curve of this relationship. Add axis labels.


### 2.Horse kicks

The [horsekick data](http://www.intro2r.info/data/horsekicks.txt) give the number of soldiers in the Prussian cavalry killed by horse kicks, by corp membership and by year. The years are from 1875 to 1894, and there are 14 different cavalry corps: the first column corresponds to the guard corp and the other columns to corps 1 through 11, 14, and 15. 

The data are from Distributome project and are derived from the book by Andrews and Herzberg. The original source of the data is the classic book by von Bortkiewicz (references are given below). The data are famous because they seem to fit the Poisson model reasonably well.

You will likely need to reformat the data.

  a. Test whether there were differences in the number of deaths between companies.

  b. Was any year particularly bad for deaths?


## Recap

 For the unit recap, we will use the “state.x77” dataset that comes preloaded in R.

```r
data(state)
head(state.x77)
```
 
```
           Population Income Illiteracy Life Exp Murder HS Grad Frost   Area
Alabama          3615   3624        2.1    69.05   15.1    41.3    20  50708
Alaska            365   6315        1.5    69.31   11.3    66.7   152 566432
Arizona          2212   4530        1.8    70.55    7.8    58.1    15 113417
Arkansas         2110   3378        1.9    70.66   10.1    39.9    65  51945
California      21198   5114        1.1    71.71   10.3    62.6    20 156361
Colorado         2541   4884        0.7    72.06    6.8    63.9   166 103766
```


### 1. First prepare the dataset to make it useful for analysis.

  a. Check the structure of your data.

  b. Convert it into a data frame.

  c. Rename problematic variable names in your new data frame.

 

### 2. Lets try to explain life expectancy based on some of our variables.

  a. Explore the data in the following ways to identify variables associated with life expectancy (identify at least 2)
    i. Using pairwise plots of variables i.e. plot the dataset
    ii. Using a PCA and associated biplot (if you're having trouble reading the plot, either get rid of your row names, or scale    your point size down with the cex = argument).

  b. Do a simple regression for each association identified. Which one fits best?

  c. Plot each of these associations. Make sure to give your plots proper axis labels and a title. Add the fitted line to each plot, give it a color other than black, and double its line width.

 d. Now do a multiple regression with all of your predictors. Are all the predictors you identified in 2a still important?


### 3. Now lets practice some logistic regression

  a. Maybe we have an expectation that there’s an important threshold at 50% high school graduation rate, and wish to model this. Convert the high school graduation variable into a binary dummy variable, where <50% is 0 and >50% is 1.

  b. Perform a logistic regression, using any predictor you think might be important.

  c. Plot this relationship, give your plot proper labels, and include the fitted logistic regression line (which you’ll have to predict)

 

### 4. Now lets practice modeling count data

  a. Check the distribution of the population variable. Does it appear normal?

  b. Check the distribution of the area variable. Does it appear normal?

  c. Lets model population as a function of area

   i. Transform your predictor (area) so that its normally distributed.

   ii. Make the model. Is area a significant predictor of population?

   iii. Model this relationship without specifying the family argument (i.e. make glm() think your response variable is normally distributed). Is area still important?



 
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


