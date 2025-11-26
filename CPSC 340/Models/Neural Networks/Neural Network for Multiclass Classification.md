---
tags:
  - "Machine-Learning/CPSC340"
---
# Description
Fully connected neural networks for multiclass classification map an input vector $x \in \mathbb{R}^d$ through one or more hidden layers before producing $k$ logits $o_{ic}$ at the output layer. The final prediction is obtained by taking the argmax of the logits or by normalizing them with [[Softmax]] to obtain class probabilities.

## Hyper Parameters
- Hidden widths $h_1,\dots,h_L$ and activation function $h(\cdot)$.
- Regularization / dropout strength.
- Optimization settings (learning rate, batch size, number of epochs $E$).

## Training

### Steps
1. Initialize weights $W^{(\ell)}$ and biases $b^{(\ell)}$ for every layer.
2. For each epoch, run forward propagation to compute logits $o_{ic}$ and the cross-entropy loss.
3. Backpropagate the gradients through each layer and update the parameters with SGD/Adam/etc.
4. Repeat until convergence, patience runs out, or validation loss stops improving.

## Prediction

### Steps
1. Run a forward pass to obtain the logits vector $o_i$ for the query point.
2. Return $\operatorname{argmax}_c o_{ic}$ or the softmax-normalized probabilities.

## Cost
- $n$ training examples, $m$ test points, $d$ features.
- Hidden size symbolized collectively as $H = \sum_{\ell=0}^{L-1} k_\ell k_{\ell+1}$ for $k_0=d$ and $k_L=k$ outputs.
### Training
Time: $$O(E\,n\,(dh + hk))$$ for a single hidden layer with $h$ units (generalizes to $$O(E\,n\,H)$$ for multiple layers).  
Space: $$O(H)$$ to store parameters plus $$O(\sum_{\ell} k_\ell)$$ for activations during backprop.
### Prediction
Time: $$O(dh + hk)$$ per example (or $$O(H)$$ generally).  
Space: $$O(h + k)$$ to keep intermediate activations.

## Cost
- $n$ examples, $d$ features, $h$ hidden units, $k$ output classes.
- Training with backpropagation across $E$ epochs takes $$O\left(E\,n\,(dh + hk)\right)$$ time because each mini-batch requires two matrix multiplications (forward + backward) per layer pair.
- Prediction per example costs $$O(dh + hk)$$ time and $$O(h + k)$$ working memory to hold activations and logits before the [[Softmax]].
- Parameter storage for the weight matrices and biases is $$O(dh + hk)$$.