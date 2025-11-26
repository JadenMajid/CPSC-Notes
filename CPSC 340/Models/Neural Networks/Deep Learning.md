---
tags:
  - "Machine-Learning/CPSC340"
---
Deep learning models are like [[Neural Networks]] with multiple hidden layers. The "divider" for deep learning vs normal neural networks has changed with time, tending towards deeper networks.
![[Pasted image 20251122145012.png]]
Deep learning sometimes results in a phenomena called [[Double Descent]], that violates the [[Fundamental Tradeoff]] from [[Classical Machine Learning]]. 

$$o_i=h(z_{i1}^{(2)})$$
$$z_{i1}^{(2)}=h(x_{i1})$$

## Learning
[[Loss Function|Loss Functions]] in Deep learning tend to be highly [[Non-Convex]], meaning they have many local minima. However, many of these local minima are actually quite good.

All learning methods for Deep learning are variations of [[Stochastic Gradient Descent]]
# Cost of layers
## Prediction
$$O(k^1d+k^1k^2...)$$
## Training
- $E$ epochs, $n$ examples, layer widths $k^0=d, k^1,\dots,k^L$.
- Backpropagation roughly doubles the work of a forward pass, so training is $$O\left(E\,n\,\sum_{\ell=0}^{L-1} k^\ell k^{\ell+1}\right)$$.
- Memory for activations during training is $$O\left(\sum_{\ell=0}^{L} k^\ell\right)$$ if activations are checkpointed layer by layer.
- need fewer parameters than "shallow but wide" [[Neural Networks]]
- Empirical Motivation for using multiple layers
	- Deep networks have lead to unprecedented performance