# 1. Introduction to AttentionLola.pdf

Attention in neural network do not imply adding more information but rather removing some

To make attention, we need to analyse relationship between inputs and outputs. To do so, we can use the Jacobian matrix. The Jacobian is computed using partial derivate. Each element of the matrix is :

$$J_{ij} = \frac{\partial \ y_i}{\partial \ x_j}$$

This matrix can be computed using backpropagation but backpropagate output instead of loss

Attention in RNN is natural because it use memory that are updated trough time and update weights of different part, that's attention

If we want to use Jacobian matrix with RNN, the elements become :

$$J_k^t = \left(\frac{\partial y_k^t}{\partial \vec x_1}, \frac{\partial y_k^t}{\partial \vec x_2}, ...\right)$$

Implicit attention is attention that is inherited from the implementation of the model (example : RNN). No much control of it

Explicit attention is attention forced into the model.

Benefit of explicit attention :
- Efficient : no need to access all data
- Scalable 
- Sequential processing of static data

![](attachments/Pasted%20image%2020250102212618.png)

