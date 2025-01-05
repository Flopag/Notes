# Contextual embeddings.pdf

An embedding is the representation of the meaning of a word

Contextual embeddings is a dynamic embedding where each word embedding depends on tis surrounding words

A static embedding is an embedding that is pre-trained. So, it represent the context of the pretrained phase

Dynamic embeddings is an embedding that can change and influence each other. So, it represent the context of the pretrained phase AND the context of the current data

## Bi-LSTM

Bi-LSTM permits to produce contextual embeddings by mixing left and right static embeddings. The more the distance between two words there are, the less effect to each other there are. So, word encodings will differ depending on the context :

![](attachments/Pasted%20image%2020250104114658.png)

## ELMo

ELMo uses Bi-LSTM to learn contextual embeddings and takes static character embeddings as input. So, it is a character based model and not a word based model

pro/con of character based model:
- pros :
	- handle out of vocabulary words
	- smaller
- Cons :
	- less powerfull
	- similar words are not always near in signification


![](attachments/Pasted%20image%2020250104120814.png)

## BERT

BERT learns contextual embeddings with a bidirectional transformer. The transformer is a stack of encoders. There is no vanishing memory as RNN and LSTM because the whole input sequence is ingested at once. This parallelisation permit faster training and larger model.

There is a multi headed self-attention that pay attention to:
- Coreference
- Syntactic relationship
- Meaning
- Topical relationship

(see functionning of head in slides)

WordPiece embeddings : The tokenisation of this model is made word by word. That permit ease of asian languages

Positional embedding : permit to encode position using $sin$ and $cos$. This is useful in transformers because transformers process inputs in parallel, so, it do not have naturally the position of the word

The input of the transformer is a combination of WordPiece and Positional embedding