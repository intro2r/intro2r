
```
# create example data sets
x <- 1:10
y <- 2:11

z <- c(0,0,0,0,0,1,1,1,1,1)

x1 <-rnorm(100)

x2 <- c(10, 90)
```

```
# histogram
hist(x1)
```

```
# boxplot

boxplot(x)

boxplot(x ~ z)

boxplot(x ~ z, notch = TRUE)
```

```
# scatterplot
plot(x ~ y)

plot(x ~ y, lwd = 2, cex = 2, col = z+1)

plot(x ~ y, lwd = 2, cex = 2, col = z+1, pch = z+3)
```

```
# pie

pie( x2 )
```



```
# barplot

x

matrix(x)

matrix(x,ncol = 2)


par(mfrow = c(1, 2))

barplot(x)

barplot(matrix(x))


barplot(matrix(x, ncol = 2))

barplot(t(matrix(x, ncol = 2)))


barplot(matrix(x, ncol = 2), beside = TRUE)

barplot(t(matrix(x, ncol = 2)), beside = TRUE)
```


```
# error bars

## segments / arrows

barplot( x2, ylim = c(0, 100))

x3 <- barplot( x2, plot = FALSE)

segments(x0 = x3, x1 = x3,
         y0 = x2, y1 = x2 + 5,
         lwd = 2)
```


```
# Stripchart

xy <- c(x, y)
zz <- c(z, z)


stripchart(xy ~ zz)
stripchart(xy ~ zz, method = 'jitter')
```

