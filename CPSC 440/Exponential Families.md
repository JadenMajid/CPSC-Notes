---
tags:
  - machine-learning
---
- Family of distributions that include categoricals and gaussians
- have a lot of nice properties
$$p(x|\theta)=\frac{h(x)\exp(\eta(\theta)^Ts(x))}{Z(\theta)}$$
- $s(x)$ : vector of sufficient statistics
	- tells us everything relevant to $\theta$ about $x$
	- exp fam. are the only class of distributions with finite sufficient statistics
- $\eta(\theta)$ : 
	- controls how parameters $\theta$ interact with $s(x)$
	- 440 will focus on $\eta(\theta)=\theta$
- $h(x)$ : support function 
	- contains terms that don't depend on $\theta$
	- also called base measure
- $Z(\theta)$ : normalizing constant
	- ensures $p(x|\theta)$ integrates to 1 over $x$

### Showing Bernoulli $\in$ Exp Fam.
![[Screenshot 2026-02-02 at 16.40.23.png]]

### Showing Gaussian $\in$ Exp Fam.
![[Screenshot 2026-02-02 at 16.42.45.png]]

## Learning with Exp. Fam.
![[Screenshot 2026-02-02 at 17.01.23.png]]

## Conjugate Priors
![[Screenshot 2026-02-02 at 17.08.53.png]]
