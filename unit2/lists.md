---
layout: default
title: Lists
---

# Lists

Along with [data frames](../unit2/matices-and-dataframes.html), a list is one of the most useful and most-encountered objects in R.

They are the only object in R that can store different modes of data objects of *different sizes*.

As such, they are the usual output from statistical tests and models, becuase these outputs include single values (e.g., a text statistic or p-value), as well as vectors of confidence limits, and matrices or data frames of input data.

A list is technically a 1-dimensional object.

Lists are akin to a a closet (*wardrobe*), where you can hang multiple different hangers off a single main bar (hence the 1d).

![](http://intro2r.github.io/unit1/img/hangers.jpg)

Lists are constructed with `list()` (cf. `c()` for atomic vectors).

Notice that, similar to data frames, we can name each component ('hanger') of the list. (For a data frame, we can use a similar construction to name the columns, if we generate the data frame within R).
```r
l <- list(a = 1:4, 
          b = c('i', 'i', 'ii', 'ii'), 
          c = c(1.1, 2.2, 3.3, 4.4)
          )
l
```
```
$a
[1] 1 2 3 4

$b
[1] "i"  "i"  "ii" "ii"

$c
[1] 1.1 2.2 3.3 4.4
```

Here, we have a list of three components, a, b, and c. 

Using `str()` to look at the structure, we can see that we have a list of 3 components: an integer, a character, and a numeric vector.
As usual, we get information on each component, its mode, length, and the first few elements.
```r
str(l)
```
```
List of 3
 $ a: int [1:4] 1 2 3 4
 $ b: chr [1:4] "i" "i" "ii" "ii"
 $ c: num [1:4] 1.1 2.2 3.3 4.4

```


