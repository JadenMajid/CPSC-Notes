adding Bias variables:

$$\hat{y}_i=\sum_{c=1}^{k}v_ch(w_c^Tx_i+\beta_c)+\beta$$
$$h(v)=\frac{1}{1+e^{-v}}$$
[[Neural Network Regression]] vs [[Binary Classification]]
[[Neural Network for Multiclass Classification]]

## Summary
- unprecedented performance on difficult pattern recognition tasks
- allow for classification on non [[linearly separable]] data
- 1 layer gives us a universal approximator
	- but the layer might need to be huge
- some functions can be approximated with exponentially fewer parameters if we use [[Deep Learning]]