---
tags:
  - Machine-Learning/CPSC340
  - "#Machine-Learning/Models/Parametric"
aliases:
  - Parametric
---
Parametric models are models in which a fixed amount of parameters are [[Training|Trained]] to a given Training dataset, and learn rules for a given model. 

The opposite of a [[Parametric Models|Parametric Model]] is a [[Non-Parametric Models|Non Parametric Model]].

A general rule of thumb for [[Parametric Models]], is `Given an infinite dataset, a parametric model will have a fixed size`

## Complexity
- Training usually scales with both the number of parameters $p$ and the number of examples $n$ (e.g., gradient descent style optimizers cost $$O(E\,n\,p)$$ for $E$ passes through the data).
- Prediction is independent of $n$ once the parameters are learned and typically costs $$O(p)$$ time and $$O(p)$$ space per example because only the fixed parameter vector is touched.
- Memory stays bounded by $$O(p)$$, so increasing the dataset does not increase the number of stored parameters, only the time spent estimating them.
