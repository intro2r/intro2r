---
layout: default
title: Split-Apply-Combine
---


# The Split-Apply-Combine Strategy for Data Analysis

 
![](img/treeplot.png)
**Figure 1.** A map of tree locations in a 1-ha plot. Each circle represents a stem, the size corresponds to the DBH, x- and y-axes are the position.



```r
head(dat_tree)

#      x     y  species  dbh status
# 1 0.078 0.091 blackoak 0.85      1
# 2 0.076 0.266 blackoak 0.90      1
# 3 0.051 0.225 blackoak 1.11      1
# 4 0.015 0.366 blackoak 0.18      0
# 5 0.030 0.426 blackoak 0.32      1
# 6 0.102 0.474 blackoak 0.11      1
```

```r
str(dat_tree)
# 'data.frame':	2251 obs. of  5 variables:
#  $ x      : num  0.078 0.076 0.051 0.015 0.03 0.102 ...
#  $ y      : num  0.091 0.266 0.225 0.366 0.426 0.474 ...
#  $ species : Factor w/ 6 levels "blackoak","hickory",..: 1 ...
#  $ dbh    : num  0.85 0.9 1.11 0.18 0.32 ...
#  $ status  : int  1 1 1 0 1 1 1 0 1 1 ...
```

### Problem: How to calculate mean tree DBH per species?

We can split the dataset up into chunks of rows based on species, and calculate mean DBH for each group.

This is an example of the split-apply-combine approach to data analysis.


## Split-apply-combine is a common data analysis pattern

**Split:** Break a big problem into manageable pieces

**Apply:** operate on each piece independently

**Combine:** stick pieces back together


### Examples of split-apply-combine

**Data preparation**

  - group-wise ranking
  - standardization
  - normalization
  - creating new variables on a per-group basis
  

**Summaries for display or analysis**

  - checking sample sizes of groups
  - calculating marginal means
  - conditioning table of counts by groups
  
**Modelling**

 - fitting separate models for groups (= panel)


With your current knowledge, we could do the following:

## Solution 1: Subset data for each species at a time

```r
# subset out blackoak
bo <-  dat_tree[dat_tree$species == "blackoak", ]

head(bo)
# x     y  species  dbh status
# 1   0.078 0.091 blackoak 0.85      1
# 2   0.076 0.266 blackoak 0.90      1
# 3   0.051 0.225 blackoak 1.11      1
# 4   0.015 0.366 blackoak 0.18      0
# 5   0.030 0.426 blackoak 0.32      1
# 6   0.102 0.474 blackoak 0.11      1

mean(bo$dbh)
# [1] 1.258519
```

*But*, given that we are repeating many of the same steps, this is both tedious and time-consuming, and also increases the chance of errors creeping in to our code.

 
## Solution 2: The *apply group of functions

R has several handy-dandy functions that do this process of splitting the dataset into chunks, applying a calculation, and combining the answers together again.

*Equivalents in other software*: Excel pivot tables, APL's array operators, SQL 'group by operator'.


## The *apply group of functions

### `apply()`

*Works on*: matrix, array.

When you want to apply a function to the rows or columns of a matrix (and higher-dimensional analogues).

```r
# Two dimensional matrix
M <- matrix(seq(1,16), 4, 4)

M
     [,1] [,2] [,3] [,4]
[1,]    1    5    9   13
[2,]    2    6   10   14
[3,]    3    7   11   15
[4,]    4    8   12   16

# apply min to rows
apply(M, 1, min)
[1] 1 2 3 4

# apply max to columns
apply(M, 2, max)
[1]  4  8 12 16
```

Not generally advisable for data frames as it will coerce to a matrix first.

If you want row/column means or sums for a 2D matrix, look at highly optimized, lightning-quick ``` colMeans() ```, ``` rowMeans() ```, ``` colSums() ```, ``` rowSums() ```



### `lapply()`

*Works on*: list

When you want to apply a function to each element of a list in turn and get a list back. 

```r
x <- list(a = 1, b = 1:3, c = 10:100) 

x
$a
[1] 1

$b
[1] 1 2 3

$c
 [1]  10  11  12  13  14  15  ... 100
 
```



```r 
lapply(x, FUN = length) 
$a 
[1] 1
$b 
[1] 3
$c 
[1] 91

lapply(x, FUN = sum) 
$a 
[1] 1
$b 
[1] 6
$c 
[1] 5005
```



### `sapply()`

*Works on*: list

When you want to apply a function to each element of a list in turn, but you want a vector back, rather than a list.

```r
x <- list(a = 1, b = 1:3, c = 10:100)

# Compare with above; a named vector, not a list 
sapply(x, FUN = length)  
a  b  c   
1  3 91

sapply(x, FUN = sum)   
a    b    c    
1    6 5005 
```



```r
# lapply:
lapply(x, FUN = sum) 
$a 
[1] 1
$b 
[1] 6
$c 
[1] 5005

# sapply:

sapply(x, FUN = sum)   
a    b    c    
1    6 5005 
```




### `tapply()`

*Works on*: vectors and factors (usually in a dataframe)

For when you want to apply a function to subsets of a vector and the subsets are defined by some other vector, usually a factor


```r
z <- data.frame(x = 1:20,
                 y = factor(rep(letters[1:5], each = 4))
                 )

z
    x y
1   1 a
2   2 a
3   3 a
4   4 a
5   5 b
6   6 b
7   7 b
8   8 b
9   9 c
10 10 c
11 11 c
12 12 c
13 13 d
14 14 d
15 15 d
16 16 d
17 17 e
18 18 e
19 19 e
20 20 e
```



```r
# Add up the values of x 
#   within each subgroup defined by y:

tapply(z$x, z$y, sum)  
 a  b  c  d  e  
10 26 42 58 74 
```





 - - -

## Other resources

https://nsaunders.wordpress.com/2010/08/20/a-brief-introduction-to-apply-in-r/

https://stackoverflow.com/questions/3505701/grouping-functions-tapply-by-aggregate-and-the-apply-family

https://www.slideshare.net/hadley/plyr-one-data-analytic-strategy





