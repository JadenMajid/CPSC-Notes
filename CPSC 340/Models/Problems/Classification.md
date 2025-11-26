---
aliases:
  - Classify
tags:
  - Machine-Learning/Problems/Classification
  - Machine-Learning/Models/Supervised
---


# Binary Classification 
- For Binary Classification our prediction is
	- $$o_i=v^Th(Wx_i)$$
	- $$\hat{y_i}=sign(o_i)$$
- we might train the squared residual
	- $$f(W,v)=\sum^n_{i=1}log(1+exp(-y_io_i))$$
- this is like [[logistic regression]] with learned features
Binary Classification is a type of [[Supervised Learning]] where data is split into two different categories.

## Complexity
- Linear classifiers trained with gradient descent (logistic regression, linear SVM) cost $$O(E\,n\,d)$$ time for $E$ passes over $n$ examples with $d$ features, and $$O(d)$$ memory for the weight vector.
- Kernelized or nearest-neighbor classifiers retain the training set, so their prediction cost grows to $$O(n\,d)$$ per query.
- Tree- and ensemble-based classifiers cost $$O(nd\log n)$$–$$O(n d t)$$ to fit $t$ depth trees and $$O(t)$$ time per prediction.