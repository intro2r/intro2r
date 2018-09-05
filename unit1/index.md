

# Unit 1: Getting StaRted

In this unit, you will become familiar with the R console, RStudio, and basic actions and operations in R.

Follow the links to each lecture, lab, and reading.

Scroll down to download the SWIRL lessons.


## Lesson 1. What is R?

Lecture: [Overview of R](./r-overview.html), demonstration of R.

Learning Goals:
 - Understand what R can and cannot do,
 - Install R and RStudio,
 - Know how to navigate within RStudio.

Lab: [Unit 1: Lab 1](../unit1/install-R-and-RStudio.html)

Reading: [NYT article](http://www.nytimes.com/2009/01/07/technology/business-computing/07program.html?_r=1&pagewanted=all)

Functions: None.


## Lesson 2. How to use R as a calculator

Lectures: 

 - [Working with R and RStudio](./first-look.html)
 
 - [How to use SWIRL](../swirl.html)

Learning Goals:
 - Perform operations on numbers and integers,
 - Assign numeric and character data to variables,
 - Manipulate variables with operators,
 - Understand and use paths and working directories.

SWIRL: Basic building blocks

Lab: [Unit 1: Lab 2](../unit1/labs.html#lab-2)

Reading: 

 - [How a computer works](./how-computers-work.md)

 - [Working directories](https://support.rstudio.com/hc/en-us/articles/200711843-Working-Directories-and-Workspaces)

Functions: `<-`, `getwd()`, `setwd()`.


## Lesson 3. How to work with vectors

Lecture: Types of data in R

Learning Goals:

 - Generate vectors using `c()`, `:`, `seq()`, `rep()`,
 - Assign these vectors to variables and manipulate them,
 - Identify types of vectors (numeric, integer, factor, character, ...)
 - Plot individual vectors with `plot()`.

SWIRL: Vectors and Sequences

Lab: [Unit 1: Lab 3](../unit1/labs.html#lab-3)

Reading:

Functions: `c()`, `:`, `seq()`, `rep()`, `plot()`, `is.vector()`, etc


## Lesson 4. How to summarise vectors

Lecture: Data structures; Functions

Best Practice: [Code style guide](../best/code-style.html), [lab](../unit1/labs.html#best-practice-lab)

Learning Goals:

 - Navigate to and from working directory with `getwd()` and `setwd()`,
 - Subset vectors with logical statements (`>`, `<`, `!=`, `==`),
 - Use functions to perform calculations, with `sum()`, `mean()`, `sd()`, etc.
 - Summarise the distribution of a vector with `boxplot()` and `hist()`.

SWIRL: 

 - Subsetting Vectors
 
 - Visualizing Data (Distributions and summarising data)

Lab: [Unit 1: Recap](../unit1/labs.html#unit-1-recap)     

Reading:

Functions: `getwd()`, `setwd()`, `sum()`, `mean()`, `sd()`, `summary()`, `length()`, `boxplot()`, `hist()`

 - - -
 
# SWIRL

The lessons we will use are available online and you need to download them to your laptop.

1. Open RStudio

2. In the console panel, next to the arrow (>), copy and paste the following: 

```
library(swirl)
install_course_github("intro2r", "swirl_courses", multi = TRUE)
```

This will download the most up-to-date lessons.

To start the lesson, type

```
swirl()
```



- - -

Updated 2018-08-29

