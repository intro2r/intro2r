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


## 2. Create vectors from shoe size, favorite animal, pineapple yes/no


**Table 1.** Ten random responses from the class survey. 

| Height | Eye Color | Shoe Size | # Siblings | Home Pop. | HP Books | HP House   | Ideal Temp | Fav Color | Tea or Coffee | Pineapple on Pizza?  | Roll your Tongue? | Tree or Pollen Allergy     |
|--------|-----------|-----------|----------|----------|----------|------------|------------|-----------|------------|------------|-------------|-------------|
| 175    | Brown     | 10        | 2        | 4621     | 7        | Hufflepuff | 21         | Blue      | Coffee     | Yes        | Yes         | Both |
| 177.8  | Blue      | 10        | 2        | 200000   | 7        | Ravenclaw  | 21         | Blue      | Coffee     | Yes        | Yes         | Neither     |
| 167.64 | Hazel     | 9.5       | 3        | 4988     | 0        | Hufflepuff | 15.56      | Blue      | Coffee     | Disgusting | No          | Both |
| 183    | Hazel     | 11.5      | 2        | 62243    | 5        | Ravenclaw  | 21         | Blue      | Coffee     | Yes        | Yes         | Both |
| 163    | Hazel     | 9         | 1        | 3300     | 7        | Hufflepuff | 18.9       | Green     | Coffee     | Disgusting | Yes         | Both |
| 175.26 | Blue      | 11        | 2        | 21845    | 7        | Gryffindor | 26         | Red       | Tea        | Yes        | Yes         | Neither     |
| 165    | Brown     | 8         | 0        | 9000000  | 7        | Hufflepuff | 20         | Purple    | Coffee     | Yes        | Yes         | Neither     |
| 162.56 | Brown     | 7         | 2        | 27865    | 7        | Gryffindor | 23         | Yellow    | Coffee     | Disgusting | Yes         | Neither     |
| 167    | Brown     | 7.5       | 0        | 80000    | 7        | Ravenclaw  | 23         | Blue      | Coffee     | Disgusting | Yes         | Both |
| 167    | Brown     | 8.5       | 5        | 3500     | 0        | Hufflepuff | 27         | Blue      | Coffee     | Disgusting | Yes         | Neither     |
{: .table table-bordered .table-striped}

 a. Using these vectors, create a matrix.

 b. Convert this matrix to a data frame (you may need to google or find external help).
 
 b. Display the first 6 rows of the data frame.
 
 c. Display the last 6 rows of the data frame.
 
 d. Add eye color as another column to the same data frame (do not create a new data frame).
 
 e. Look at the structure and summary of the data frame. Which columns are which data type?

	
## 3. Create a data frame from these data


**Table 2.** Apple production in selected countries in 2016 (*Source:* FAO).

| Country |     Harvested area (ha) |     Apple production (tonnes) | 
|---     |     -------------------|   ---------|
| China |     2383815 |     44447793 |  
| India |     314000 |     2872000 |  
| Iran |     238638 |     2799197 |  
| Russia |     214270 |     1843544 |  
| Poland |     177203 |     3604271 |  
| Turkey |     173394 |     2925828 |  
| United States |     130552 |     4649323 |  
| Uzbekistan |     101726 |     1120209 |  
| Pakistan |     91928 |     590039 |  
| Ukraine |     91600 |     1099240 |  
| Italy |     56164 |     2455616 |  
| France |     49618 |     1819762 |  
| Chile |     36063 |     1759421 |  
| Ukraine |     91600 |     1099240 |  
| Brazil |     33981 |     1049251 |  
| Germany |     31334 |     1032913 |  
| United Kingdom |     16512 |     481100 |  
{: .table table-bordered .table-striped}

 a. Display the head, tail, and summary of data.
 
 b. What are the dimensions of the data frame?
 
 c. What is the mean of Harvested area?
 
 d. What is the minimum apple production?
 
 e. Plot the values of apple production on harvested area.

 - - -


# Lab 2

Read in the following data frame (copy and paste into your R console).
This data details CO2 emissions from various sources in 2015. (*[Source](https://en.wikipedia.org/wiki/List_of_countries_by_carbon_dioxide_emissions)*)
```r
CO2_2015 <- data.frame(
   Country  = c('World', 'China', 'United States', 'European Union', 'India', 'Russia', 'Japan', 'Germany', 'International Shipping', 'Iran', 'South Korea', 'Canada', 'Saudi Arabia', 'Indonesia', 'International Aviation'), 
    Total_kt = c(36061710, 10641789, 5172336, 3469671, 2454968, 1760895, 1252890, 777905, 642024, 633750, 617285, 555401, 505565, 502961, 502936),
    Percent_World_CO2  = c(100.00, 29.51, 14.34, 9.62, 6.81, 4.88, 3.47, 2.16, 1.78, 1.76, 1.71, 1.54, 1.40, 1.39, 1.39),
    Per_capita_t = c(NA , 7.7, 16.1, 6.9, 1.9, 12.3, 9.9, 9.6, NA , 8, 12.3, 15.5, 16, 2, NA),
    Kg_per_USD1000_GDP_2014 = c(490.8, 1235, 324.2, 184.7, 1051.5, 999.4, 205.2, 197.4, NA, 1344.4, 475.7, 301, 921.9, 492.7, NA)
)
```

## Subsetting 

### 1.  Load in data set and subset the following, each from `CO2_2015`.

 a. Subset Percent of world emissions using `$`, and assign to a new variable.
 
 b. Subset one column using ['name']
 
 c. Check the structure of the Country column. What is the data structure?



## Subsetting with [ ] positionally (one dimension)

### 2. Use the Country vector you just pulled out:

 a. Display just the first element of the vector

 b. Display just the last element of the vector
 
 c. Display the 2, 5, and 9th element of the vector
 
 d. Display the first 5 elements of the vector
 
 e. Remove the first 4 elements of this vector


## Subsetting with [ ] logically (one dimension)

### 3. Using the Percnt_World_CO2 column:

 a. Display all values of the vector less than 10
 
 b. Display all values of the vector more than 2
 
 c. Display all values of the vector more than 2 and less than 10
 
 d. Display all values of the vector less than 2 or more than 10
	

## Subsetting in two dimensions

### 4. Use the :

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


