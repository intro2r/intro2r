---
layout: default
title: Subsetting and Indexing
---

# Subsetting and Indexing

Subsetting in R is fast and incredibly powerful.

There are three subsetting operators: `[`, `[[`, `$`.

There are also important differences in how we subset different objects (vectors, lists, factors, matrices, and data frames).


### Subsetting and `str()`

Subsetting is a natural complement to `str()`. 

As you know, `str()` shows you the structure of any object, and subsetting allows you to 
pull out the pieces that you’re interested in. 
This is particularly useful for plotting and presenting the results of statistical tests.


## Subsetting atomic vectors

We covered subsetting atomic vectors in Unit 1: [Subsetting Vectors](http://www.intro2r.info/unit1/swirl/subsetting_vectors) SWIRL lesson. 

We can subset atomic vectors in six ways.

Remember that each element has a index (position). We can use these indices to subset.

Take an example vector
```r
x <- c(1, 2, 3, 4, 5)
```

### i. Positive integer

Positive integers return elements at their locations.
```r
x[c(1,3,5)]
```
```
[1] 1 3 5
```

```r
x[c(1,1)]
```
```
[1] 1 1
```


### ii. Negative integers 

Negative integers return all elements *except* those locations specified.
```r
x[c(-1, -2)]
```
```
[1] 3 4 5
```

```r
x[-c(1, 2)]
```
```
[1] 3 4 5
```

**Note:** You cannot mix positive and negative indexes.
```r
x[c(-1, 2)]
```
```
Error in x[c(-1, 2)] : only 0's may be mixed with negative subscripts
```

### iii. Logical vectors
Logical statements test each element in your focal vector and returns a vector of TRUE or FALSE for each element.
Then, R selects the elements of your focal vector where the corresponding logical value is TRUE. 

First, make your logical statement.
```r
# x is iqual to 2
x == 2
```
```
[1] FALSE  TRUE FALSE FALSE FALSE
```

Embed the statement in brackets to select.
```r
# Subsect all elements iqual to 2
x[x == 2]
```
```
[1] 2
```

All logical statements work: ` == `, ` != `, ` < `, ` > `, ` <= `, ` >= `.


### iv. Nothing

An index of nothing returns the entire vector. This is much more useful for matrices, arrays, and data frames.
```r
x[]
```
```
[1] 1 2 3 4 5
```


### v. Zero
An index vector of 0 returns a vector of length 0, useful mostly for generating test data.
```r
x[0]
```
```
integer(0)
```

### vi. Character vectors
If the vector is named, we can index using these names.
```r
names(x) <- c('a', 'b', 'c', 'd', 'e')
x
```
```
a b c d e 
1 2 3 4 5 
```

```r
x['a']
```
```
a 
1
```

And you can repeat these indices, as with integers.
```r
x[c('a', 'a', 'c')]
```
```
a a c 
1 1 3 
```

## Subsetting matrices and arrays

```r
m <- matrix(1:4, ncol = 2, nrow = 2)
m
```
```
     [,1] [,2]
[1,]    1    3
[2,]    2    4
```

You can subset matrices (2d) and arrays (>2d) higher-dimensional structures very simply with an extension of the method
used to index atomic vectors, by giving the 'coordinate' of each element, using brackets (`[`) as before, separated by commas.
E.g., for a 2d matrix: ` [row, col] `.

```r
m[1, 1]
```
```
[1] 1
```

```r
m[ , c(1,2)]
```
```
     [,1] [,2]
[1,]    1    3
[2,]    2    4
```

Blank subsetting is useful here because it allows you to keep all rows or all columns.
```r
m[1, ]
```
```
[1] 1 3
```

As with atomic vectors, we can use positive integers, negative integers, logical vectors, nothing, zero, and names to index.


## Subsetting data frames

```r
df <- data.frame(sample_id = c('i', 'ii', 'iii', 'iv'), x = c(1,2,3,4), y = c(5, 6, 7, 8))
df
```
```
  sample_id x y
1         i 1 5
2        ii 2 6
3       iii 3 7
4        iv 4 8
```

We can use the 2d indexing for data frames as for matrices, to select specific elements: ` [row, col] `.
```r
df[1, c(1, 2)]
```
```
  sample_id x
1         i 1
```


### Accessing data frame columns

More usually, you will want to pull out specific columns, to plot or put into a model.

We can access columns by their position (remember that blank indexing extracts all rows/columns).

BEST PRACTICE: Is **not** to do this. Your column position may change. 
```r
df[, 1]
```
```
[1] i   ii  iii iv 
Levels: i ii iii iv
```

It is therefore better to refer to columns by **name**, similar to with vectors and matrices.

```
df[, c('x', 'y')]
```
```
  x y
1 1 5
2 2 6
3 3 7
4 4 8
```

*Note:* If we refer to only one column by name in this fashion, we get a vector.
```r
> df[, 'x']
```
```
[1] 1 2 3 4
```

We can also refer to column names using the 'list style' (dropping the comma). (*Note:* subsetting a single column like this maintains the data frame stucture).

```r
df['x']
```
```
  x
1 1
2 2
3 3
4 4
```

### Other operators: `[ ` vs ` [[ ` and ` $ `

As we saw above, we can subset a dataframe and maintain the dataframe (i.e., list) structure.
```r
df['x']
```
```
  x
1 1
2 2
3 3
4 4
```

The use of ` [[ ` and  ` $ ` go 'one level down', pulling the components out and returning a vector from the data frame.
```r
df[['x']]
```
```
[1] 1 2 3 4
```
Notice that the column names are not retained here.
 

` $ ` is essentally short-hand for ` [[ `.
```r
df$x
```
```
[1] 1 2 3 4
```

Both these ways of subsetting are needed for plotting functions and others.



We can also subset dataframes by elements in particular columns, as for matrices.
```r
df[df$x > 2, ]
```
```
  sample_id x y
3       iii 3 7
4        iv 4 8
```

```r
df[df['x'] > 2, ]
```
```
  sample_id x y
3       iii 3 7
4        iv 4 8
```




## Subsetting Lists

Subsetting lists works similarly to vectors and dataframes.

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


We can access each part by number,
```r
l[1]
```
```
$a
[1] 1 2 3 4
```

and by name.
```r
l['a']
```
```
$a
[1] 1 2 3 4
```


Using ` [ ` returns a list structure,

```r
l['a']
```
```
$a
[1] 1 2 3 4
```

whereas ` [[ ` and ` $ ` return the components of that part of the list.
```r
l[['a']]
```
```
[1] 1 2 3 4
```

```r
l$a
```
```
[1] 1 2 3 4
```

We can also index down into elements of the list.
```r
l$a[1:3]
```
```
[1] 1 2 3
```



## Subsetting and Assignment

All subsetting operators can be combined with assignment ( ` <- `) to modify selected values of the focal vector. 

```r
x
```
```
a b c d e 
1 2 3 4 5 
```


We can assign new values to specific indexed elements,
```r
x[2] <- 6
x
```
```
a b c d e 
1 6 3 4 5 
```

Use logical statements to revise several elements, 
```r
x[x > 3] <- 9
x
```
```
a b c d e 
1 9 3 9 9 
```


- - -

More details and advanced details on subsetting:

Hadley Wickham's [Advanced R: Subsetting](http://adv-r.had.co.nz/Subsetting.html)


