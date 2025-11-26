---
tags:
  - Machine-Learning/Problems/Regression
  - Machine-Learning/Models/Supervised
---
# Description
Regression is a a [[Supervised Learning|Supervised]] learning task that attempts to predict continuous output values based on some input. Regression models a relationship between dependent variable and one or more [[Independence|Independent]] variables. 
# Examples
- [[Linear Regression]]
- [[Polynomial Regression]]
- [[LASSO Regression]]
- [[Support Vector Regression]]

## Complexity
- Closed-form linear regression with normal equations costs $$O(d^2 n + d^3)$$ time and $$O(d^2)$$ space due to the matrix inversion.
- Gradient-based solvers (SGD, mini-batch, coordinate descent) run $$O(E\,n\,d)$$ time for $E$ epochs and only need $$O(d)$$ space for the weight vector.
- Kernelized or support-vector regressors can require $$O(n^2)$$ memory and $$O(n^2 d)$$ time because they depend on the support vectors / Gram matrix.
