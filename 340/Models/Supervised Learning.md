---
tags:
  - CPSC340
---
# Description
Supervised learning is a [[Classical Machine Learning|Machine Learning]] paradigm in which a model learns rules for some dataset with labeled training examples. Supervised learning works best with large, well labelled datasets.

# Steps
1. Train model on some subset of data
2. Evaluate model on rest of data
3. Goal: high [[Testing]] performance, not [[Training]] performance

```dataview
TABLE
    contains(file.tags, "#Supervised") AS Supervised,
    contains(file.tags, "#Unsupervised") AS Unsupervised,
    contains(file.tags, "#Parametric") AS Parametric,
    contains(file.tags, "#Non-Parametric") AS NonParametric
FROM "340/Models/Supervised Learning Models"
SORT file.name ASC

```
