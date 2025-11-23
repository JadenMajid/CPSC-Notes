---
tags:
  - "Machine-Learning/CPSC340"
---
Deep learning models are like [[Neural Networks]] with multiple hidden layers. 
![[Pasted image 20251122145012.png]]
Deep learning sometimes results in a phenomena called [[Double Descent]], that violates the [[Fundamental Tradeoff]] from [[Classical Machine Learning]]. 

$$o_i=h(z_{i1}^{(2)})$$
$$z_{i1}^{(2)}=h(x_{i1})$$
# Cost of layers
## Prediction
$$O(k^1d+k^1k^2...)$$
- need fewer parameters than "shallow but wide" [[Neural Networks]]
- Empirical Motivation for using multiple layers
	- Deep networks have lead to unprecedented performance