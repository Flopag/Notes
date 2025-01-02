# Recurrent Neural Networks (RNN).pdf

Recurrent neural network are neural networks where the neurones are trained using back propagation. So, for each input given to the RNN, the hidden states are updated.

## Layers

RNN are composed of tree types of layers:
- Input layer : takes text (in our case)
- Output layer : gives text or machine code (depend on what we want)
- Hidden layers : Layers that process input and construct the output

Given the number of Inputs and Outputs, there are multiple types of RNN:
- One to one : one input for one output (example: image classification)
- One to many : One input for multiple output (example: image descriptor)
- Many to one : multiple inputs for one output (example : text classification)
- Many to many : multiple inputs for multiple outputs (example : text descriptor)

![](attachments/Pasted%20image%2020241230145242.png)

## Propagation

For each input sequence $x$, the states are updated using:

$$h_t = f_W(h_{t-1}, x_t)$$

Where:
- $h_t$ is the new state
- $h_{t-1}$ is the previous state
- $x_t$ is the current input (given at time $t$)
- $f_W$ is a function that takes two inputs

![](attachments/Pasted%20image%2020241230150635.png)

### A basic RNN

Our basic RNN is composed of a single hidden vector $h$.

We will use :

$$f_W(h_{t-1}, x_t) = tanh(W_{hh}h_{t-1} + W_{xh}x_t)$$

Where: $W_{hh}$ and $W_{xh}$ are two weights from two matrices (I don't know to what they corresponds) 

The output will be given using :

$$y_t = W_{hy}h_t$$

Where $W_{hy}$ is a weight from a matrix

![](attachments/Pasted%20image%2020241230150740.png)

Many-to-One :

![](attachments/Pasted%20image%2020241230155905.png)

One-to-Many :

![](attachments/Pasted%20image%2020241230155925.png)

## Sequence-to-Sequence architecture (Seq2Sec)

The inputs and outputs are many to many and the architecture combines many-to-many and one-to-many

The encoding process (learning) use the many-to-one architecture :

![](attachments/Pasted%20image%2020241230160330.png)

The decoding process (generating) use the one-to-many architecture :

![](attachments/Pasted%20image%2020241230160444.png)

## One-hot encoding

A one-hot vector is a vector full of $0$ but at position of the index of the target

![](attachments/Pasted%20image%2020241230161227.png)

Example of application :

![](attachments/Pasted%20image%2020241230161410.png)

In learning phase :
1. Compute the confidence of next letter
2. If the right guess (green in example) is not the most confident, back propagate to have better guess

This is very long to compute, so, we use truncated back propagation : Use back propagation batch (small par of the dataset) by batch

Problem :
- Using tanh and signmoid tend to give null gradient for small values. So,  small values do not contribute to learning -> vanishing gradients
- Matrix are multiplied repeatedly, so, some matrix values are big -> exploding gradients

### Vanishing gradients

#### What is vanishing gradients?

We have seen a simple RNN cell, with the following update formula :

$$h_t = tanh(W_{hh}h_{t-1} + W_{xh}x_t) = tanh\left(W \left(

\begin{matrix}

h_{t-1}\\
x_t

\end{matrix}

\right)\right)$$

Where $W = \left(\begin{matrix} W_{hh} & W_{hx}\end{matrix}\right)$

![](attachments/Pasted%20image%2020241230210204.png)

In each back propagation, we multiply the weight matrix.

For multiple cell, this is done multiple time and the gradient can vanished by multiplication of divisions :

![](attachments/Pasted%20image%2020241230210339.png)



#### How to fix it ?

- Use of another activation function as ReLU
- Use of an architecture using memory as:
	- LSTM
	- GRU

#### LSTM (to undertand more)

LSTM have two hidden state per time step instead of one and use four gates computed using the inputs : 
- $i$ (input) : how much information to input in cell
- $f$ (forget) : how much to forget/discard from previous time step
- $o$ (output) : how much to output
- $g$ : how much to write to cell

$$\left(
\begin{matrix}i \\ f \\ o \\ g\end{matrix}
\right)

= 

\left(
\begin{matrix}\sigma \\ \sigma \\ \sigma \\ tanh \end{matrix}
\right)

W

\left(

\begin{matrix}

h_{t-1} \\ x_t

\end{matrix}
\right)$$

$$c_t = f \bullet c_{t-1} + i \bullet g$$

$$h_t = o \bullet tanh(c_t)$$

![](attachments/Pasted%20image%2020241230221833.png)