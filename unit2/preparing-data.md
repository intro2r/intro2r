---
layout: default
title: Preparing data for import to R
---

# Preparing external data for importing to R

A step-by-step guide to formatting an external dataset to allow importing to R.

Here, we focus on a data frame.


## Overview & Summary

1. **2-D table** To import into R, most data you will use needs to be arranged in a 2-dimensional table (exceptions include GIS spatial data and other specialized data formats).

2. **Extra lines and/or columns** Remove or comment out any headers, footers, or un-needed text.

3. **Special characters** Remove or replace text characters that give R trouble. The most common ones are hashes (#) and apostrophes (').

4. **Rename some/all columns** Make sensible names. R also replaces white space in column names with periods (.).

5. **Columns** Make sure that the data is in columns, separated by your delimiter of choice (usually tab or comma).


## Step-by-Step

### 1. Find your raw data

Here is data from the 2015 [New Haven Road Race](http://www.newhavenroadrace.org/wp-content/uploads/2015/03/NH16-5k-Overall.txt), openly available online.

![](https://intro2r.github.io/unit2/img/1.png)

### 2. Select, and try to copy and paste into a spreadsheet

![](https://intro2r.github.io/unit2/img/2.png)

### 3. Nope!

It all gets copied into one cell.

![](https://intro2r.github.io/unit2/img/3.png)

How can we fix this?

### 4. We need to do some fixes in a plain-text file first

Paste into Notepad or equivalent.

![](https://intro2r.github.io/unit2/img/4.png)


### 5. Delete unneeded lines in the file

These top lines are not needed.

![](https://intro2r.github.io/unit2/img/5.png)


Nor is this table header rule

![](https://intro2r.github.io/unit2/img/6.png)


### 6. Replace text that R does not like: apostrophes and hash

![](https://intro2r.github.io/unit2/img/7.png)


### 7. Now, try and move to the spreadsheet

Select all, copy and paste...

![](https://intro2r.github.io/unit2/img/8.png)


### 8. Choose column delimiters

You can select characters (tab, space, etc) or and a fixed width.

![](https://intro2r.github.io/unit2/img/9.png)


In our case, fixed width is better.

![](https://intro2r.github.io/unit2/img/10.png)


Delete extra column delimiters, place ours at beginning of each column.

![](https://intro2r.github.io/unit2/img/11.png)


Press 'OK', and we should hace a nice looking spreadsheet!

![](https://intro2r.github.io/unit2/img/12.png)


### 9. Final issues within the spreadsheet

White space within columns is easier to remove within the spreadsheet (otherwise, this process will remove the white space between the first and surname in the 'name' column.

So, find and replace within selected columns only.

![](https://intro2r.github.io/unit2/img/13.png)


That's better

![](https://intro2r.github.io/unit2/img/14.png)


Revise column names in two columns

![](https://intro2r.github.io/unit2/img/15.png)


### 10. Copy back to plain text file

Select all

![](https://intro2r.github.io/unit2/img/16.png)


Paste into Notepad (or equivalent text editor)

![](https://intro2r.github.io/unit2/img/17.png)


### Save the new data file

![](https://intro2r.github.io/unit2/img/18.png)


Woo hoo!



