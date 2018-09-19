---
layout: default
title: Importing_Data
---


In this lesson, you will learn about importing data. 

We will practice using the various functions to read in data. 

There are various datasets installed with this lesson. 

However, we have to find them! 

We can do this by changing our working directory to where R has stored the data in your hard drive. 

First, let's check our current working directory, with getwd().

```{r}
getwd()
``` 

You can find the path to the lesson datasets using an object that we created, called 'lessonpath'. To see the path, type 'lessonpath'. This should display where on your computer the files for this lesson are stored.

```{r}
lessonpath
``` 

Now, you will need to change your working directory to this location. Type: setwd(lessonpath).

```{r}
setwd(lessonpath)
``` 

Now, our working directory is located in the 'data' directory for this swirl lesson. All the data files for this lesson are located here. 

OK, let's read in some simple data! We have made the custom function `viewData()` that will open up the data files in the RSudio text editor, so that you can look at the raw data as we try and read it in. Look at the first data set, test1.txt. Remember that you need to put the file name in quotes.

```{r}
viewData('test1.txt')
``` 

Now that you have looked at this data, we will use the `read.table()` function first. Use `read.table()` to read in the first example dataset, called test1.txt. Do not worry about assigning this data to any variable for now, just read it in (remember the quotes!)."

```{r}
read.table('test1.txt')
``` 

This object does not look exactly like the dataset we just opened. The column names have been replaced with 'V1, 'V2', etc. What is going on? 

To examine the data in more detail we will need to look at its' stucture. Embed the previous call to `read.table()` within a call to `str()`.

```{r}
str(read.table('test1.txt'))
``` 

So we have a dataset that looks like it should be four columns and three rows. However, we have four columns of factors, not numbers. :( *sad face*. 

R does not know that the first row is supposed to be the column names and has made up column names for us ('V1', 'V2', etc.) and also treated each of the columns as text (or specifically here, a factor) because it thinks that the 'a', 'b', etc are part of the data. 

What to do? 

Well, we can tell R that the first row of this data is the column names, or 'header'. To do this, we need to add the 'header = TRUE' argument to the `read.table()` call. Try that within the previous expression so that we can confirm the structure.

```{r}
str(read.table('test1.txt', header = TRUE))
``` 

That looks better! We now have a dataset of four numeric columns, with each column named a different letter. Now, let's get into specifics of column separators ... 

We have used read.table(), which uses generic white space as its column delimitor. How about we try setting the delimitor (or 'seperator') to a comma instead. What happens to the structure?

```{r}
str(read.table('test1.txt', header = TRUE, sep = ','))
``` 

We still get a dataframe, but of only one column! The column separator here is obviously not a comma. However, this example does illustrate a couple of other aspects of `read.table()`. 

First, we told R that the column separator *is* a comma. Therefore, because there are not any commas in the data, R thinks that the data is just one big column. As such, R has put periods in between each letter of the column header. 

Moreover, R has treated each row as an entire cell in the data and converted them to factors. You can see that the *real* separator is a tab (indicated by the backslash t, '\t'). 

Now that we know what the actual separator is, let's put that in place of the comma.

```{r}
str(read.table('test1.txt', header = TRUE, sep = '\t'))
``` 

We get our nice dataframe back again. Yay! 

Now that we can read in a tab-delimited text file, let's try our hand at a .csv file. First, open the 'example2.csv' file with the `viewData()` function.

```{r}
viewData('example2.csv')
``` 

Now try and read in the example2.csv file using the `read.csv()` function. Remember that 'csv' stands for 'comma separated variables'. You can drop both the header = TRUE and sep =  arguments, because the default for `read.csv()` is header = TRUE, sep = ','. Also no need to put it all within `str()` this time.

```{r}
read.csv('example2.csv')
``` 

Ok, so now you can read it in, let's check the structure again. Remember, in this case, there is no need to assign the data to any object name. Just nest the call to read.csv() within str().

```{r}
str(read.csv('example2.csv'))
``` 

One of the features of R that is hopefully appearing in your mind, is that there are many ways to skin a cat in R. We can use the `read.csv()` function to read in a csv file with the first row as headers. The `read.csv()` sets these two arguments a defaults. However, we could also use the `read.table()` function to read in this .csv file, by changing the defaults. See if you can read example2.csv with `read.table()`. Embed it in the `str()` as before.

```{r}
str(read.table('example2.csv', header = TRUE, sep = ','))
``` 

Now, you should be happy using read.table() and read.csv() to import data into R. 

The functions `read.csv2()`, `read.delim()`, and `read.delim2()` work similarly to `read.csv()` in that they set different defaults. Check the help files and the class lecture for more information if you want, otherwise, you can just use `read.table()` and `read.csv()` and set any arguments you need to for each specific dataset. 

Now we will try and read in some data that has some errors. RStudio will open up a sequence of data files. You should be able to modify the data in the text editor, save it using 'Ctrl-S' or the 'save' button in RStudio, and try and read the data in to R. 

We will start with example3.txt. Open this file with `viewData()`.

```{r}
viewData('example3.txt')
``` 

**IMPORTANT!:** Before you do anything else, read this text! 

The following questions depend on two things: the correct code AND the correct data. 

To proceed in the lesson, you will have to edit the data in the text editor such that it can be read into R. 

There may (will!) be cases where you try and read the data in and an error causes swirl to crash. If that happens, just restart swirl, with `swirl()`, and continue with the lesson. 

Got that? Ok, let's carry on ... 

First, try and read example3.txt in to R with `read.table()`. It will not work. You will have to edit and save the data file so that it will read in.

```{r}
read.table('example3.txt', header = TRUE)
``` 

You received at least one (maybe several!) error messages trying to read in the example3.txt file. The useful one stated something like 'line 1 did not have 5 elements' and 'incomplete final line ...'. These errors were caused by the apostrophe in the first row of the data. Deleting that apostrophe allowed the data to be read in correctly.
It's terrifying that such a small thing can have such *cat-apostrophic* effects ... 

Let's try another one. Open example4.txt.

```{r}
viewData('example4.txt')
``` 

Great, now edit that file and try and read it in with `read.table()` as before.

```{r}
read.table('example4.txt', header = TRUE)
``` 

That one had an errant comment ... 

Let's try another one. Open example5.txt.

```{r}
viewData('example5.txt')
``` 

Great, now edit that file and try and read it in with `read.table()` as before. In this case, we want to force the separator to be a tab, so set sep = '\t'.

```{r}
read.table('example5.txt', header = TRUE, sep = '\t')
``` 

Let's try another one. Open example6.txt.

```{r}
viewData('example6.txt')
``` 

Great, now edit that file and try and read it in with `read.table()` as before. This is a tough one, so it may help to copy the file into a spreadsheet, or do some searching with the search function for specific characters within the file. Remember to set the header and sep arguments

```{r}
read.table('example6.txt', header = TRUE, sep = '\t')
``` 

Great work! You should now be able to read data in to R. You should also have some idea of some of the pitfalls and errors that can be very frustrating when you are trying to do so! 

Please submit the log of this lesson to Google Forms so that Simon may evaluate your progress.

1. Yes, yes, yes!

Yes, yes, yes! 
