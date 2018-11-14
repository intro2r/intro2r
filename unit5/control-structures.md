Control Structures
========================================================

Control Structures
==================

 - Allow you to encode decisions about running code:

  + run code if a certain condition is met: `if`, `if-else`

  + run code multiple times: loops. `for()`, `while()`, `repeat  {}`. Use `break`, `next` to stop or skip.
  



if
====

> if this condition is true, then carry out this task

Use: 
```r
if(cond) expr
```

 - cond: a logical vector of length one.

 - expr: code to be evaluated if cond == TRUE.
 
Example: 

```r
x <- 1
if(x < 10){print('x is small')}
```

```
[1] "x is small"
```

if-else
=======

> if this condition is true, carry out task A, otherwise carry out task B

Use:
```r
    if (cond) { expr } else { expr }
```

Example:

```r
x <- 25

if(x < 10){
  print('x is small')
} else {
    print('x is big')
  } 
```

```
[1] "x is big"
```

Loops
=====

Loops allow you to run chunks of code multiple times.

The loop will run until a certain condition has been reached.

Use `for()`, `while()`, `repeat()` to construct loops.

`next` and `break` are used to modify the loop.

for()
====

The for loop progresses along a vector (`seq`), each element in turn (`var`).

Use:
```r
for(var in seq) { expr }
```

Example:

```r
    x <- c(1,2,3,4,5)

    for(i in 1:5) {
    print(x[i])
    }
```

```
[1] 1
[1] 2
[1] 3
[1] 4
[1] 5
```

while()
=======

The while loop runs while a condition is met.

Use:
```r
while(cond) { expr }
```


Example:

```r
    x <- 1

    while(x < 4) {
      x <- x + 1
      print(x)
    }
```

```
[1] 2
[1] 3
[1] 4
```


repeat
========

The repeat loop runs over a piece of code infinitely.

We need to use the `break` command within it to stop the loop.

Use:
```r
repeat { expr }
```


Example:

```r
    x <- 1

    repeat {
      print(x)
      x <- x + 1
      if(x > 5) break
    }
```

```
[1] 1
[1] 2
[1] 3
[1] 4
[1] 5
```


next
=====

The control `next` jumps to the next cycle in the loop, without completing the current one.

Example

```r
    x <- 1:4
    for (i in x) {
    if (i == 2) {
    next
    }
    print(i)
    }
```

```
[1] 1
[1] 3
[1] 4
```


Control Structures
==================

 - Allow you to encode decisions about running code:

  + run code if a certain condition is met: `if`, `if-else`

  + run code multiple times: loops. `for()`, `while()`, `repeat {}`. Use `break`, `next` to stop or skip.
  

 - SWIRL lesson covers for loops
 
 
