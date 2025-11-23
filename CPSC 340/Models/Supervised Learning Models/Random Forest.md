---
tags:
  - Machine-Learning/CPSC340
  - Machine-Learning/Models/Parametric
  - Machine-Learning/Models/Non-Parametric
  - Machine-Learning/Models/Supervised
  - Machine-Learning/Problems/Classification
---
# Description
Random Forests are an [[Ensemble Methods|Ensemble]] [[Supervised Learning|Supervised]] [[CPSC 340/Classical ML/Classification]] machine learning model that uses a set of $k$ [[Bootstrapping|Bootstrapped]] [[Decision Trees]], then predict the [[Mode]] of the output. Random forests are a very generalist classifier that is hard to beat. Random forests generally outperform [[Decision Trees]] in [[Generalization Gap|Egap]] because they leverage multiple trees that make [[Independence|Independent]] errors that are more tolerant to [[Variance]]. 
## Hyper Parameters
- $k$ : Number of [[Decision Trees|Trees]]
- $t$ : maximum depth
	- [[Non-Parametric Models|Non-Parametric]] if $t=\infty$ 
	- [[Parametric Models|Parametric]] if $t<\infty$ 
- Bootstrapping method for examples
	- Normally select $n$ random examples from $X$, with replacement
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
