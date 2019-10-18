---
layout: default
title: Unit 6: Labs
---


# Unit 6. Programming: Labs

These labs test and build on the material presented in the SWIRL lessons.

Scroll down or click [here](../unit6/labs.html#how-to-submit-your-labs) to to check how to submit them.


 - - -
 
## Lab 1


## Tree plot in Michigan 

![](../unit5/img/treeplot.png)

*Trees in a 1-ha plot on East Lansing, MI, USA. Colours indicate different species; size of symbol indicates DBH.*

```r
# Read in the data
dat_tree <- read.table("http://www.intro2r.info/data/treespecies_cleandata.txt", 
                       header = TRUE, sep = '\t')
```

![](../unit5/img/dbh.png)


1. Write a function to calculate basal area (remember that BA = radius^2 * pi).

2. Calculate the basal area of each tree.

3. Calculate the total BA of all trees.

4. Using `tapply()`, calculate the mean BA of each species 

5. Using one call to `tapply()` what is the total BA of (i) alive trees, and (ii) dead trees?

6. Write a function to generate a map (an x-y plot) of the trees. Set some nice defaults. Establish a 2 x 3 grid of panels in a figure, and use this function to make a map of each species.

- - -


## Lab 2: More Trees!

### 1. Write a loop to read in each of the following six files, one for each species.

You can either read them in from the URLs, or download them to your hard drive and read them in from there.

There are several ways to do this.

Think about what data object/s you want to create.

You might want to use `paste()`. 

```
http://www.intro2r.info/data/blackoak.txt
http://www.intro2r.info/data/hickory.txt
http://www.intro2r.info/data/maple.txt
http://www.intro2r.info/data/misc.txt
http://www.intro2r.info/data/redoak.txt
http://www.intro2r.info/data/whiteoak.txt
```

### 2. Write a loop to make the same 2 x 3 panel figure of maps as for Lab 3 Q6.
 
 - Use your custom plotting function from Lab 3.

 - Make sure to use a loop!


### 3. Create six random tree communities of 100 trees from the full trees dataset

 - Use `sample()`.
 
 - Create a list, and have each element of this list be a community.
 
 - Plot the six communities. Ensure that point size is proportional to DBH.
 
 - Calculate the mean DBH of each community.


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



