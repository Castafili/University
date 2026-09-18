---
date: 21/10/2025
tags:
  - economy
  - AUEB
---
- Assumes the dependence of response Y on inputs X<sub>1</sub>, X<sub>2</sub>, … X<sub>p</sub> is approx. linear:

$$ Y ≈ β_0 + β_1X_1 + β_2X_2 + … + β_pX_p $$

- Actually f(X<sub>1</sub>, X<sub>2</sub>, …, X<sub>p</sub>) is NEVER linear

- Useful both conceptually and practically

- Tool used for predictions and good starting point for sophisticated statistical learning methodologies

---
## Simple Linear Regression

Model: 
$$ Y = β_0 + β_1X + ε $$

$β_0$ : *intercept* 
$β_1$ : *slope*

Collectively they are called: *coefficients* or *parameters* (unknown)

Estimates $(\hat{\beta}_0, \hat{\beta}_1)$ will be made with training data sets. We can predict response $\forall$ value of X. 

Ex.
	X = x then the predict value of Y is:

$$\hat{y}=\hat{\beta_0}+\hat{\beta_1}x$$

___
## Estimating Coefficients

- Training data: *n* measurements on X and Y:

$$(x_1,y_1),(x_n,y_n),...,(x_n,y_n)$$

- For *i*th value of X, Y's predictions is: $\hat{y_i}=\hat{\beta_0}+\hat{\beta_1}x_i$
- Estimate $(\hat{\beta}_0, \hat{\beta}_1)$, the difference $e_i=y_i-\hat{y_i}$ is the *i*th *residual*
- Definition of Residual Sum of Squares:

$$\text{RSS}=e^2_1+e_2^2+...+e_n^2$$
$$\text{OR}$$
$$\text{RSS}=(y_1-\hat{\beta_0}-\hat{\beta_1}x_1)^2+(y_2-\hat{\beta_0}-\hat{\beta_1}x_2)^2+...+(y_1-\hat{\beta_n}-\hat{\beta_1}x_n)^2$$


___
## Least Squares criterion

lecture slides 5 page: 9 

---
Reached until page: 28 of lecture slides 5

Source: [[Applied Machine Learning in Econ]]

---
Created: 2025-10-21