---
tags:
  - "#Machine-Learning/Models/Neural-Networks"
---
When training [[Neural Networks]] on images, the individual activations of pixels is almost meaningless. We need to represent the context of the pixel

We can use convolutions in the neighbourhood of a given pixel to show context. 
Convolutions have some input vector or matrix, some kernel/weights/filter vector or matrix, and output some vector or matrix.

## Boundary Issue
What do we do at the edges?
- Pad outside input with zeros
- pad outside input with edge value
- mirror at the image edge
- ignore(return shorter $Z$ than input $X$)

# Formal Definition
![[Screenshot 2025-11-24 at 2.30.48 PM.png]]
# Naive Convolutions
The obvious way to do this is to give the [[Mean]] Pixel intensity in the neighborhood, but it has some drawbacks
- Loss of spatial information
- Effectively a blur
	- We lose the crispness of edges

# Gaussian Blur
This controlled blur is like a weighted average focused on closer pixels.

# Negative Weights
Can use negative weights to get very specific feature relationships

# For [[Deep Learning]]
We can apply several different convolutions and create new features that we train the model on.
![[Screenshot 2025-11-24 at 2.24.42 PM.png]]
# Examples
## 1D Convolution
We can apply convolutions on a signal $\vec x$, with some filter/kernel/weight $\vec v$, to product some final output vector $\vec z$
![[Screenshot 2025-11-24 at 2.24.58 PM.png]]

![[Screenshot 2025-11-24 at 2.26.52 PM.png]]