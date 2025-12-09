---
tags:
  - machine-learning/CPSC340
aliases:
  - Ensemble
---
# Description
Ensemble methods are a category of models that train sub-models, and use their output to create some final prediction. The simple canonical method for [[CPSC 340/Models/Problems/Classification|Classification]] is to predict the [[Mode]] of the sub-model predictions. 

Some ensemble methods train many different types of models on the data, then train some model on the submodel's predictions that attempts to learn patterns in the accuracies of the submodels.
![[Pasted image 20251122163159.png]]
## Hyper Parameters
- Base learner choice (homogeneous like all trees vs heterogeneous mixes of trees/linear models/etc.).
- Resampling or feature-subsetting policy (bagging, pasting, random subspaces).
- Aggregation rule (majority vote, probability averaging, weighted combination, meta-learner for stacking).

## Examples
- [[Random Forest]] (bagging over decision trees)
- [[AdaBoost]] (boosting weak learners)
- [[Gradient Boosted Trees]]
- [[Stacking]] ensembles that train a meta-model on base learner outputs
## Training

### Steps
1. Select the type of base learners plus any re-sampling / feature sub-selection scheme.
2. Train each of the $b$ base learners on its assigned data slice (these runs are independent and can be parallelized).
3. Store every fitted learner alongside its aggregation rule.
## Prediction
1. Score the query point with every base learner.
2. Aggregate predictions (vote, mean, weighted combination, meta-model, etc.) to produce the final output.

## Cost
- $b$ base learners where training learner $i$ costs $T_i$ time and occupies $S_i$ space.
- $P_i$ denotes the per-example prediction cost of learner $i$.
### Training
Time: $$O\left(\sum_{i=1}^{b} T_i\right)$$ which simplifies to $$O(b\,T_{base})$$ when every learner has similar cost $T_{base}$.  
Space: $$O\left(\sum_{i=1}^{b} S_i\right)$$ to keep all fitted learners plus any aggregation weights.
### Prediction
Time: $$O\left(\sum_{i=1}^{b} P_i + b\right)$$ (the additional $b$ counts aggregation work; for uniform learners this is $$O(b\,P_{base})$$).  
Space: $$O(1)$$ additional per query because the models are pre-stored.
