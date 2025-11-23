---
tags:
  - Machine-Learning/CPSC340
  - Machine-Learning/Model/Supervised
  - "#Machine-Learning/Model/Classifier"
  - "#Machine-Learning/Model/Non-Parametric"
aliases:
  - KNN
---
# Description
KNN is a [[Supervised Learning|Supervised]] machine learning model that predicts the label of some datapoint by measuring its distance to [[Training]] examples, and predicting the [[Mode]] of the $k$ nearest neighbours. KNN is very fast to train, because training only consists of saving training data, but is very expensive to predict. KNN predictions need to iterate over all $m$ prediction examples and compare every one to all $n$ training datapoints. KNN can be expensive in both space and time  for large $n$.
## Hyper Parameters
- $k$ : number of neighbors to compare(typically odd to avoid tie breaks)
- [[Norms|Norm]] : typically [[L2|L_2]] norm
## Training
Store input training data
## Prediction
Find the distance of each $m$ testing examples to each $n$ training examples, predicting the [[Mode]] class of the $k$ closest training exampels
## Cost
- $n$ training examples
- $m$ testing examples
- $d$ features
### Training
Time
$$O(nd)$$
Space
$$O(nd)$$
### Prediction
Time$$O(mnd)$$
Space$$O(nd)$$

