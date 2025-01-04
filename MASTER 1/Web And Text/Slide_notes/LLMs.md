# FalconLamaFin 2023-11-29 07_49_12.pdf

Most LLMs are based on transformers with stack of encoder and decoder.

encoder generates embeddings from input token

Decoder generates output tokens from input embeddings

These implement self-attention to learn relationships between words

## Llama

Specificities:
- Activation function is SwiGlu (combination of Swish and GLU) instead of [ReLu](RNN.md)
	- improves gradient flow, reduce training time
- Self-attention
- Rotary Positional Embedding (RoPe) not transformer like embedding
	- better handling of longer sequences, better generalisation over unseen data
- Root mean squared layer normalization (RMSNorms)

## Llama 2

Specificities:
- Use Flash attention instead of self-attention
	- reduce complexity
- Multi-query attention instead of single query
	- can generate multiple outputs for a single input
- Multi-head attention (transformer)
- Parallelism for training

## Falcon

Specificities :
- Decoder-only
- Multi-query attention
- Flash attention
- RoPe
- LayerNorm

![](attachments/Pasted%20image%2020250104205554.png)

## Evaluation metrics and dataset

(just a list of technologies)

## Fine-Tuning (using LoRa)

This permit to adapt pre-train LLM on a specific domain by adapting parameters on smaller domains datasets

Low-ranked adaptation (LoRa) can be used. It uses low rank approximation methods that inject low-rank matrix decomposition layer

How it works?
1. Freeze pre-trained model weights
2. Fine tune with a smaller model on a specific task
3. Inject LoRA model un specific LLM layer

In LoRA, large $\Delta W$ matrix is represented by two smaller matrices $A$ and $B$ where $AB = \Delta W$

$A$ and $B$ have a smaller size than $\Delta W$, so, it store less information, but, fine-tuning do not require fine-tuning all weights anyway

![](attachments/Pasted%20image%2020250104210428.png)

I can generates absurd contents (hallucinations) due to bias in inputs, limitation in the model understanding or language complexities

Three type of hallucination :
- Input conflicting : generates deviated responds to user inputs
- Context conflicting : make contradictions with itself
- Fact conflicting : contradict facts

hallucination reduction (just a list of methods)