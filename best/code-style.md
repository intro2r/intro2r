R Style Guide I: Syntax
========================================================


![](http://intro2r.github.io/img/mcqueen.jpg)

*Steve McQueen, your (R) style guru*


# 1. Why have a code style?

### a. Coding styles help communication

Good coding style is like correct punctuation: 

you can manage without it, 

butitsuremakesthingseasiertoread.


### b. Your code has 1 author; but many readers

you, tomorrow

you, on Friday

you, next week

you, next year

your friend


your friend's friend

your mum

your reviewer

your third reviewer

your revising your manuscript

me

the dog 

...


### c. There are many different styles of writing code

![](http://intro2r.github.io/img/men-style.png)

 - different software or language 
 - different people
 
Try to develop a **consistent** style 


### d. Consistent style is important, because ...

 - **Focus should be what the code does, not how it is written.**
 - Changes in style mid-way through code increases effort and deceases understanding.
 - Especially important when working with others.


### e. Style can be applied to:

1. **Syntax**

2. Files

3. Functions

4. Code documentation



# 2. Syntax Style

## The arrangement of words and phrases

1. Object names.

2. Spacing.

3. Argument names.

4. Indenting.

5. Long lines.

6. Assignment.

7. Semicolons.

8. Quotes.

========

## 1. Object names

R is case-sensitive ... other software (M$, ...) is not.

### Principles

 - Variable names should be nouns.
 - Function names should be verbs.
 - Concise and meaningful (hard!)
 - Avoid periods (used in R to indicate class).
 - Avoid writing over common names (e.g., sqrt!)
 
 
 
### Best Practice

 - **Variables:** lowercase, numbers, and underscores.
    ``` 
    x
    my_sqrt
    ```
 - **Functions:** camelCase.
    ``` 
    myNewFunc()
    calcTemp()
    ```
 - All CAPS (constants).
 
 

## 2. Spacing

### Principle

- Ease of reading and understanding code.

 
### Best Practice

Put a space:

 - Before and after all operators (```=, +, -, <-```, etc...).
    ``` 
    1 + 3
    x / y
    ```
 - Arguments in function calls.
    ```
    seq(from = 1, to = 10)
    ```
 - *Except* around ```:```, ```::```, ```:::```.
    ```
    1:10
    ```
 - Use extra spacing to improve alignment.
    ```
    new_var <- 1:10
    x       <- 10:1
    ```
 - No spaces around ```()``` or ```[]```, unless there is a ```,```.
    ```
    seq(1, 10)
    x[1, ]
    ```
 

 
## 3. Argument names

Two kinds of arguments:

 - Supplies the **data**.
 - **Details** of computation.
 
 
 
### Principle

- Ease of understanding the function.
 
### Best Practice 
 
- Generally omit names of data arguments (they are often the first argument/s).
```
seq(1, 10)
mean(1:10)
```

- If you override the default, use the full argument name.
```
dir.create("my_new_file.r", recursive = TRUE)
```


## 4. Indenting

### Principle

- Show hierarchy of code and curly braces or brackets
- Make code easier to read, aligning related lines.



### Best Practice

- Use consistent indenting (2 or 4 spaces, never TABS).
- Always indent after curly braces.
```
# an example of a loop (we will do this later in the course)
for i in 1:10 {
  x <- 1 + 1
}
```


- Align arguments within a function if line overruns.
```
dir.create(file.path("testdir2", "testdir3"), 
               recursive = TRUE)
```

=======

## 5. Long lines

### Principle

- Ease of reading and following code.
- Ease of changing code.

### Best Practice

- Try and limit to 80 characters per line.
- If a function call is too long for one line, use one line each for the function name, each argument, and closing ```)```.
```
seq(from = 1,
      to = 100,
      by = 5)
```


## 6. Assignment

### Principle

- Separation of assignment and arguments.

### Best Practice

- Use ``` <- ``` for assignment.

- Never use ``` = ```.

- R was redesigned early on to permit use of ```=``` **in most cases but not all**.

```
x <- 1:10

# No, no, no, no, no, nooooooooooo ...
x = 1:10
```

See [here](https://stackoverflow.com/questions/1741820/what-are-the-differences-between-and-in-r?rq=1) for lots of gory details and discussion.


## 7. Semicolons

### Principle

- Do not use them.

### Best Practice

- Do not use them.


## 8. Quotes

### Principle

- Correct identification of text.
- Correct identification of escaped sequence inside character strings.

### Best Practice

- Double quotes ``` " " ``` and single quotes ``` ' ' ``` are usually **interchangable**.
- Double quotes are **preferred** because of the use of apostrophes in text strings.

```
simonSays <- "Great work, folks!"
```

[R help Quotes](https://stat.ethz.ch/R-manual/R-devel/library/base/html/Quotes.html)



    
# Links to various R style guides

[Google](https://google.github.io/styleguide/Rguide.xml): One of the first.

[Hadley Wickham](http://adv-r.had.co.nz/Style.html): Hadley WIckham built on Google's guide ...

[Hadley's Tidyverse](http://style.tidyverse.org/) ... and eventually re-organised everything.

[Microsoft](https://rattle.togaware.com/rattle-rstyle.html) A slightly different approach 

[Rchaeology of Style](https://cran.r-project.org/web/packages/rockchalk/vignettes/Rstyle.pdf) Learning R style by looking at the R source code

[C S Gillespie](https://csgillespie.wordpress.com/2010/11/23/r-style-guide/) R style and teaching

 
 - - -

Updated: 2018-09-29
