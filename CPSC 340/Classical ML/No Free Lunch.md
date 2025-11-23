---
tags:
  - Machine-Learning/CPSC340
---
The No Free Lunch Theorem states that there is no universally "best" model. It relates to the idea of a [[Generalization Gap]]. The evaluation of a model is dependent on the data used to test it. A general purpose algorithm may be a "jack of all trades, master of none".

Despite the theorem, some models do appear to generalize better. For example, [[Random Forest|Random Forests]] tend to generalize very well.

If we consider two models $A,B$, we can always construct some distributions $X_A,X_B$ that perform better for $A\&B$ respectively.