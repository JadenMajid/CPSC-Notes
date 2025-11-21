---
tags:
  - CPSC340
  - Statistics
---
[[#340]]
The fundamental tradeoff is an idea from [[Classical Machine Learning]], that states that there are 3 sources of error:
- Irreducible Error
	- IE can never be removed from a model
- Bias error
	- BE is the result of constants in the data that influence most if not all datapoints
- Variance Error
	- VE is the result of [[Optimization Bias]], or overfitting. This results when the model is too complex, and is able to "memorize" the training data

![[Pasted image 20251120183041.png]]

The [[Fundamental Tradeoff]] is limited to [[Classical Machine Learning]]. Newer models such as in [[Deep Learning]] violate the [[Fundamental Tradeoff]], exhibiting a phenomena called [[Double Descent]], where increasing model complexity can lead to lower [[Validation]] Error
