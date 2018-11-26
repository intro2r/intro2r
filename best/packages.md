---
title: Packages
layout: default
---

# Packages

R can be extended almost infinitely with packages: add-ons that folks have contributed that do specific things.

## How to find packages

Packages can be found in a variety of ways.

#### 1. The R project website

[CRAN](https://cran.r-project.org/web/packages/) Lists all the packages, 
  as well as different collections that work on different subject areas.
  

#### 2. Articles

Many articles will cite the R packages they used.


#### 3. Google

Search for 'R package' and whatever task you are trying to accomplish.


#### 4. RStudio
  
RStudio has its' own collection of packages: [https://www.rstudio.com/products/rpackages/](https://www.rstudio.com/products/rpackages/)  
  
  
#### 5. Various websites

Various websites maintain different collections of packages.

e.g., [https://awesome-r.com/](https://awesome-r.com/)




## Installing packages

Packages can be installed from within RStudio, under the 'packages' pane.

Alternatively, you can install them with the `install.packages()` function from within the console. Note the quotes.

```r
install.packages('lme4')
```


## Loading packages

For every version of R, you only need to install a package once.

However, in each R session, you will need to load these packages using the `library()` function. Note the lack of quotes.

```r
library(lme4)
```



## Recommended packages

### linear mixed effect models

General overview [here](https://bbolker.github.io/mixedmodels-misc/glmmFAQ.html)

- lme4, nlme


### Plotting tricks and hacks

- [plotrix](https://cran.r-project.org/web/packages/plotrix/index.html). Check the manual for all the cool things it can do!



### multivariate stats

Both these packages have good overviews and examples.

 - [vegan](https://cran.r-project.org/web/packages/vegan/index.html), 
 
 - [labdsv](http://ecology.msu.montana.edu/labdsv/R/)


### spatial

 - [spatstat](http://spatstat.org/)
 
 

## Other graphing packages

### ggplot2

[ggplot2](https://ggplot2.tidyverse.org/) is a powerful graphics language that translates models and data structure into graphics.

It can be complex to learn and use. 


### lattice

[Lattice](https://cran.r-project.org/web/packages/lattice/index.html) improves on the default plotting options of base R, and 
can be useful for multivariate data and multi-panel plots with data conditioned on other data.



