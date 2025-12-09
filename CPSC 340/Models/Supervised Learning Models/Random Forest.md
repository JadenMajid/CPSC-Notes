---
tags:
  - machine-learning/CPSC340
  - machine-learning/models/Parametric
  - machine-learning/models/non-parametric
  - machine-learning/models/supervised
  - machine-learning/problems/classification
---
#### Time
Each bootstrapped tree costs roughly $$O(n\,d\,t)$$ when scanning thresholds or $$O(n\,d\,\log n)$$ when maintaining sorted feature lists, so the full forest is $$O(k\,n\,d\,t)$$ (or $$O(k\,n\,d\,\log n)$$ in the sorted variant).
#### Space
$$O(k\,2^t)$$ to store the tree structures plus $$O(n\,d)$$ for the bootstrapped samples if they are materialized.
	- [[Parametric Models|Parametric]] if $t<\infty$ 
- Bootstrapping method for examples
	- Normally select $n$ random examples from $X$, with replacement
#### Space
$$O(k)$$ to keep the per-tree votes/logits before aggregation.
- Bootstrapping method for features
	- Normally select $\sqrt{n}$ random features at each [[Decision Stump]]
## Training

### Steps
1. Bootstrap Dataset $X_i$ from $X$
2. Train decision tree on $X_i$, bootstrapping features at each stump
3. Repeat for $k$ trees and datasets
4. Store $k$ trees
## Prediction

### Steps
1. Predict each testing example $x_i$ on every tree
2. $\hat{y_i}=$[[Mode]] of $k$ trees
3. Repeat for all testing examples
## Cost
- $n$ training examples
- $m$ testing examples
- $d$ features
- $k$ trees
- $t$ maximum depth
### Training
#### Time
$$O(n^2dkt)$$
Optimizable to 
$$O(ndkt\log n)$$
#### Space
$$O(kdn)$$
### Prediction
#### Time
$$O(mkt)$$
