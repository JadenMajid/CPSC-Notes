---
tags:
  - machine-learning
---
- Allows us to find marginal likelihood of hyper parameters
- 
![[Screenshot 2026-02-02 at 16.23.34.png]]
- 3 more likely than 7 because there are a lot more good $d=3$ models than $d=7$. We integrate over our weights to find marginal likelihood, so the poor fits lower the marginal likelihood 
![[Screenshot 2026-02-02 at 16.25.29.png]]

### Choosing Kernels
- Can just compare marginal likelihood between different transforms$$p(y|X,\text{Poly}) > p(y|X,\text{RBF})$$
- 