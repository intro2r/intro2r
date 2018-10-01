---
layout: default
title: Formulae
---

# Formulas

## The basic formula

A formula in R is an object that is a symbolic expression of a relationship between one or more response or dependent variables (on the left), and one or more predictors or independent variables (on the right), with a tilde ~ separating the two sides.

E.g., `response variable ~ explanatory variables`

Thus, a basis regression analysis is: `y ~ x`

Additional variables can added to make a multiple regression. `y ~ x + z`

By fitting this model in R, we are actually estimating the parameters of the statistical model:

*y ~ beta1x + beta2z + error*

The formula we write does not explicitly include the intercept or the error term.

The error is assumed to be normal for regular regression models. We will specify it explicitly in generalized linear models.

The intercept is implicit in the model, but we can specify it explicitly:

`y ~ 1 + x + z`

To specify a model without an intercept, we can either add a 0
```r
y ~ 0 + x + z
```
or -1

```r
y ~ -1 + x + z
```

## Terms

The terms on either side of a formula can be any of 3 types:

  - A numeric vector, implying a single coefficient (e.g., slope beta)

  - A factor or ordered factor, implying one coefficient for each level

  - A matrix, implying a coefficient for each column

Functions can modify the variables in a formula. E.g., age > 40

## Symbolic operators

| Symbol 	| Use |
|---        |---   |
| + 	| separate effects in a formula | 
| : 	| interaction (A:B is interaction of A and B) | 
| * 	| main effects plus interactions A*B is equivalent to A + B + A:B | 
| ^ 	| crossed | 
| %in% 	| nested within | 
| / 	| nested within | 
| \| 	| conditional on; defines separate panels or shingles in lattice  | 
{: .table table-bordered .table-striped}

## Example right side of formulas

| Right Side of Formula 	| Meaning | 
|----                  |-----           |  
| A + B 	| main effects of A and B |  
| A:B 	| interaction of A with B |  
| A*B 	| main effects and interactions = A + B + A:B |  
| ABC 	| main effects and interactions A+B+C+A:B+A:C+B:C+A:B:C | 
| (A+B+C)^2 	| A, B, and C crossed to level 2: A+B+C+A:B+A:C+B:C | 
| ABC-A:B:C 	| same as above: main effects plus 2-way interactions | 
| 1 + state + state:county 	| nested ANOVA | 
| 1 + state + county%in%state 	| nested ANOVA emphasizing county nested in state | 
| state / county 	| nested ANOVA | 
| (1 / subject) 	| fit random intercepts for subjects | 
| (1+time / subject) 	| fit both random intercepts and random subject-specific slopes  | 
{: .table table-bordered .table-striped}

