# Lecture 2 2020 Attention for MT.pdf

RNN can perform machine translation but the gradients can vanish (see [RNN](RNN.md)). So we use improved version of RNN as LSTM and GRU. These models decide if an input is important or not to be propagated.

These are designed to deal with vanishing gradients but are bad for very long sentences. 

So, we can use attention to focus only on the most important part of a sentence :

![](attachments/Pasted%20image%2020250103162751.png)

The attention is modelized by a vector of weights. The vector shows the importance of each word. This vector creates shortcuts between context vector (encode of alignment between input and output) and inputs. The context vector indicates on which input to focus

fRNN reads input sequence in order and bRNN reads input sequence in reverse. BiRNN do both.

For a given word $x_j$ :

$$h_j = \left[\overrightarrow {h_j^T};\overleftarrow {h_j^T}\right]^T$$

Where :
- $\overrightarrow {h_j^T}$ is the forward hidden states
- $\overleftarrow {h_j^T}$ is the backward hidden states

The context vector is :

$$c_i = \sum_{j=1}^{T_x} \alpha_{ij}h_j$$

Where:
- $\alpha$ is the weight matrix
- $h$ is the hidden state vector

The weights are computed using a alignment model