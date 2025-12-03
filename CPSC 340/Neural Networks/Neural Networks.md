---
tags:
  - Machine-Learning/CPSC340
  - Machine-Learning/Models/Neural-Networks
aliases:
  - Neural Network
---
adding Bias variables:

$$\hat{y}_i=\sum_{c=1}^{k}v_ch(w_c^Tx_i+\beta_c)+\beta$$
$$h(v)=\frac{1}{1+e^{-v}}$$
[[Neural Network Regression]] vs [[Classification]]
[[Neural Network for Multiclass Classification]]

# Summary
- unprecedented performance on difficult pattern recognition tasks
- allow for classification on non [[linearly separable]] data
- 1 layer gives us a universal approximator
	- but the layer might need to be huge
- some functions can be approximated with exponentially fewer parameters if we use [[Deep Learning]]

## Cost
- $L$ layers with widths $k_0=d, k_1, \dots, k_L=k$.
- Training with backpropagation over $E$ epochs and $n$ examples costs $$O\left(E\,n\,\sum_{\ell=0}^{L-1} k_\ell k_{\ell+1}\right)$$ because each layer pair is visited twice (forward + backward).
- Prediction per example is $$O\left(\sum_{\ell=0}^{L-1} k_\ell k_{\ell+1}\right)$$ operations and $$O\left(\max_\ell k_\ell\right)$$ working memory for activations.
- Storing the parameters requires $$O\left(\sum_{\ell=0}^{L-1} k_\ell k_{\ell+1}\right)$$ space.