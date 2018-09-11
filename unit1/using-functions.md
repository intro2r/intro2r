---
layout: default
title: using functions
---

# Using Functions

In this lecture we will discuss the difference between objects and functions, and how to use functions.

We will cover writing your own functions later.


## Objects 

An object is a *thing*.

An object could be a single number, a sequence of numbers, a dataset, the output from a statistical test, or any thing that you can access or call in R ...


## Functions

Functions are tools, procedures, or commands.

They do stuff to objects.

Functions are tools that automate more complicated sets of commands, such as operations, assignments, etc. 
Many functions are predefined, or can be made available by importing R packages.

For example, it is much quicker and simpler to type: `mean(my_data)` than `sum(my_data) / length(my_data)`.

Often you will take an object (e.g., a sequence of numbers), do something to it with a function (e.g., `the mean()` function), that function will output a new object (the mean of that sequence).

We have already used several functions, such as `mean()`, `sd()`, `sqrt()`, and `plot()`. 
Some of these functions are very simple and some are very complex.


## Arguments

Within the parentheses of each function, you can specify various *arguments*.

Arguments are inputs and options available for that function:

 - *input* arguments tell the function what *inputs* (e.g., data such as a vector or dataframe) to use. 

 - *option* arguments tell that function if there are any *options* available and what the *defaults* are (e.g., the function `mean()` has an argument checking what to do with NAs, the default of which is to keep them: `mean(1:10, na.rm = FALSE)`).

 - Arguments can also be other objects, or parameters, or even left open to allow arguments from other functions to be used (this is particularly common in plotting functions).

The help files for each function list and describe the arguments. `?sqrt`.


### A single argument: e.g., `sqrt()`

A typical example would be the function `sqrt()`, which has only one argument: `x`.

`x` can be a numeric vector, and the function returns as an output the square root. 

Executing a function (‘running it’) is termed *calling* the function. 

An example of a function call is:
```
> sqrt(2)
[1] 1.414214
```
or
```
> sqrt(x = 2)
[1] 1.414214
```



### Multiple arguments: e.g., `mean()`

Within a function, arguments are seperated by commas.

Arguments use `=` to assign values (cf. `<-` to assign values to objects outside of function calls).

The function `mean()` has four arguments, two of which you are likely to use:

```
mean(x, trim = 0, na.rm = FALSE, ...)
```

Here:

 - `x` is the data, usually a numeric vector.

 - `trim = 0` specifies how many values to remove from either end of 'x' before the mean is computed. The default is set to 0. 

 - `na.rm = FALSE` specifies whether to remove any missing values from 'x' before calculation, or not.

 - `...` this is the argument telling you that you can pass other arguments to mean().


You can either write out the name of each argument, or not. If not, R then assumes that arguments are entered in the order in which they appear in the help file (i.e., how the function itself is coded).

Usually, for mean(), you will only want to pass it the data. Thus, you only need to specify 'x'. In most cases, you do not need to type out `x = `, but can just give it the data.
```
> mean(x = 1:10)
[1] 5.5
> 
> mean(1:10)
[1] 5.5
```

If you want to change the defaults, then it is best practice to write out the argument in full. 
```
> mean(c(1:10, NA))
[1] NA
> mean(c(1:10, NA), na.rm = TRUE )
[1] 5.5
```

 - - -
 
 Updated: 2018-09-10
 
