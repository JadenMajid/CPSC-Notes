---
tags:
  - "Machine-Learning/CPSC340"
---
- For [[Regression]]: our prediction is
	- $$\hat{y_i}=v^Th(Wx_i)$$
- we might train the squared residual
	-$$ f(W,v)=\frac{1}{2}\sum^n_{i=1}(\hat{y_i}-y_i)^2$$

## Cost
- $n$ examples, input dimension $d$, $h$ hidden units, $k=1$ output.
- Training with backpropagation across $E$ epochs costs $$O(E\,n\,(dh + h))$$ time and $$O(dh + h)$$ space for the weights.
- Prediction per example is $$O(dh + h)$$ because it requires one forward pass through the hidden layer and output node.
