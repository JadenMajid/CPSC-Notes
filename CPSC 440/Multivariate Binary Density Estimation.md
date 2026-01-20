---
tags:
  - machine-learning/CPSC440
---
## Motivation
### Traffic congestion Modelling
![[Screenshot 2026-01-12 at 16.19.53.png]]
We want some model of the above data to identify probs or route buses

### Spam Filtering
- Basically the same as 340 problem, given bag of words predict class of spam or not
- See [[Naive Bayes]]
- Remember the Naive Bayes assumption:
	- $p(x_1,...,x_d,y)=p(x_1|y)*...*p(x_d|y)p(y)$
- Naive bayes performs much better than product of bernoullis for sampling, but output still looks kind of garbage
	- ![[Screenshot 2026-01-12 at 17.08.25.png]]
- 

## Notation
- $n$ examples
- $d$ features
- $x^{(3)}$ is a vec with $d$ elems
- $X_3$ is 3rd dim of $X$
	- column vec
- $x_3$ is a value

## Product of Bernoullis
![[Screenshot 2026-01-12 at 16.24.14.png]]
- Simple model for multivariate data
- Assumes that all dimensions are independent
- makes learning super easy but kinda trash(sometimes)
	- Samples on MNIST![[Screenshot 2026-01-12 at 16.40.05.png]]
- Assumption often wrong but "good enough to be useful"





