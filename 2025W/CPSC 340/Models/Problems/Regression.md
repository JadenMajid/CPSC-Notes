tags:
  - Machine-Learning/Problems/Regression
  - Machine-Learning/Models/Supervised
# Description
Regression is a [[Supervised Learning|Supervised]] task that predicts continuous outputs from input features by modeling the relationship between dependent and [[Independence|Independent]] variables.

## Objectives
- Minimize expected loss (squared error, absolute error, etc.).
- Produce calibrated uncertainty estimates or confidence intervals when required.

## Typical Datasets
- Tabular sensor readings, time-series forecasts, pricing/valuation data, physics simulations.

## Common Algorithms
- [[Linear Regression]], [[Polynomial Regression]], [[LASSO Regression]], [[Support Vector Regression]], [[Neural Network Regression]].

## Evaluation
- Metrics: MSE/RMSE, MAE, $R^2$, adjusted $R^2$, log-likelihood.
- K-fold cross-validation or rolling-window validation for time-series.

## Complexity
- Closed-form linear regression with normal equations costs $$O(d^2 n + d^3)$$ time and $$O(d^2)$$ space due to the matrix inversion.
- Gradient-based solvers (SGD, mini-batch, coordinate descent) run $$O(E\,n\,d)$$ time for $E$ epochs and only need $$O(d)$$ space for the weight vector.
- Kernelized or support-vector regressors can require $$O(n^2)$$ memory and $$O(n^2 d)$$ time because they depend on the support vectors / Gram matrix.
