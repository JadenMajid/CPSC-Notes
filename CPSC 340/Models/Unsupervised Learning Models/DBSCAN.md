---
tags:
  - Machine-Learning/CPSC340
  - Machine-Learning/Problems/Clustering
  - Machine-Learning/Models/Unsupervised
  - Machine-Learning/Models/Non-Parametric
---
# Description
DBSCAN (Density-Based Spatial Clustering of Applications with Noise) groups points that have at least `minPts` neighbors within an $\varepsilon$ radius and marks isolated points as noise. It can recover arbitrarily shaped clusters and automatically discards low-density regions.

## Hyper Parameters
- $\varepsilon$ : neighborhood radius for density checks.
- $\text{minPts}$ : minimum neighbors required for a point to become a core point.
## Training

### Steps
1. Scan each point and label it as *core* if it has at least `minPts` neighbors inside the $\varepsilon$-ball.
2. Grow a cluster from each unvisited core point by performing region queries and adding reachable density-connected points.
3. Label any remaining points that never satisfy the density condition as noise.
## Prediction
DBSCAN is mainly fit once; assigning a new point requires checking whether it lands within $\varepsilon$ of an existing core. If so, attach it to that cluster, otherwise label it as noise.
---
## Cost
- $n$ training examples
- $m$ test queries
- $d$ features
- Region query cost $Q$: $$Q = O(d)$$ with a spatial index, $$Q = O(n\,d)$$ without.
### Training
#### Time
$$O\left(n\,Q\right)$$ which is $$O(n^2d)$$ with a naive scan and can drop to $$O(n\log n)$$ (or better) when using a tree index (kd-tree/ball-tree) for range searches.
#### Space
$$O(n)$$ to store points, their cluster ids, and any spatial index.
---
### Prediction
#### Time
$$O(Q)$$ per query (again $$O(nd)$$ without an index or $$O(\log n)$$–$$O(n^{1-1/d})$$ with one).
#### Space
$$O(1)$$ additional per query beyond the stored model/index.
