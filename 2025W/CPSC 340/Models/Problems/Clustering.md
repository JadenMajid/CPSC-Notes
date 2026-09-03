tags:
  - Machine-Learning/Models/Unsupervised
  - "#Machine-Learning/Problems/Clustering"
# Description
Clustering is an [[Unsupervised Learning]] problem where similar examples are grouped without labeled targets. Because no ground truth is given, evaluation is harder than in [[Classification]].

## Objectives
- Discover coherent structure (dense regions, connected components, manifolds) in the data.
- Remain robust to noise/outliers and insensitive to feature scaling when possible.

## Typical Datasets
- Customer segmentation, document/topic grouping, gene expression data, image patches.

## Common Algorithms
- [[K-Means]] / [[K-Medians]] for convex clusters.
- [[DB-SCAN]] for density-based shapes.
- [[Hierarchical Clustering]] and [[Agglomerative Clustering]] for nested partitions.
- Ensemble clustering (e.g., consensus functions) averages multiple partitionings to improve stability.

## Evaluation
- Internal metrics: silhouette score, Davies–Bouldin, within-cluster sum of squares.
- External metrics (only when labels exist): adjusted Rand index, mutual information.
- Visualization (t-SNE/UMAP) to inspect structure qualitatively.

## Complexity
- [[K-Means]] / [[K-Medians]]: $$O(t\,p\,n\,k\,d)$$ to fit $k$ centroids over $t$ random restarts and $p$ iterations; $$O(kd)$$ space.
- [[DB-SCAN]]: $$O(n^2d)$$ without a spatial index and $$O(n\log n)$$–$$O(n^{1+1/d})$$ with one; $$O(n)$$ space.
- [[Hierarchical Clustering]] / [[Agglomerative Clustering]]: naive implementations run $$O(n^2\log n)$$ time and $$O(n^2)$$ space because they maintain all pairwise distances.
