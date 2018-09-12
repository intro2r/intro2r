---
layout: default
title: Unit 2 Labs
---

# Unit 2: Working with Data: Labs

These labs test and build on the material presented in the SWIRL lessons.

Scroll down or click [here](../unit2/labs.html#how-to-submit-your-labs) to to check how to submit them.

 - - -

# Lab 1

## 1. Matrix operations I

 a. Create a vector from 1 to 20 using whatever method you like. 
 
 a. Convert this vector into a 4 column matrix.
 
 b. Sum the rows of the matrix, with `rowSums()`.
 
 c. Sum the columns of the matrix, with `colSums()`.

 d. Give the matrix column names (whatever you want).


## 2. Create three separate vectors for shoe size, height, pineapple yes/no

 a. Using these vectors, create a data frame (you may need to google or find external help).
 
 b. Display the first 6 rows of the data frame.
 
 c. Display the last 6 rows of the data frame.
 
 d. Add eye color as another column to the same data frame (do not create a new data frame).
 
 e. Look at the structure and summary of the data frame. Which columns are which data type?

	
## 3. Create a data frame from given data

 a. Look at the head, tail, and summary of data
 
 b. What are the dimensions of the data frame?
 
 c. What is the mean of column X?
 
 d. What is the min of column Y?
 
 e. Plot the values of column Z

 - - -


# Lab 2

## Subsetting with `$`

### 1.  Load in data set

 a. Subset for just column X and assign to a variable
 
 b. Subset by column name using [ ]
 
 c. Check the structure of just column X. What is the data structure?



## Subsetting with [ ] positionally (one dimension)

### 2. Use the vector you just pulled out

 a. Display just the first element of the vector

 b. Display just the last element of the vector
 
 c. Display the 2, 5, and 9th element of the vector
 
 d. Display the first 5 elements of the vector
 
 e. Remove the first 4 elements of this vector


## Subsetting with [ ] logically (one dimension)

### 3. Use the same vector

 a. Display all values of the vector less than 8
 
 b. Display all values of the vector more than 4
 
 c. Display all values of the vector more than 4 and less than 8
 
 d. Display all values of the vector less than 4 or more than 8
	

## Subsetting in two dimensions

### 4. Use this data frame

 a. Display the first element of the first column
 
 b. Display the entire first row
 
 c. Display the entire 2nd column without its name
 
 d. Display the 2-5th rows and the 3-4th columns
 
 e. Display column Xs values that are more than 10
 
 f. Display column Xs values for where column Y responded TRUE
 
 g. Make a boxplot of column Xs for which column Y is FALSE
 
 h. Remove the 3rd row of data


 - - -


# Lab 3


## 1. Read in the following clean data sets:

 a. .txt (tab-delim). Display the first 10 rows.
 
 b. .csv (, delim). What is the mean X?
 
 c  something else. How many rows and columns does this data have?



## 2. Clean and read in the following data sets

 a.
 
 b.
 
 c.



## 3. Clean and read in the `birdflu.xls` spreadsheet.

 a.
 
 b.
 
 c.
 
 d.

	Birdflu questions



 - - -


# Lab 4: Unit 2 Recap



## 1. Working with lists

 a. Create a matrix.
 
 b. Create a data frame.
 
 c. Create a vector.
 
 d. Put all three objects in a list.
 
 e. Subset the data frame from the list by its name.
 
 f. Subset a column in the data frame in the list.
 
 g. Subset the vector by its position in the list.



## 2. Use the `birdflu.xls` spreadsheet again

 a. Edit the birdflu spreadsheet from a wide format to a long format. 
 
 b. Read in the edited birdflu data
 
 c. How many deaths were there in year?
 
 d. How many cases were there in country in all years?
 
 e. How many cases were there in country in year?



## 3. Class survey data

 a. Try to read in the class survey data file.
 
 b. Fix survey and read in again.
 
 c. Find the average of this column.
 
 d. Find the average of column on one factor and the other.
 
 e. A few more subsets.
 
 f. Plot a few things.

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


