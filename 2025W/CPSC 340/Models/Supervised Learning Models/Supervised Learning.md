---
tags:
  - machine-learning/CPSC340
  - machine-learning/models/supervised
aliases:
  - Supervised
---
# Description
Supervised learning is a [[Classical Machine Learning|Machine Learning]] paradigm in which a model learns rules for some dataset with labeled training examples. Supervised learning works best with large, well labelled datasets.

# Steps
1. Train model on some subset of data
2. Evaluate model on rest of data
3. Goal: high [[Testing]] performance, not [[Training]] performance

## Complexity
- Most parametric supervised learners train in $$O(E\,n\,d)$$ time for $E$ passes over $n$ examples with $d$ features (e.g., linear models, logistic regression, simple neural nets).
- Non-parametric learners (KNN, unrestricted trees) often shift the cost to inference, e.g., $$O(n\,d)$$ per query for KNN or $$O(t)$$ for a depth-$t$ decision tree.
- Data preprocessing (feature scaling, shuffling, batching) adds linear $$O(n\,d)$$ overhead but is usually dominated by model training.

```dataview
TABLE
    contains(file.tags, "Supervised") AS Supervised,
    contains(file.tags, "Unsupervised") AS Unsupervised,
    contains(file.tags, "Parametric") AS Parametric,
    contains(file.tags, "Non-Parametric") AS NonParametric
FROM "CPSC 340/Models/Supervised Learning Models"
SORT file.name ASC

```
