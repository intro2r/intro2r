---
title: Exercises
layout: default
---

## Modifying Plots



### New Haven Road Race data

```r
dat <- read.table('http://www.intro2r.info/data/NewHavenRoadRace_clean.txt', header = TRUE, sep = '\t')
```


1. Make a bar plot of the number of runners in each age class. Make axis labels in a larger font, and each bar a different colour.

2. Plot each runner's pace (y) as a function of their sex (x). Ensure proper axis labels, axis numbers in a larger font, and males and females in different colours.

3. Plot pace as a function of age class. Include axis labels, and make each box a different colour.

4. Plot each runner's time as a function of their pace. Ensure correct axis labels and increasing symbol size with increasing pace.


### Michigan tree species

```r
dat <- read.table('http://www.intro2r.info/data/treespecies_cleandata.txt', header = TRUE, sep = '\t')
```

1. Make a map of the locations of all the trees.

2. Map the alive and dead trees different symbols and colours.

3. Map the symbol size as a function of DBH.

4. Make a map of only black oak trees.

5. Plot tree DBH as a function of species. Make each box a different colour.

6. Plot mean DBH as a function of status for each species.


