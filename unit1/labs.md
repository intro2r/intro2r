Unit 1. Getting Started: Labs
=============================

These labs test and build on the material presented in the SWIRL lessons.

Scroll down or click [here](../unit1/labs.html#how-to-submit-your-labs) to check how to submit them.

# Lab 1

1. Read the *New York Times* [article](http://www.nytimes.com/2009/01/07/technology/business-computing/07program.html?_r=1&pagewanted=all) on R.

2. [Install R and RStudio](http://www.intro2r.info/unit1/install-R-and-RStudio.html).

 - - -


# Lab 2

## Simple Operations

### 1. Perform the following basic operations in the R console:

  a. Add 3 and 5.

  b. Add 1, 3, 5, 7 and 11.

  c. Subtract 675 from 3.

  d. Divide 1 by 1.4.

  e. Multiply 2 by 2 by 2.

  f. Find 2 to the 3rd power.

  g. Check if 4 is less than 5.

  h. Check if 5 is greater than 7.


## Manipulate Variables

### 2. Assign variables and perform operations

  a. Assign 2 to the variable `x`.

  b. Add 4 and `x`.

  c. Assign 10 to the variable `myVar`.

  d. Divide `myVar` by `x`.

  e. Check if `myVar` is greater than `x`.


## External data and variable manipulation

### 3. Use the Harry Potter movie data (Table 1) to answer each question.

**Table 1.** Box office history for all Harry Potter movies<sup>[1](http://www.the-numbers.com/movies/franchise/Harry-Potter#tab=summary)</sup>. 

| Release Date | Movie                                         | Production Budget | Domestic Opening Weekend | Domestic Box Office | Worldwide Box Office |
|--------------|-----------------------------------------------|------------------|------------------------|--------------------|---------------------|
| Nov 16, 2001 | Harry Potter and the Sorcerer’s Stone         | $125,000,000     | $90,294,621            | $317,575,550       | $974,755,371        |
| Nov 15, 2002 | Harry Potter and the Chamber of Secrets       | $100,000,000     | $88,357,488            | $261,987,880       | $878,979,634        |
| Jun 4, 2004  | Harry Potter and the Prisoner of Azkaban      | $130,000,000     | $93,687,367            | $249,538,952       | $796,688,549        |
| Nov 18, 2005 | Harry Potter and the Goblet of Fire           | $150,000,000     | $102,685,961           | $290,013,036       | $896,911,078        |
| Jul 11, 2007 | Harry Potter and the Order of the Phoenix     | $150,000,000     | $77,108,414            | $292,004,738       | $942,943,935        |
| Jul 15, 2009 | Harry Potter and the Half-Blood Prince        | $250,000,000     | $77,835,727            | $301,959,197       | $935,083,686        |
| Nov 19, 2010 | Harry Potter and the Deathly Hallows: Part I  | $125,000,000     | $125,017,372           | $295,983,305       | $960,283,305        |
| Jul 15, 2011 | Harry Potter and the Deathly Hallows: Part II | $125,000,000     | $169,189,427           | $381,011,219       | $1,341,511,219      |
| Nov 18, 2016 | Fantastic Beasts and Where to Find Them       | $180,000,000     | $74,403,387            | $234,037,575       | $803,798,342        |



  a. Create three separate variables for each of the first three movies, giving them the value of their worldwide box office take. 

  b. Check if the Sorcerer’s Stone made more money than the Prisoner of Azkaban. 

  c. How much money did all three movies make together?


 - - -


# Lab 3

## Generate Vectors

### 1. Create the following vectors and save them as variables of your choosing:

  a. A vector from 1 to 1000, using `:`.

  b. The same vector, using `seq()`.

  c. A vector from 0 to 200 in increments of 5, using `seq()`.

  d. A vector of 10 1s, using `rep()`.

  e. Using `c()`, create a vector of the sizes of your shoe size and your 4 nearest neighbors.

  f. Using `c()`, create a combined vector of your variables from c, d, and e, and the number 10.5.


## Manipulate vectors

**Table 2**. Word counts and book size data from The Harry Potter book series.

| Title	                                        | WordCount<sup>1</sup>  | ChapterCount<sup>2</sup>	| PageCount<sup>3</sup> | 
| ------                                        |  ------------|   -------------|   ----------| 
| Harry Potter and the Sorcerer's Stone	        |       76,944 |            17  |         223 | 
| Harry Potter and the Chamber of Secrets       |       85,141 |            18  |         251 | 
| Harry Potter and the Prisoner of Azkaban      |      107,253 |            22  |         317 | 
| Harry Potter and the Goblet of Fire           |      190,637 |            37  |         636 | 
| Harry Potter and the Order of the Phoenix     |      257,045 |            38  |         766 | 
| Harry Potter and the Half-Blood Prince        |      168,923 |            30  |         607 | 
| Harry Potter and the Deathly Hallows          |      198,227 |            37  |         607 | 

*Sources:* [1](https://wordcounter.net/blog/2015/11/23/10922_how-many-words-harry-potter.html), [2](http://harrypotter.wikia.com/wiki/List_of_chapters_in_the_Harry_Potter_novels), [3](https://dustyloft.wordpress.com/2007/07/12/number-of-pages-harry-potter/)

 

### 2. Using data about the Harry Potter series of books (Table 2), create the following vectors and manipulate them:

  a. Create a vector of the word count from each book. 

  b. Create a vector of the number of chapters in each book.

  c. Divide the word count of each book by the number of chapters to find the average number of words per chapter.

  d. Create a histogram of the number of words per book.


## Further vector practice

### 3. Create the following vectors from the class survey data:

  a. Create a vector of the favorite animals of 10 of your classmates

  b. Check what kind of vector this is?

  c. Create a vector of the number of harry potter books 10 of your classmates have read. 

  d. Plot this vector.



 - - -


# Unit 1 Recap

### 1. Create the following vectors:

  a. Generate a vector of 10 shoe sizes, three people with size 10, two of size 11, and five of size 9, using `c()`.

  b. Create a vector of the leap years from 1900 to 2018, using `seq()`.

  c. Count to 10 in 2s, 5 times.

  d. Make a vector of your favorite color repeated 10 times.

  e. Five of your classmates like pineapple on their pizza, and twenty do not. Use `rep()` to create a vector.


### 2. Examine the qualities of each vector with the given quantities

  a. What is the structure of your heights vector?

  b. Summarize the shoe size data. What is the maximum shoe size in the class?

  c. How is the structure of class height and favorite color different? 


### 3. Perform the following on each vector

  a. What is the average class height?

  b. Create a boxplot of class height.

  c. What is the tallest height in the class?

  d. What is the average number of harry potter books read?

  e. Create a plot of country of origin.

  f. Create a plot of yes vs nos to pineapple on pizza.


### 4. Is there anything that has been exceptionally confusing so far?


 - - -

# Best Practice Lab

### Correct these R code snippets following the best practice code style.

1. ``` average<-mean(feet/12+inches,na.rm=TRUE) ```

2. ``` x<-1 : 10 ```

3. ``` x [1,] ```

4. ``` mean(x <- 1:10, FALSE) ```

5. ``` doSomethingVeryComplicated(data = datafil1,position="here",baseline = na,title="A very long title")```

6. ``` x=5 ```

7. ``` simonSays <- 'It's time's to gets going, y'all!' ```

 

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


1. Log into Canvas.

2. Go to the Assignments page.

3. Under 'Labs', you should find the correct assignment.

4. Copy and paste your R code into the text box.

5. Click 'Submit Assignment'.


You are permitted to submit your answers as many times as you like within each Unit. 

Answers will be graded two or three times a week and re-opened if you submit early.

Each lab will close at its respective deadline (see Canvas).

Final grades for each lab will be computed and entered into the Canvas gradebook at the end of each Unit.


 - - -

Updated: 2018-09-29


