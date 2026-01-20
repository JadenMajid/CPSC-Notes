aliases:
  - Classify
tags:
  - Machine-Learning/Problems/Classification
  - Machine-Learning/Models/Supervised
# Description
Binary classification is a type of [[Supervised Learning]] where labeled data is split into two categories. Logistic-style models often compute
$$o_i = v^\top h(Wx_i), \qquad \hat{y}_i = \operatorname{sign}(o_i)$$
and minimize a loss such as
$$f(W,v) = \sum_{i=1}^n \log(1 + e^{-y_i o_i})$$
which mirrors [[logistic regression]] with learned features.

## Objectives
- Separate positive and negative classes with low generalization error.
- Control class imbalance via thresholding, weighting, or resampling when necessary.

## Typical Datasets
- Email spam vs. ham, medical diagnosis (disease vs. healthy), fraud detection.

## Common Algorithms
- [[Logistic Regression]], linear / kernel SVMs, [[CPSC 340/Models/Supervised Learning Models/Decision Trees]], [[Random Forest]], [[Neural Networks]].

## Evaluation
- Metrics: accuracy, precision/recall, F1, ROC-AUC, PR-AUC depending on imbalance.
- Train/validation split or cross-validation paired with calibration curves / confusion matrices.

## Complexity
- Linear classifiers trained with gradient methods cost $$O(E\,n\,d)$$ time and $$O(d)$$ space for weights.
- Kernelized or nearest-neighbor methods keep the training set, yielding $$O(n\,d)$$ prediction cost per query.
- Tree/ensemble methods cost $$O(n\,d\,t)$$ to fit depth-$t$ trees and $$O(t)$$ per prediction, with forests multiplying by the number of trees.

## Complexity
- Linear classifiers trained with gradient descent (logistic regression, linear SVM) cost $$O(E\,n\,d)$$ time for $E$ passes over $n$ examples with $d$ features, and $$O(d)$$ memory for the weight vector.
- Kernelized or nearest-neighbor classifiers retain the training set, so their prediction cost grows to $$O(n\,d)$$ per query.
- Tree- and ensemble-based classifiers cost $$O(nd\log n)$$–$$O(n d t)$$ to fit $t$ depth trees and $$O(t)$$ time per prediction.