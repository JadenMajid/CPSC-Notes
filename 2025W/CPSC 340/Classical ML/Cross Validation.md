---
aliases:
  - CV
tags:
  - machine-learning/CPSC340
---
# Description
Cross-validation is a method used in machine learning and statistics to evaluate how well a model [[Generalization Gap|generalizes]] to unseen data. It’s a way to get a more reliable estimate of model performance than just splitting your data into a single [[Training]] set and [[Testing]] set.

Cross validation is a way of better estimating the [[Generalization Gap]] of a set of hyper parameters for a particular model. 
## Hyper Parameters
- $k$ : number of folds
### Steps
1. Shuffle data randomly
2. Split data into $k$ parts
3. For each $i\in [1,k]$ parts, train model on $X-X_i$ and evaluate performance with $X_i$
4. Return [[Mean]] of [[Validation]] Error
## Cost
- $c$ : Cost of model
- $k$ : number of folds
$$O(ck)$$