---
layout: default
title: Unit 5: Labs
---


# Unit 5. Graphics: Labs

These labs test and build on the material presented in the SWIRL lessons.

Scroll down or click [here](../unit5/labs.html#how-to-submit-your-labs) to to check how to submit them.


 - - -
 
## Lab 1

Using the sparrow data set.

```r
dat <- read.table(file = "http://www.intro2r.info/data/sparrows.txt", header = TRUE)
```

### 1. Create four barplots. For all graphs in this lesson, ensure you have proper axis labels. 

Show the following: 

i. the number of males and females of species SESP,
ii. the number of males and females of species SSTS,
iii. the number of individuals in each species that are male,
iv. the number of individuals in each species that are female.


### 2. For species SSTS, make two histograms.

Plot the distribution of Head for (i) males and (ii) females.


### 3. Make two plots.

Plot Wingcrd as a function of (i) Tarsus and (ii) Head.


### 4. Make two boxplots.

Plot (i) Tarsus as a function of Sex and (ii) Head as a function of Sex. 


 - - -
 
## Lab 2
 
Using the sparrow data set.

```r
dat <- read.table(file = "http://www.intro2r.info/data/sparrows.txt", header = TRUE)
```


### 1. Create four barplots again.


Show the following: 

i. the number of males and females of species SESP,
ii. the number of males and females of species SSTS,
iii. the number of individuals in each species that are male,
iv. the number of individuals in each species that are female.

To help aid comparisons, make sure that the y axes for each plot has the same range.

Each plot should have x and y axis labels in bold.


### 2. For species SSTS, make two histograms again.

Plot the distribution of Head for (i) males and (ii) females.

Ensure that males and females are different colours.

Each plot should have axis lines wider than the default width and horizontal y-axis numbers.


### 3. Make two plots again.

Plot Wingcrd as a function of (i) Tarsus and (ii) Head.

Differentiate each species by colour and symbol.

Ensure that the tick marks point inwards and the axis labels have units (you can make up what the units are).


### 4. Make two boxplots again.

Plot (i) Tarsus as a function of Sex and (ii) Head as a function of Sex. 
 
Make sure that each sex has a consistent color.



- - -

## Lab 3

### 1. Make two boxplots again.

Plot (i) Tarsus as a function of Sex and (ii) Head as a function of Sex. 
 
Add points for the raw data.


### 2. Plot the data again, but instead of boxplots, use stripcharts to display all the data points. 

Calculate the mean Head size and Tarsus size for both species x sex combination.
 
Superimpose the mean values on top and add error bars. 
 
Ensure that the data points are paler and the summary data stand out. (Check the bestiary for details on stripcharts).


### 3. Plot Head as a function of Tarsus.

Ensure that the points for each sex and species are different but consistent (e.g., circles for species 1, squares for species 2, empty for males, filled for females). 


- - -


## Lab 4 & Recap: Tree plot in Michigan 

![](../unit5/img/treeplot.png)

*Trees in a 1-ha plot on East Lansing, MI, USA. Colours indicate different species; size of symbol indicates DBH.*

```r
# Read in the data
dat_tree <- read.table("http://www.intro2r.info/data/treespecies_cleandata.txt", 
                       header = TRUE, sep = '\t')
```


### 1. Create a similar plot map to the above:

- Use colour and symbols to distinguish species.
 
- Scale symbol size to DBH.

- Use nice axis labels and ensure that tick numbers are horizontal.


### 2. Make a histogram of the DBH of blackoak.

 - Use wider lines.
 
 - Label the axes with units.
 

### 3. Display boxplots of DBH for alive and dead trees.

Make a single figure containing two boxplots of tree DBH, one for alive and one for dead trees.

 - Fill each box a different colour.

 - Add an arrow and a label identifying the species of the outlier in the boxplot of dead trees.


### 4. Make a dotplot illustrating the mean and SE of DBH for alive and dead trees of hickory.

Make a similar plot to the boxplots above (q3), but instead of boxes, display the datapoints for each tree. Ensure that these points are a paler shade of grey.

 - Overlay segments to display the SE of the mean for alive and dead trees.

 - Overlay larger and darker points indicating the mean DBH of alive and dead trees.




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



