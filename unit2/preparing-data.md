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
