---
tags:
  - "CPSC340"
---
loss functions are scoring functions that determine the error of a model

In [[Supervised Learning]] loss functions are tools to determine how well a model can predict the given labels

$f(w)=||Xw-y||^2$

In [[Unsupervised Learning]] loss functions are less useful, but they can still give some indication of model performance.

The [[Norms]] used in a loss function can be used to control model complexity.

We want [[Convex]] loss functions, because all minima in a [[Convex]] loss function are guaranteed to be global minima.

Loss functions can add [[Regularization]], a tool to reduce [[Optimization Bias]]

#340