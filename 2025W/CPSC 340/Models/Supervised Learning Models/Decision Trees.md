---
tags:
  - machine-learning/CPSC340
  - "#machine-learning/models/non-parametric"
  - "#machine-learning/models/Parametric"
  - "#machine-learning/models/supervised"
  - "#machine-learning/problems/classification"
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
1. Fit a [[Decision Stump]] at the current node using the chosen scoring function.
2. Split the data according to the stump's rule so each child sees only the relevant subset.
3. Recurse on each child until the stopping criteria are hit (depth $t$, min samples per leaf, or the split gain drops below a threshold).
4. Store the leaf label (classification) or prediction value (regression) for every terminal node.
## Prediction
Apply found rules to input data, outputting $\hat{y}$
## Cost
- $n$ examples
- $d$ features
- $t$ depth
- Sorting each feature once per node lets us evaluate candidate thresholds in linear time after an initial $$O(n \log n)$$ sort.
### Training
Time (typical implementation): $$O(n\,d\,t)$$ when scanning unsorted thresholds or 

$$O(d\,n\log n)$$ when maintaining sorted feature lists at every split.  
Space: $$O(n + 2^t)$$ to hold the data subsets (or pointers) plus the tree nodes.
### Prediction
Per example: $$O(t)$$ comparisons along the path from root to leaf, so $$O(m\,t)$$ for $m$ predictions.  
Space: $$O(t)$$ to store the path/recursion stack.

![[Pasted image 20251122133640.png]]