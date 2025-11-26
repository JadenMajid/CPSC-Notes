tags:
  - "Machine-Learning/CPSC340"
-# Description
Neural network regression uses one or more hidden layers to learn a nonlinear mapping from inputs to a continuous output. A common setup is a single hidden layer with activation $h(\cdot)$ followed by a linear readout $v$ so that $\hat{y}_i = v^\top h(W x_i)$.

## Hyper Parameters
- Hidden width $h$, activation choice (ReLU, tanh, etc.).
- Loss (squared error is standard) and regularization strength.
- Optimizer settings: learning rate, batch size, number of epochs $E$.

## Training

### Steps
1. Initialize the weights $W$ and readout vector $v$ (plus biases) randomly.
2. Loop over epochs: run forward passes to compute predictions $\hat{y}_i$ and the squared-error loss $f(W,v) = \tfrac{1}{2}\sum_i (\hat{y}_i - y_i)^2$.
3. Backpropagate gradients through the hidden layer and update parameters via SGD/Adam/etc.
4. Monitor validation loss / early stopping criteria.

## Prediction
### Steps
1. Perform a forward pass to calculate $\hat{y}_i = v^\top h(W x_i)$.
2. Return the scalar output (optionally with confidence intervals if ensembling or Bayesian methods are used).

## Cost
- $n$ examples, input dimension $d$, $h$ hidden units, $k=1$ output.
- Training with backpropagation across $E$ epochs costs $$O(E\,n\,(dh + h))$$ time and $$O(dh + h)$$ space for the weights.
- Prediction per example is $$O(dh + h)$$ because it requires one forward pass through the hidden layer and output node.
