---
tags:
  - Machine-Learning/Models/Unsupervised
  - "#Machine-Learning/Problems/Clustering"
---
Clustering is an [[Unsupervised Learning]] problem where similar examples in some dataset are grouped. Evaluating the performance of a Clustering algorithm can be difficult because there is no ground truth to compare against.

Clustering is closely related to [[Classification]]
![[Pasted image 20251122180356.png]]
# Algorithms
- [[K-Means]]
- [[DB-SCAN]]
- [[Hierarchical Clustering]]
- [[Agglomerative Clustering]]
# Ensemble Clustering

## Complexity
- [[K-Means]] / [[K-Medians]]: $$O(t\,p\,n\,k\,d)$$ to fit $k$ centroids over $t$ random restarts and $p$ iterations; $$O(kd)$$ space.
- [[DB-SCAN]]: $$O(n^2d)$$ without a spatial index and $$O(n\log n)$$–$$O(n^{1+1/d})$$ with one; $$O(n)$$ space.
- [[Hierarchical Clustering]] / [[Agglomerative Clustering]]: naive implementations run $$O(n^2\log n)$$ time and $$O(n^2)$$ space because they maintain all pairwise distances.
