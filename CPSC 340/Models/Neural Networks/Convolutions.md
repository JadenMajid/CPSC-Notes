---
tags:
  - "#Machine-Learning/Models/Neural-Networks"
---
When training [[Neural Networks]] on images, the individual activations of pixels is almost meaningless. We need to represent the context of the pixel

We can use convolutions in the neighbourhood of a given pixel to show context. 

# Naive Convolutions
The obvious way to do this is to give the [[Mean]] Pixel intensity in the neighborhood, but it has some drawbacks
- Loss of spatial information
- Effectively a blur
	- We lose the crispness of edges

# Gaussian Blur
This controlled blur is like a weighted average focused on closer pixels.