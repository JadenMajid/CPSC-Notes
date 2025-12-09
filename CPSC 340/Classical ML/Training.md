---
tags:
  - "machine-learning/CPSC340"
---
Training is the process in which rules are learned for a given dataset. 

Training can look very different for [[Parametric Models]] and [[Non-Parametric Models]]. For example, in [[K Nearest Neighbors|KNN]], a type of [[Supervised Learning]], training is only the storage of [[Training]] Data.

We can always decrease training with further training or a more complex model. This is due to the [[Fundamental Tradeoff]], where our model can memorize our training dataset, and fit to the [[Variance]] in the dataset.

> [!NOTE] KEY PRINCIPLE
> DO NOT TRAIN ON TESTING DATA. TESTING DATA SHOULD BE LOOKED AT AT MOST ONCE.
