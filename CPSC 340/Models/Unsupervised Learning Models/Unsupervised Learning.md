---
tags:
  - Machine-Learning/Models/Unsupervised
aliases:
  - Supervised
---
# Description
Unsupervised learning is a [[Classical Machine Learning|Machine Learning]] paradigm in which tries to find some pattern in an unlabeled dataset.

# Steps


```dataview
TABLE
    contains(file.tags, "Supervised") AS Supervised,
    contains(file.tags, "Unsupervised") AS Unsupervised,
    contains(file.tags, "Parametric") AS Parametric,
    contains(file.tags, "Non-Parametric") AS NonParametric
FROM "CPSC 340/Models/Unsupervised Learning Models"
WHERE Unsupervised=true
SORT file.name ASC

```

## Complexity
- Iterative clustering / dimensionality-reduction methods usually run $$O(E\,n\,d)$$ per epoch, where $E$ is the number of refinement passes (e.g., sparse autoencoders, PCA with gradient updates).
- Density and graph-based approaches (DBSCAN, spectral clustering) can cost $$O(n^2)$$ or more because they require repeated neighborhood or similarity computations.
- Since labels are unavailable, additional $$O(n\,d)$$ work is often spent on internal validation metrics (silhouette score, reconstruction error) to choose hyperparameters.
