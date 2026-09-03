---
tags:
  - machine-learning
---


## Naive Naive Bayes
![[Screenshot 2026-01-14 at 16.12.34.png]]
what if we model every permutation of input features?
- fucking terrible idea, we need $2^d-1$ parameters to do this
	- but can model any data with this, just exorbitantly space expensive

## Motivation
### Political Polling
- We want to know support for parties but we can't ask every person in a district.
- We can ask a subset of the population and create a sample
	- But how do we avoid systemic biases? like if there are categorical differences between people who answer the phone or not

![[Screenshot 2026-01-14 at 16.16.16.png]]
- For categorical data we can't use one dimension to represent categorical data, we need to one hot encode data
- Ordered categorical variables are called ordinal
- To find the most likely candidate we can just find $$\arg\max_c[\theta_c]$$
## Parameterizing Categorical Probabilities
we just one hot encode the non ordinal features
![[Screenshot 2026-01-14 at 16.21.38.png]]

$$\sum_{i=0}^k\theta_i=1$$
![[Screenshot 2026-01-14 at 16.21.03.png]]

## Sampling
Given $\theta$, produce samples.
![[Screenshot 2026-01-14 at 16.32.26.png]]

## Learning
How do we go from data to $\theta$
![[Screenshot 2026-01-14 at 16.34.29.png]]

-  Start with MLE
	- $\arg\max_{\theta} P(X|\theta)$
	- If we try to maximize log likelihood, the constraint on $\sum\theta_i=1$ is not respected, all values blow up to $\infty$
- We can resolve this with a new parameter $\tilde\theta$ that is unconstrained where $\theta\propto\tilde\theta$
	- Can maximize LL of $\tilde\theta$, then add a normalizing constant $Z_{\tilde\theta}=\sum\tilde\theta_i$
	- if we use $\theta=\frac{\tilde\theta}{Z_{\tilde\theta}}$, then we can satisfy the $\sum\theta_i=1$ constraint
- Infinitely many solutions for $\tilde\theta$ but unique solution for $\theta$
![[Screenshot 2026-01-14 at 16.46.52.png]]

## Dirichlet Prior
$$p(\theta_1,\ldots,\theta_k|\alpha_1,\ldots,\alpha_k)\propto\theta_1^{\alpha_1-1},\ldots,\theta_k^{\alpha_k-1}$$
- $\alpha$ is a hyperparameter
- 
### Dirichlet Visualization
for $k=3$, with symmetrical and non-symmetrical priors wrt components of $\theta$
![[Screenshot 2026-01-14 at 16.59.25.png]]

### Dirichlet MAP
![[Screenshot 2026-01-14 at 17.09.07.png]]

## Conjugate Priors
Are when Priors and posterior have same form they are called conjugate priors and they are very nice to work with :)