---
tags:
  - Machine-Learning/CPSC340
  - Machine-Learning/Models/Neural-Networks
---
# Description
Deep learning models are like [[Neural Networks]] with multiple hidden layers. The "divider" for deep learning vs normal neural networks has changed with time, tending towards deeper networks.

> Core Idea: compose basic operations into complex functions


![[Pasted image 20251122145012.png]]
Deep learning sometimes results in a phenomena called [[Double Descent]], that violates the [[Fundamental Tradeoff]] from [[Classical Machine Learning]]. 

$$o_i=h(z_{i1}^{(2)})$$
$$z_{i1}^{(2)}=h(x_{i1})$$
- For speech recognition and computer vision and language processing
	- Non non-deep learning methods have ever given this level of performance.
	- Deep models continue to improve performance, but at a slowing rate recently
	- Some overfitting to popular datasets like ImageNet
		- But the drop is very consistent, so this suggests that it may ![[Screenshot 2025-12-03 at 2.12.01 PM.png]]
- We are still missing a lot of theory and understanding for deep learning
	- we don't really understand why it works so well
	- sometimes models look smarter than they really are because training data/validation data is flawed

## Limitations
> [!QUOTE]
> Try to break your models, don't just get them to work

 Weird inputs can make models act unpredictably.![[Screenshot 2025-12-03 at 2.21.12 PM.png]]

- Networks may not understand fundamental concepts. 
	- Is being surrounded by grass a part of the fundamental idea of being a cow?![[Screenshot 2025-12-03 at 2.34.52 PM.png]]
	- Kids can do this, but models can struggle with this
- The model will learn from ALL available info in the training data
	- Here, the model learned that the type of scan affects the likelihood that the enlarged heart condition is present.![[Screenshot 2025-12-03 at 2.36.49 PM.png]]
- Bias in data/labels/learning method
	- Models will pick up biases in the training data.![[Screenshot 2025-12-03 at 2.38.44 PM.png]]
	- We need to be mindful of what data we make available to models.
	- Can be a major issue depending on context
		- "Predicting repeat offenders"


> [!QUOTE]
> Sometimes no model is better than a broken model

### Adversarial usage
- Adversarial noise can be added which breaks some models
	- Here, imperceptible noise can be added which breaks the model's predictions.![[Screenshot 2025-12-03 at 2.23.03 PM.png]]
- TODO
	- ![[Screenshot 2025-12-03 at 2.34.32 PM.png]]

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
	- Deep networks have led to unprecedented performance