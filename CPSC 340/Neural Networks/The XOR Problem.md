---
tags:
  - "machine-learning/CPSC340"
---
we want to output like an xor gate
we can't do this with a [[linear model]] because the data is not linearly separable
we CAN do this with [[Neural Networks]]


with 2 inputs, and 3 neurons, we map our data into a 3 dimensional space that is [[linearly separable]]

#machine-learning/CPSC340
#machine-learning/CPSC340
#machine-learning/CPSC340

## Cost
- The canonical XOR network uses two hidden neurons and one output neuron, so forward or backward passes are constant-size $$O(1)$$ computations with respect to the dataset dimensionality.
- Training therefore scales linearly with the number of labeled XOR examples: $$O(E\,n)$$ for $E$ passes through $n$ samples, because each pass performs constant work per example.