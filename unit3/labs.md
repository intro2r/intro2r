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

  *For bonus points...* d. Our survey respondents answered either `yes` or `no` when asked whether they believed in anthropogenic climate change, and we want to know whether their age has an effect.

 

### 2) Read in the class survey data and answer the following questions.

The class survey data are found on the [Data](http://www.intro2r.info/data/) page.

  a. Which variables are continuous?

  b. Which variables are categorical? Are any binomial (do any have only 2 levels)?

  c. Check the distribution of class height and number of Harry Potter books read. Do they appear normally distributed? Note that you can use the `breaks` argument in `hist()` if you want to decrease the bin size of your histogram.

  d. Plot ideal temperature. Are there any outliers?

 

### 3) Read in your cleaned Michigan tree species data.

  a. We want to compare mean diameter at breast height (dbh) between each species. Assess visually whether DBH is normally distributed.

  b. Assess visually whether there is equal variance in DBH between each species.

  c. Based on these tests, do you think an ANOVA is an appropriate test comparing average dbh in each species?

  d. Enter the following code: ` m1 <- aov(dbh ~ species, data = data_name)` where data_name is the name of your data frame. You just performed an ANOVA!

  e. Plot the model residuals as a function of the fitted values (remember `~` from the lesson). Does it seem like our model fit the data? 
  
  - - -
  

## Lab 2

### 1. Using `table()` or `hist()`, tabulate the following.

a. From the New Haven road race data: 
  
  i. the number of people running who were and were not from New Haven,
  
  ii. ten equal-sized categories (i.e., bins of equal range) of running time,
  
  iii. the number of people of each gender in each age category.

b. From the Michigan tree data:

  i. the number of trees in each species,
  
  ii. the number of trees greater and less than 1 meter dbh,
  
  iii. the number of trees per species that are alive versus dead.

c. From the class survey data:

  i. The number of people in each House,
  
  ii. the number of people of each eye colour,
  
  iii. the number of people of each eye colour and House,
  
  iv. the number of people less than 1 meter, 1--2 meters, and >2 meters tall,
  
  v. the number of people who can roll/not their tongue and number of siblings.
 

### 2. Backyard birds

In the October of 2015, Jane saw 12 black-capped chickadees, 2 red-bellied woodpeckers, and a canada goose in her back yard. This year, she saw 10 back-capped chickadees, 5 red-bellied woodpeckers, and 1 zebra. Has the bird population changed significantly?

### 3. Tree phenology

John studies the reproductive phenology of trees. In 2014, 59 male trees flowered and 34 female trees. 

  i. Is this population male-biased?

  ii. In 2015, 71 male trees flowered and 39 female trees. Had the proportion of male-flowering trees changed?


### 4. A fish survey 

was done to see if the proportion of fish types is consistent with previous years. Suppose, the 3 types of fish recorded: parrotfish, grouper, tang are historically in a 5:3:4 proportion and in a survey the following counts are found:

| Fish | parrotfish | grouper | tang |
|----- | -- | -- | -- |
|observed | 53 | 22 | 49 |
{: .table table-bordered .table-striped}

Have the proportions of each species changed?

### 5. Using the class survey data: 

a. Is the ratio of people who like tea to coffee 50:50?
  
b. Your TA, Andrew, loves pineapple on his pizza---prior to this class, he was the only one we knew about. Using class responses, test whether Andrew is truly the only one who likes pineapple on his pizza.
  
c. Do people with shoe sizes over 10 prefer pineapple on their pizza?


## Lab 3

Use the `*apply()` group of functions to answer the following questions. 

Each question should require only one line of code, once the data are read in.


### 1. Michigan tree plot data 

Calculate:

a. The mean and standard deviation of dbh of each species, for all trees.

b. The mean and standard deviation of dbh of each species for alive and dead trees. 

c. The number of trees of each species that are alive and dead.


### 2. New Haven road race data

Calculate:

  a. Mean race time for all genders.

  b. The fastest race time for each age class.

  c. The number of runners in each age class-gender combination.
  

### 3. Class survey data

Calculate:

  a. The median shoe size of people in each House.
  
  b. The mean height of folks according to whether they prefer tea or coffee and whether they can roll their tongue.
  
  c. The maximum home town population of people according to their preferred vacation, pizza topping, and favorite color.

 - - -


## Lab 4

Use the sparrow data (see the Data page).

Read in the data.

### 1. Is there a skewed gender ratio between males and females for all the sparrows pooled? 

Perform the appropriate test, and create an appropriate plot to visualize. The barplot() function may be helpful here.

### 2. Do the two species have different gender ratios? 

Perform the appropriate test.

### 3. Is there a difference in tarsus size between species? 

Check assumptions, perform the appropriate test, and create an appropriate plot to visualize. 

### 4. Was there an influence of observer on culmen measurements? If so, which observers had significantly different measurements from each other? 

Check assumptions and perform the appropriate test. Be sure that your observer variable is properly encoded as a factor. 

### 5. Is there an interaction between Sex and Species on Culmen size? 

Perform the appropriate test and, if so, interpret the model output. Run a post-hoc test if needed.


 
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


