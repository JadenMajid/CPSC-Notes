- For Binary Classification our prediction is
	- $$o_i=v^Th(Wx_i)$$
	- $$\hat{y_i}=sign(o_i)$$
- we might train teh squared residual
	- $$f(W,v)=\sum^n_{i=1}log(1+exp(-y_io_i))$$
- this is like [[logistic regression]] with learned features
Binary Classification is a type of [[Supervised Learning]] where data is split into two different categories.
#340