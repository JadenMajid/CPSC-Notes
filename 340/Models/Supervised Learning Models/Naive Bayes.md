---
tags:
  - CPSC340
  - Parametric
  - Non-Parametric
  - Supervised
---
# Description
Naive Bayes(NB) is a type of [[Supervised Learning]] model that is a [[Probabilistic Classifier]]. It uses from [[Bayes Theorem]] as a statistical basis. It is called Naive because it assumes that features are [[Independence|Independent]] given some class $C$, massively simplifying calculation. 
$$P(X|C)=P(x_1|C)*P(x_2|C)*...*P(x_d|C)$$
$$P(x_{ij} = c \mid y_i = \text{class}) \approx 
\frac{\text{\# examples in class with } x_{ij} = c}{\text{\# examples in class}}$$

Naive Bayes is commonly implemented with [[Bag of Words]], a way to convert textual data to categorical data.

NB can be parametric, or non-parametric depending on how the dimensionality of the dataset is handled. If an infinite number of examples have some finite dimensionality to their features, then it is [[Parametric Models|Parametric]]. If an infinite dataset results in infinite dimensionality in feature space, then it is [[Non-Parametric Models|Non-Parametric]]. 

### Laplace Smoothing
Laplace smoothing is when a smoothing term is added to avoid Bayes Poisoning. On a conceptual level, Laplace smoothing shifts the model from assuming the dataset is a factual representation of the true distribution, to assuming that any 
$$P(x_{ij} = c \mid y_i = \text{class}) \approx 
\frac{\text{\# examples in class with } x_{ij} = c}{\text{\# examples in class}}$$
## Hyper Parameters
- Laplace Smoothing
	- $\beta$ : smoothing constant
		- $\beta < 1$ : weaker smoothing(trust data)
		- $\beta = 1$ : standard smoothing
		- $\beta > 1$ : stronger smoothing(don't trust data)
## Training

### Steps
1. 
$$$$
## Prediction

## Cost
- $n$ examples
- $d$ features
### Training
$$$$
### Prediction
$$$$