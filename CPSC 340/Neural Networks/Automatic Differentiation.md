---
tags:
  - machine-learning/CPSC340
---
# Description
Algorithm is still [[Stochastic Gradient Descent]], but we have an algorithm that finds the gradient of the loss function automatically. Computing the gradient has the same cost as computing the loss(same [[Big O]]). Closely related with [[Back Propagation]].

There are two types, reverse mode, and forward mode. 340 will focus on reverse mode.

![[Screenshot 2025-11-24 at 1.05.38 PM.png]]
# Reverse Mode
Reverse mode is the default. Recursively rewrite every instance as an application of the [[Chain Rule]].

## Steps

### Forward Pass
We first compute and store the intermediary steps for calculating the value of the our loss function. We store the values found because they are reused in the backwards pass step.
### Backwards Pass
The values from the forward pass help us to find the values of each relevant gradient.

![[Screenshot 2025-11-24 at 1.24.49 PM.png]]

## Multiple Parameters
Often in Machine learning, we have more than one parameter. In order to calculate this we can use a [[Directed Acyclic Graph]]. 
- Root nodes are parameters
- Intermediate nodes are computed parameters
- leaf nodes are function values
![[Screenshot 2025-11-24 at 1.28.54 PM.png]]
## Skip Connections

### Resnet Blocks
Residual Network blocks are a implementation of skip blocks that are very common now.
# Examples
## Simple Example
Consider the following
$$f(x)=10\log(1+\exp(-2x))$$
we can rewrite f(x) as the following
$$f(x)=f_5(f_4(f_3(f_2(f_1(x)))))$$
$$f_1(z)=-2z,f_2(z)=\exp(z), f_3(z)=1+z,f_4(z)=\log(z),f_5(z)=10z$$
And to find $f'(x)$, we can use the gradients of the composition functions recursively 
$$f'_1(z)=-2,f'_2(z)=\exp(z),f'_3(z)=z,f'_4(z)=\frac{1}{z},f'_5(z)=10$$
$$f'(x)=f'_5(f_4(f_3(f_2(f_1(x)))))*f'_4(f_3(f_2(f_1(x))))*f'_3(f_2(f_1(x))*f'_2(f_1(x))*f'_1(x)$$

## Deep Learning Example

## Andrej Karpathy example(DAG)
### Nodes
![[Screenshot 2025-11-24 at 1.31.09 PM.png]]
### Forward Pass
![[Screenshot 2025-11-24 at 1.29.18 PM.png]]
### Backwards Pass
#### Single Dimension Operators
![[Screenshot 2025-11-24 at 1.35.01 PM.png]]
#### Multi Dimension Operators

![[Screenshot 2025-11-24 at 1.38.17 PM.png]]