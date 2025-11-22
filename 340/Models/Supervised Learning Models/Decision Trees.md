---
tags:
  - CPSC340
  - "#Non-Parametric"
  - "#Parametric"
  - "#Supervised"
---
# Description
Decision Trees are a type of [[Supervised Learning]] where simple rules for datasets are learned.
Nested rules are applied to predict the category of datapoints. Decision trees are like nested [[Decision Stump|Decision Stumps]].
## Hyper Parameters
- $t$
	- Max depth
- Scoring function
	- [[Infogain]]
	- [[Accuracy]]
## Training

### Steps
1. Train a [[Decision Stump]] at the root
2. Predict on input data, splitting it into two categories
3. If max depth not reached
	1. Pass data to 2 new [[Decision Stump|Decision Stumps]] and train them
## Prediction
Apply found rules to input data, outputting $\hat{y}$
## Cost
- $n$ examples
- $d$ features
- $k$ thresholds(unique $x_{ij}$ across $j$)
- $t$ depth
### Training
$$O(2^tndk)$$
### Prediction
$$O(nt)$$

![[Pasted image 20251122133640.png]]