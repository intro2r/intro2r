
# Matrices

Matrices are an extension of numeric or character vectors. 

They are not a separate type of object but simply an atomic vector with dimensions; the number of rows and columns.

Because they are an atomic vector, all the elements are the same type (integer, numeric, etc).

Matrices are used frequently in mathematical models and statistics.


## How to make a matrix

We can create an empty matrix and fill it later,
```{r}
matrix(ncol = 2, nrow = 2)
```

```
     [,1] [,2]
[1,]   NA   NA
[2,]   NA   NA
```

or create one from vector
```{r}
matrix(1:4, ncol = 2, nrow = 2)
```

By default, matrices are filled by columns. We can fill be rows instead.
```{r}
matrix(1:4, ncol = 2, nrow = 2, byrow = TRUE)
```

We can label the columns ...
```{r}
m <- matrix(1:4, ncol = 2, nrow = 2)
colnames(m) <- c("A", "B", "C", "D")
m
```

... and the rows
```{r}
rownames(m) <- c("a", "b", "c", "d")
m
```

We can add extra columns
```{r}
cbind(m, 5:6)
```

or rows
```{r}
rbind(m, 7:8)
```




