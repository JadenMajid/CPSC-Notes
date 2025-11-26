---
tags:
  - "Machine-Learning/CPSC340"
---
- Input is connected to some hidden layer
- Hidden layer is connected to multiple output units
- we can predict by maximizing $o_{ic}$ over all $c$
- $$V=l \text{ by } x $$
- can convert to probabilities by taking [[Softmax]]
- 

## Cost
- $n$ examples, $d$ features, $h$ hidden units, $k$ output classes.
- Training with backpropagation across $E$ epochs takes $$O\left(E\,n\,(dh + hk)\right)$$ time because each mini-batch requires two matrix multiplications (forward + backward) per layer pair.
- Prediction per example costs $$O(dh + hk)$$ time and $$O(h + k)$$ working memory to hold activations and logits before the [[Softmax]].
- Parameter storage for the weight matrices and biases is $$O(dh + hk)$$.