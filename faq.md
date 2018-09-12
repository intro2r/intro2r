---
layout: default
title: FAQ

---

# Frequently Asked Questions (FAQ)

This page will list common questions and problems you might encounter during the course.

A. Installing

B. Submitting labs

C. The R console

D. Error messages

E. Getting more help


# A.Installing

Help getting your computer set up to do the course.

## 1. How do I install R and RStudio?

Link the page [here](http://www.intro2r.info/unit1/install-R-and-RStudio.html)


## 2. How do I install SWIRL?

To download the SWIRL package, copy and paste this into the R console.

You should only need to do this once.

```{r}
install.packages("swirl")
```

## 2. How do I download the course SWIRL lessons?

You will need to run this every time we update the lessons.

First, load the swirl package and uninstall previous versions of this course.  

```{r}
library(swirl)
uninstall_all_courses()
```

Then delete your progress in any current lesson.

You will need to enter the user name you were using for the SWIRL lesons, in quotes.

```{r}
delete_progress("USER")
```

Now, you can install the whole course again.

```{r}
install_course_github('intro2r', 'swirl_courses', multi = TRUE)
```

And start SWIRL ...

```{r}
swirl()
```

## 3. Full script to uninstall, delete progress, and reinstall SWIRL lessons

```{r
# Copy and paste this first:
# get access to  swirl library
library(swirl)
# uninstall all courses; the '1' tells R that yes, you do want to uninstall.
uninstall_all_courses(1)

# you will need to enter your user name here ...
# delete your progress (replace 'USER' with the name you use in SWIRL)
delete_progress("USER")
# Re-install the course, with updated lessons
install_course_github('intro2r', 'swirl_courses', multi = TRUE)
# start SWIRL
swirl()
```


# B. Submitting labs

## 1. How do I write up the labs?

You will need to write R code to answer each of the questions.

This should be a .R or .txt file saved on your computer, written in the text editor panel of RStudio (or any other text editor).

Please format your answers as follows:

 - Copy and paste each question, commented out with `#`. This ensures that we know which answer corresponds to which question.

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

Please do not copy the code from the console, as the lines will contain '>', which will cause your code to fail on our computer when we test it.


## 2. How to submit your lab answers on Canvas

i. Log into Canvas.

ii. Go to the Assignments page.

iii. Under ‘Labs’, you should find the correct assignment.

iv. Copy and paste your R code into the text box, or upload your .R or .txt file.

v. Click ‘Submit Assignment’.

You are permitted to submit your answers as many times as you like within each Unit.

Answers will be graded two or three times a week and re-opened if you submit early.

Each lab will close at its respective deadline (see Canvas).

Final grades for each lab will be computed and entered into the Canvas gradebook at the end of each Unit.
 

# C. The R console

## 1. What are comments (#)?

The hash or pound symbol (`#`) is used in R to indicate a 'comment', or a line in the file that is not evaluated by R when it is pasted in to the Console.

You can use comments to describe what you code is doing so that in 6 months time you can still understand what you meant!

You can also use comments to “comment-out” a line of code that you want to keep in the file but not run.


## 2. What are the numbers in the output in square brackets [1] on the left of the console?

You will come across many instances where the data you display in the R console are too big for the window and over-run a single line.

It will always display `[1]` for the first element.

Then, R tells you how far along that sequence of data you are when the next line starts.


## 3. What are the 'arrows' (>)?

When the R console displays an arrow (>), that tells you that R is ready. You can enter code.


## 4. What does the plus symbol mean in the R console?

The plus symbol (+) on the left of the console means that R is waiting.

The plus sign (+) tells you that R is waiting (very patiently) for something else from you …

Normally you will need to close out a function.

In any case, you can press ESC to terminate that code, which will not run, and return to the arrow prompt.



# D. Error messages

## 1. “Error: could not find function ‘…’”

Here, R cannot find the function command that you have written.

Either it is not loaded, or most likely, you have mispelled it.

## 2. “Error: object ‘…’ not found”

Here, the object name that you have typed in is not recognised.

Please check and try again!



# E. Getting more help

## 1. How do I find out more about a function?

Typing a question mark, followed by the function name, will pop up the help file on that function.

E.g.,

```{r}
?mean
```

## 2. How do I find out how to do *x* in R?

Many times, you will want to do something in R that is not covered in this course.

The best way to find out how to do it, is to type `R thing you want to know` into a search engine.

This will likely return a series of blogs, forums, and R sites that address these issues.

Specific sites also cater to such questions.

[Stackexchange and CrossValidated](https://stats.stackexchange.com/) are good places to search for help, or ask a question that has not been asked before.




