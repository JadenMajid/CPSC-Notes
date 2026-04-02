---
tags:
  - machine-learning/CPSC440
  - machine-learning
---
Density Estimation: going from data -> prob model
Inference: "Doing things" with a prob model

Inference task: computing dataset probabilities
$$p(x|\theta)=\theta^x(1-\theta)^{1-x}$$

Inference task: given $\theta$, find $X$ that maximizes $p(X|\theta)$
- for bernoullis, $p(X|\theta)=\theta^{n_1}(1-\theta)^{n_0}$
- if $\theta<0.5$, then the most likely dataset is $X=(0,0,...,0)$
- The modal dataset is really weird: if $\theta < 0.2$ we expect 20% of samples to be 0

Sampling is the 'opposite' of density estimation.
- Given some model, generate IID examples
- trivial for simple models like bernoulli, but good for complicated models
	- "this person does not exist" model evaluation by humans

## MLE
The likelihood function is a function from parameters that tells us how likely data is from parameters. the MLE is the $\theta$ with the highest likelihood. Usually we maximize log-likelihood instead of likelihood b/c log turns multiplication into addition

- $\int_0^1 \mathbf{L}\ne 1$  

$$\mathbf{L}(\theta)=p(X|\theta)$$
![[Screenshot 2026-01-07 at 16.23.25.png]]


- MLE is asymptotically optimal as $n\rightarrow\infty$
	- MLE is best for many problems (asymptotically)
- with small n, it can do bad things like n=4, \[1,1,0\]
- for "unlucky" $X$ it can also do bad things
- MLE has a tendency to overfit
- 340 solution was [[Naive Bayes|Laplace Smoothing]]
- Data could be most likely for a really weird $\theta\rightarrow$ overfitting
	- if $\theta$ allows high complexity then model can just memorize training data exactly
## MAP
After seeing data $X$ which $\theta$ is most likely?
![[Screenshot 2026-01-07 at 17.01.06.png]]
![[Screenshot 2026-01-07 at 17.12.36.png]]

## Beta Distribution
![[Screenshot 2026-01-07 at 17.13.26.png]]
Useful because its very flexible, and the posterior and MAP have very simple forms
![[Pasted image 20260112160602.png]]

