---
tags:
  - Machine-Learning/Models/Unsupervised
  - "#Machine-Learning/Problems/Clustering"
  - Machine-Learning/Models/Parametric
aliases:
  - K-Medians
---
# Description
K-Means is an [[Unsupervised Learning]] algorithm that attempts to [[Clustering|Cluster]] some dataset into $k$ clusters. K-Means is guaranteed to [[Converge]] and is [[Deterministic]], however is affected by initial [[Mean]] initializations. K-means is most often run with $t$ random restarts. K-Means can only find [[Convex]] clusters.

The labels assigned to each mean are not guaranteed to be consistent across random restarts, so using the [[Mode]] label across random restarts is not useful.

K-Medians is a very similar model, however reassigns the medians at each step to the median feature value of each feature.

K-Means/K-Medians can be evaluated by summing the total distance from each point to their assigned cluster. This [[Loss Function]] should not be interpreted blindly, because higher values of $k$ will [[Monotonic|monotonically]] decrease the loss function
![[Pasted image 20251122181819.png]]
## Hyper Parameters
- $k$ : how many clusters to fit
- $t$ : how many random restarts to do
- [[Norms|Norm]] function to use when calculating distance
- Point reassignment algorithm : [[Mean]] or [[Median]] (K-means vs K-medians)
## Training

### Steps
1. loop $t$ times
	1. loop until convergence(clusters do not change) or $p$ iterations reached
		1. initialize $k$ clusters to random datapoints
		2. assign each point in $X$ to its closest cluster using the loss function
		3. reassign each cluster to the Mean/Median of its points' features
2. store "best" clustering(lowest total sum of distances of points to their means) 
## Prediction

### Steps
1. return label of closest cluster for each testing example in $\tilde{X}$ 
## K-means Cost
- $n$ training examples
- $m$ testing examples
- $d$ features
- $k$ points
- $t$ random restarts
- $p$ maximum iterations

---

### Training
#### Time
$$O(t \cdot p \cdot n \cdot k \cdot d)$$

#### Space
$$O(n \cdot d + k \cdot d)$$

---

### Prediction
#### Time
$$O(m \cdot k \cdot d)$$

#### Space
$$O(k \cdot d)$$

---

## K-medians Cost
- $n$ training examples
- $m$ testing examples
- $d$ features
- $k$ points
- $t$ random restarts
- $p$ maximum iterations

---

### Training
#### Time
$$O(t \cdot p \cdot k \cdot n \cdot d)$$

#### Space
$$O(n \cdot d + k \cdot d)$$

---

### Prediction
#### Time
$$O(m \cdot k \cdot d)$$

#### Space
$$O(k \cdot d)$$