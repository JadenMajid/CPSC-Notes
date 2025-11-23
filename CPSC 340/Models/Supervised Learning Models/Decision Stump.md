---
tags:
  - Machine-Learning/CPSC340
  - "#Machine-Learning/Model/Supervised"
  - "#Machine-Learning/Model/Parametric"
  - "#Machine-Learning/Model/Classifier"
---
# Description
Decision Stumps are equivalent to [[Decision Trees]] with a depth of 1. One rule is learned on a dataset, and predictions are made depending on that rule. 
![[Pasted image 20251122133817.png]]
## Hyper Parameters
- Scoring function
	- [[Accuracy]]
	- [[Infogain]]
## Training
To learn a stump we need to find the following:
- What feature to split on
- What threshold value to split on
- What classes to use on leaves
### Steps
1. Search for rule in input dataset with the best score using scoring function
	1. Get a baseline(like the [[Mode]] of the input)
	2. Iterate on examples(as thresholds)
	3. Iterate on features(nested)
$$$$
## Prediction
Apply found rules to input data, outputting $\hat{y}$
## Cost
- $n$ examples
- $d$ features
- $k$ thresholds(unique $x_{ij}$ across $j$)
### Training
$$O(ndk)$$
### Prediction
$$O(1)$$