---
tags:
  - machine-learning/CPSC340
  - "#machine-learning/models/non-parametric"
aliases:
  - Non-Parametric
---
Non parametric models are models that grow infinitely with an infinite [[Training]] dataset. 

Examples: 
- [[K Nearest Neighbors|KNN]]
- Infinite [[Decision Trees]]
- and many others

## Complexity
- Training typically takes $$O(nd)$$ time and space because most non-parametric learners simply store the $n$ training points with $d$ features rather than fitting a fixed set of weights.
- Prediction grows with the stored data because each new example must interact with previously seen points (for example, KNN is $$O(nd)$$ per query and an unrestricted decision tree can grow to $$O(2^t)$$ nodes at depth $t$).
- Model size is therefore unbounded: doubling the dataset generally doubles the memory footprint and the per-query work.