# LLaMA_Archi.pdf

## Normalization

In neural networks, the modification of a parameter at a layer will propagates to other layers. It will lead to shift in the distributions at the inputs of the layers, especially for architecture with many layers

We can use normalization to stabilize these inputs

### BatchNorm

BatchNormal normalize activations of a layer within a mini-batch during training. This is commonly applied to intermediate layers

It :
- stabilize training by reducing internal covariate shift and improve convergence
- make gradient independent on parameter values, so, hight learning rates
- Regularize and reduce the need of dropout

It works by subtracting the mini-batch mean and dividing by the mini-batch standard deviation. Parameters are learnable to allow the model to adjust the normalization

### LayerNorm

LayerNorm normalize activations across entire layer, independently for each sample in the batch

This is suitable for online inference

![](attachments/Pasted%20image%2020250105113215.png)

### Root Mean Square Normalization (RMSNorm)

It recentre and rescale the invariance property. The recentering reduces sensitivity to shift on inputs and weights. Rescaling stabilizes the output when inputs and weights are randomly scaled

RMSNorm simplifies LayerNorm by discarding the mean. It cost the recentering invariance efforded by mean but it is not fundamental to LayerNorm sucess

## positional embedding ([see](Contextual_embeddings.md))

Self-attention (transformers) enable parallel processing of sequences but at cost of positional information

The positional embedding is computed using $sin$ and $cos$ :

$$PE_{(pos, 2i)} = \sin \left(\frac {pos}{10000^{\frac {2i} d}}\right)$$

$$PE_{(pos, 2i +1)} = \cos \left(\frac {pos}{10000^{\frac {2i} d}}\right)$$


![](attachments/Pasted%20image%2020250105145304.png)

## Relative Positional Embedding

Words nearer to each other are likely to be more related, so, use of relative position instead. This embedding represent the distance between two words used in attention calculation as vectors. These vectors are grouped in a pairwise embedding matrix where rows represents words and columns represents the positional distance of the word to all other words

This is hard to compute and must guarantee that positional embeddings of already generated words do not change (that not the case using relative positions)

## Rotary Positional Embeddings (RoPE)

Encode absolute position $m$ of tokens through a rotation matrix and incorporates relative position dependency in self-attention formulation

Idea : embed token's position by rotating queries ($Q$) and keys ($K$), the rotation is different at each position

The rotation can be done using the Euler representation of a complex number :

$$\left(\begin{matrix} \cos m\theta & -\sin m\theta \\ \sin m\theta & \cos m\theta \end{matrix}\right)$$

We can use a very naïve illustration on general vectors (ignoring k, q, embeddings, ...) :

The idea is to rotate tokens by a multiple $m$ of $\theta$ where $m$ depends on the token position in the sentence

Adding more tokens at the beginning or the end of a the sentence do not change the token positional embedding vector since its position is unchanged. This is easier to cache

![](attachments/Pasted%20image%2020250105154720.png)

As long as distance between two word is preserved, the dot product is unchanged regardless of token added at the beginning or the end of the sentence :

![](attachments/Pasted%20image%2020250105154931.png)

## KV Cache

During inference (prediction) at time $T$, only the last output token at time $T-1$ is required, all token from time $t < T-1$ are recalculated for no reason (since we know them).

KV cache store already computed keys ($K$) and values ($V$)

Example :

without KV cache :

![](attachments/Pasted%20image%2020250105155942.png)

With KV cache :

![](attachments/Pasted%20image%2020250105160000.png)

(stop at slide 49)