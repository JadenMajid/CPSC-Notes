---
tags:
  - machine-learning
---
## Motivation: Predicting time left from Battery %
- How long until my phone dies?
	- could model with categorical vars, but that doesn't really make sense

## Gaussians
![[Screenshot 2026-01-21 at 16.15.19.png]]

### Why use a Gaussian?
- Central limit theorem
- Distribution with the maximum entropy for a given $\mu,\sigma^2$ 
- Simplifies a lot of stuff
	- Good enough to be useful

### Why not use a Gaussian?
- doesn't support poly-modal distributions
- sensitive to outliers
- truncated distributions
	- ![[Screenshot 2026-01-21 at 16.19.06.png]]
- asymmetric distributions
	- ![[Screenshot 2026-01-21 at 16.19.55.png]]
- 

### Gaussian Inference
#### Mode
maximized if $x=\mu$
#### likelihood of IID
$$\frac{1}{(\sqrt{2\pi}\sigma)^n}\exp{-\frac{1}{2\sigma^2}}\sum_{i=1}^n(x^{(i)}-y)^2$$
#### Sampling on a CDF
we want $f(x)$ for 
- $u \sim Unif([0,1])$
- The following to be true
	- $P(f(x)\le0.5)=0.5$
	- $P(0.173<f(x)\le0.273)=0.1$
- for gaussians there are no nice forms for $f^-1$, so we can compute numerically instead
	- can run binary search because all CDFs are monotonic
	- Box-Muller form is more efficient

### MLE for univariate Gaussians
![[Screenshot 2026-01-21 at 16.32.46.png]]

## Predictive Uncertainty
MAP allows us to account for uncertainty in our model $w$
$$Var[y|X]=\sigma^2\not\propto n$$

MAP commits to a single best $w$, 
![[Screenshot 2026-01-21 at 17.01.48.png]]

