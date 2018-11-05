---
layout: default
title: Unit 5: Labs
---


# Unit 5. Graphics and Programming: Labs

These labs test and build on the material presented in the SWIRL lessons.

Scroll down or click [here](../unit5/labs.html#how-to-submit-your-labs) to to check how to submit them.

## Due Dates

Lab 1 and 2: 2018-11-09 23:58

Lab 3 and recap: 2018-11-16 23:58


 - - -
 
## Lab 1

Using the sparrow data set.

```r
dat <- read.table(file = "http://www.intro2r.info/data/sparrows.txt", header = TRUE)
```

## 1. Create a plot with 4 panels (2 x 2).

The panels should show the following barplots:

 - top left, the number of males and females of species SESP
 - top right, the number of males and females of species SSTS
 - bottom left, the number of individuals in each species that are male
 - bottom right, the number of individuals in each species that are female

To help aid comparisons, make sure that the y axes for the two plots in each row have the same range.

Each panel should have x and y axis labels in bold.


# 2. For species SSTS, make a three-panel horizontal figure.

Plot Tarsus, Head, and Weight each as a function of Sex in separate panels.

Ensure that males and females are different colours.

Each panel should have the lines wider than the default width and horizontal y-axis numbers.


## 3. Make a five-panel plot.

Plot Wingcrd as a function of Tarsus, Head, Culmen, Weight, and Nalospi, differentiating each species by colour and/or symbol.

Ensure that the tick marks point inwards and the axis labels have units (you can make up what the units are).


 
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



