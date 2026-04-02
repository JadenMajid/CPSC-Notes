---
tags:
  - machine-learning
---
![[Screenshot 2026-01-26 at 16.13.38.png]]
![[Screenshot 2026-01-26 at 16.16.28.png]]![[Screenshot 2026-01-26 at 16.16.56.png]]
- Above plots are for some $d=2$ data, the rings + color are the prior.
- $$P(x|\sigma^2)$$$$
P(x|\Sigma^2) \text{ where }\Sigma^2\text{ is diag.}$$ $$P(x|\Sigma^2)\text{ with no restrictions on }\Sigma$$

## Degenerate Gaussians
Gaussians are degenerate if $\Sigma$ is not invertible
![[Screenshot 2026-01-26 at 16.25.17.png]]
- Degeneracy is possible to all linear subspaces of a dimension(other than $d$)
![[Screenshot 2026-01-26 at 16.33.22.png]]
![[Screenshot 2026-01-26 at 16.53.08.png]]
- $x,z$ are normal in their univariate dists, but not normal in $xz$ bivariate space
![[Screenshot 2026-01-26 at 16.52.57.png]]
## MLE
![[Screenshot 2026-01-26 at 16.58.41.png]]
![[Screenshot 2026-01-26 at 17.00.12.png]]
$$a^TBc=\langle ac^T, B\rangle_F$$
$$\langle A, C\rangle_F+\langle B, C\rangle_F=\langle A+B, C\rangle_F$$
- can do outer product of vecs then Frobenius inner product with inner matrix 
![[Screenshot 2026-01-26 at 17.06.44.png]]
## MAP
![[Screenshot 2026-01-26 at 17.17.07.png]]
![[Screenshot 2026-01-26 at 17.18.14.png]]

