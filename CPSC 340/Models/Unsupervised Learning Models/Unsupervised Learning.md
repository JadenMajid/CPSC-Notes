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
