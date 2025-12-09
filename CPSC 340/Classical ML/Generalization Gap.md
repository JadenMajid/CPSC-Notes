---
aliases:
  - Egap
tags:
  - machine-learning/CPSC340
  - math/statistics
---
The generalization gap is the difference between model performance in seen and unseen data. it relates deeply with the [[Fundamental Tradeoff]]. The gap is normally referred to with $E_{gap}$. When training a model, we begin with a high $E_{train}$, and high $E_{test}$. As we move right on the [[Fundamental Tradeoff]] curve, we decrease [[Bias]] Error, which decreases both $E_{train}$, and $E_{test}$. After we pass a certain point, Bias Error is minimized, and [[Variance]] Error dominates when testing on unseen data. $E_{gap}$ is unknowable, because we cannot find an exact value for $E_{test}$, however we can estimate $E_{test}$ with [[Validation]] data.

$$E_{gap}=E_{train}-E_{test}$$

![[Pasted image 20251120183041.png]]

![[Pasted image 20251122144611.png]]