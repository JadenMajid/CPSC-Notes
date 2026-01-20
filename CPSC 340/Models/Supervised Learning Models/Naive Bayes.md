---
tags:
  - machine-learning/CPSC340
  - machine-learning/models/Parametric
  - machine-learning/models/non-parametric
  - machine-learning/models/supervised
  - "#machine-learning/problems/classification"
---
# Description
Naive Bayes(NB) is a type of [[Supervised Learning]] model that is a [[Probabilistic Classifier]]. It uses from [[Bayes Theorem]] as a statistical basis. It is called Naive because it assumes that features are [[Independence|Independent]] given some class $C$, massively simplifying calculation. 
$$P(X|C)=P(x_1|C)*P(x_2|C)*...*P(x_d|C)$$
$$P(x_{ij} = c \mid y_i = \text{class}) \approx 
\frac{\text{\# examples in class with } x_{ij} = c}{\text{\# examples in class}}$$

Naive Bayes is commonly implemented with [[Bag of Words]], a way to convert textual data to categorical data.

NB can be parametric, or non-parametric depending on how the dimensionality of the dataset is handled. If an infinite number of examples have some finite dimensionality to their features, then it is [[Parametric Models|Parametric]]. If an infinite dataset results in infinite dimensionality in feature space, then it is [[Non-Parametric Models|Non-Parametric]]. 

We can add a cost table that we optimize on, rather than raw probabilities(if we want to weight the cost of misclassification to be different than uniform)
![[Screenshot 2026-01-12 at 16.58.36.png]]

Naive Bayes is similar to product of bernoullis, except we tighten assumption to "dims of X are indep given y class"

### Bayes Poisoning
Bayes poisoning is when a data point has not been seen with a given class, resulting in a $P(x_{ij} = c \mid y_i = \text{class})=0$. This 0 propagates across the entire chain of probabilities, resulting in an output prediction of % for the class.
### Laplace Smoothing
Laplace smoothing is when a smoothing term is added to avoid Bayes Poisoning. On a conceptual level, Laplace smoothing shifts the model from assuming the dataset is a factual representation of the true distribution, to assuming that there's a small chance of observing any possible event, even if it wasn't present in the training data.
$$P(x_{ij} = c \mid y_i = \text{class}) \approx 
\frac{\text{\# examples in class with } x_{ij} = c}{\text{\# examples in class}}$$
## Hyper Parameters
- Laplace Smoothing(if used)
	- $\beta$ : smoothing constant
		- $\beta < 1$ : weaker smoothing(trust data)
		- $\beta = 1$ : standard smoothing
		- $\beta > 1$ : stronger smoothing(don't trust data)
## Training
We need to learn the conditional distribution of each of the $d$ features for every class.

### Steps
1. Initialize class-count and feature-count tables to zero.
2. For every training example, increment its class count and update the per-feature statistics associated with that class (categorical counts or running Gaussian means/variances).
3. Apply Laplace/variance smoothing as needed so that unseen feature values still receive non-zero probability mass.
4. Store the class priors $P(y=c)$ and the conditional likelihood parameters $P(x_j \mid y=c)$ for all $j,c$.
## Prediction
### Steps
1. For a new point, compute the log-posterior for each class: $\log P(y=c) + \sum_j \log P(x_j \mid y=c)$.
2. Choose the class with the highest posterior or return the normalized probabilities.

## Cost
- $n$ training examples
- $m$ testing examples
- $d$ features
- $k$ classes
### Training
Time
$$O(nd)$$ to sweep the dataset once (each example updates only the stats for its class).
Space
$$O(dk)$$
### Prediction
Time
$$O(mdk)$$
Space
$$O(k)$$ working memory for the per-class log-likelihoods.