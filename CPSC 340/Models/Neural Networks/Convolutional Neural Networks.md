---
tags:
  - Machine-Learning/CPSC340
  - Machine-Learning/Models/Neural-Networks
aliases:
  - ConvNet
  - CNN
---
# Description
Convolutional Neural networks are [[Neural Networks]] that are trained on datasets that are transformed with [[Convolutions]]. These datasets are normally images. The Neural Network learns the convolutions required. These convolutions are trained with [[Back Propagation]] and [[Automatic Differentiation]]. 
![[Screenshot 2025-11-26 at 2.49.36 PM.png]]
## Motivations
Consider training a model on a 500x500 pixel image, $d$ for this model is 250,000, if the first layer has $k=10,000$ then $W$ has $2.5$ billion parameters. Convolutional Neural Networks drastically reduce the number of parameters.

## Receptive Fields
As we keep applying convolutions, we increase the side of the receptive fields
> Deeper layers depend on increasingly non local data.


![[Screenshot 2025-11-26 at 2.53.18 PM.png]]
## Hyper Parameters
- number of [[Convolutions|Convolution]] layers
	- number of output channels per convolutional layer
- number of [[Classification]] layers
- 
## Training

### Steps
1. 
## Prediction
### Steps
1. 
---
## Cost
- $n$ training examples
- $m$ testing examples
- $d$ features
### Training
#### Time
$$$$
#### Space
$$$$
---
### Prediction
#### Time
$$$$
#### Space
$$$$
