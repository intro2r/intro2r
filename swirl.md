# Introduction to SWIRL 

## What is SWIRL?

Statistics With Interactive R Learning

![](img/swirl.png)

*Every new tech thing needs a nice acronym and logo*



# What SWIRL is

an R package for teaching and learning statistics and R **simultaneously** and **interactively**



# What SWIRL is

**Lessons** are a *dialogue* between swirl and the user

Composed of:
  - text output, 
  - multiple choice and text-based questions, 
  - and (most importantly) questions that require the user to enter actual R code at the prompt. 
  

**Responses** are evaluated for correctness based on instructor-specified answer tests.
 - Appropriate *feedback* is given immediately to the user.


# Why are we using swirl?

Students work directly in R console = real working environment

Allows immediate evaluation of code and immediate feedback

Allows remote logging of scores so I can check progress  


# How to use SWIRL


# 1. Install SWIRL package

You only need to do this once.


```r
# install swirl. 
# Requires ""
install.packages("swirl")
```
 


# 2. Install the lessons

Lessons are on the intro2r GitHub page

(github = social coding site, sharing code)


You only need to do this once for each Unit (unless we update the lessons ... ).


```r
# load the swirl pakcage
library(swirl)

# access github and download the course
# (this function is provided with the swirl package)
install_course_github("intro2r", "swirl_courses", multi = TRUE)
```

This command downloads the first set of lessons to your computer.



# 3. Start swirl

You will need to do this every time you start R or want to continue an old lesson or start a new lesson.


```r
# load the swirl package into your current R session
# (No need for "")
library(swirl)

| Hi! Type swirl() when you are ready to begin.

# start swirl ... 
# (swirl is a function, so you need '()')
swirl()
```


# 4. Choose a name


```r
> library(swirl)

| Welcome to swirl! Please sign in. 
| If you've been here before, use the same name as you did then. 
| If you are new, call yourself something unique.

What shall I call you? 
```

Enter your name.

I will need to be able to identify you, so please use:
 - firstname lastname, or 
 - Yale ID.

This name will also allow you to continue lessons if you stop them in the middle.


# 5. Choose a course


```r
| Please choose a course, or type 0 to exit swirl.

1: Getting Started
2: Take me to the swirl course repository!

Selection: 
```

Enter the number of the course you want to work on.

E.g.: '1'



# 6. Choose a lesson


```r
| Please choose a lesson, or type 0 to return to course menu.

1: Basic Building Blocks
2. ...
...
```

Choose the first lesson: Basic Building Blocks

Type: '1'



# 7. Do the lesson!


```r
| Attempting to load lesson dependencies...

| Package ‘base64enc’ loaded correctly!

  |                                                                            |   0%

| In this lesson, we will explore some basic building blocks of the R programming language.

...
```

Hit 'Enter' to advance when presented with '...'

The screen also shows you how far through the lesson you are (0%).



# 8. Completing the lesson
 
**You will need to be connected to the internet to submit your lesson**

When you are done, the last question will ask if you want to submit your answers to me
to verify that your completed the lesson.

You should enter the number of your response (usually '1').

This will bring up a new web page, a Google form.

Scroll down, and click 'submit'.

This will send an encrypted response to the Google form so that we can verify you completed the lesson.



# Some useful commands for swirl

## bye()

Exit swirl

## play()

Leave swirl temporarily and gain access to the console again

## nxt()

Return to swirl after playing

## main()

Return to the main menu

## info()

Display a list of these special commands



