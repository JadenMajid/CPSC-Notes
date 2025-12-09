---
tags:
  - "#machine-learning/models/neural-networks"
aliases:
  - Convolution
---
# Description
When training [[Neural Networks]] on images, the individual activations of pixels is almost meaningless. We need to represent the context of the pixel

We can use convolutions in the neighbourhood of a given pixel to show context. 
Convolutions have some input vector or matrix, some kernel/weights/filter vector or matrix, and output some vector or matrix.
## Major Arguments
- Filter is the convolution we are applying
- Output channels is the amount of layers in the output tensor
- Padding is the number of "added rows and columns" on the outside of the input layer
- Stride is the number of pixels that are "skipped" per applied convolution
![[Screenshot 2025-11-26 at 2.21.45 PM.png]]

## Boundary Issue
What do we do at the edges?
- Pad outside input with zeros
- pad outside input with edge value
- mirror at the image edge
- ignore(return shorter $Z$ than input $X$)

## Formal Definition
![[Screenshot 2025-11-24 at 2.30.48 PM.png]]
## Naive Convolutions
The obvious way to do this is to give the [[Mean]] Pixel intensity in the neighbourhood, but it has some drawbacks
- Loss of spatial information
- Effectively a blur
	- We lose the crispness of edges
$$w_i=c, c\in \mathbb{R}$$

## Gaussian Blur
This controlled blur is like a weighted average focused on closer pixels.
$$w_i\alpha \exp(-\frac{1}{2}(\frac{i}{\sigma})^2)$$
## Negative Weights
Can use negative weights to get very specific feature relationships

## Laplacian of Gaussian
a smoothed 2nd derivative approximation
![[Screenshot 2025-11-24 at 2.48.17 PM.png]]
## Sharpen
An average that places negative weights on the surrounding pixels
$$w=[-a,b,-a]$$
## Centered Difference
Approximates 1st derivatives
$$w=[-1,0,1]$$
## Gabor Filter(2D)
[[Gaussian]] multiplied by $\sin$ or $\cos$ in $x$ or $y$. 
![[Screenshot 2025-11-24 at 2.50.01 PM.png]]
We can take the max of a vertical and horizontal Gabor to get a Horizontal/Vertical [[Edge Detector]]
![[Screenshot 2025-11-24 at 2.50.10 PM.png]]
# For [[Deep Learning]]
We can apply several different convolutions and create new features that we train the model on.
![[Screenshot 2025-11-24 at 2.24.42 PM.png]]
# Multi-Channel Inputs And Stride
Images can be seen as a [[Tensors|Tensor]], where each [[Color Models|Layer]] is a matrix in that [[Tensors|Tensor]]. 

Below, we see a [[RGB]] image mapped to a 16 layer tensor, where each layer is a different convolution on the original image. We take a $(3\times 64\times 64)\rightarrow(16 \times3\times3\times3)\text{ for each convolution area}\rightarrow(16\times64\times64)$
![[Screenshot 2025-11-26 at 2.05.03 PM.png]]

## Padding & Stride
Stride is the "skipping" of elements when applying convolutions. With a stride of 2, we reduce the dimensionality of the output of the convolution by a factor of $\frac{1}{2}$.
![[Screenshot 2025-11-26 at 2.19.13 PM.png]]
Padding is applied to the outside of the input layer that increases the "size" of each layer.
![[Pasted image 20251126142340.png]]
![[Screenshot 2025-11-26 at 2.22.43 PM.png]]

# Translation Invariance
Process each window the same way. Regardless of where we are in the image we should be applying the same operations.

> Apply the same weights regardless of where inside the image we are looking

## Local Connection & Weight Sharing

![[Screenshot 2025-11-26 at 2.30.03 PM.png]]
We can construct some weight matrix that is equivalent to applying a convolution on the input 
![[Screenshot 2025-11-26 at 2.33.14 PM.png]]

## Unfold/im2col
A way to gather local information and transform images into tensors.
![[Screenshot 2025-11-26 at 2.37.39 PM.png]]

![[Screenshot 2025-11-26 at 2.39.40 PM.png]]
# Examples
## 1D Convolution
We can apply convolutions on a signal $\vec x$, with some filter/kernel/weight $\vec v$, to product some final output vector $\vec z$
![[Screenshot 2025-11-24 at 2.24.58 PM.png]]

![[Screenshot 2025-11-24 at 2.26.52 PM.png]]