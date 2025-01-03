# Lecture_Intro MT.pdf

The aim of machine translation (MT) is to translate a text from a language to another

## Rule based MT

Rule base MT do not use machine/deep learning, statistic but only translate using bilingual dictionaries

## Statistical MT (SMT)

SMT leans to find the sentence in the destination language ($y$) that best correspond to the sentence in the source language ($x$). This can be written as :

$$y = argmax_y \ P(y|x) = argmax_y \ P(x|y) \ P(y)$$

SMT are separated in two components : translation model and language model.  

### Translation model

The translation model computes $P(x|y)$ (how words, phrases should be translated), permits to make good translations.

This model learn using large corpora (as rosetta stone) or human-translated texts.

The learning process introduce an additional parameter: the alignment $a$. The target probability become :

$$P(x, a|y)$$

The alignment aim to reorder words after translation. It is done because words do not have the same order in the different languages.

![](attachments/Pasted%20image%2020250101180500.png)

The alignments can also transform word that must be separated (one to many) in multiple one, and reversely (many to one).

### Language model

The language model computes $P(y)$ (prediction of the next word), permits to maje good sentences.

### Decoding (computation of $argmax_y$)

Brute force solution : Enumerate al $y$ and choose the one with greater probability. Too expensive

Heuristics search algorithm : discard hypotheses with low probability. First, construct a tree of possibilities and then we find the best path :

![](attachments/Pasted%20image%2020250102133358.png)

## Neural Machine Translation (NMT)

Largely outperform SMT performance

Basic idea : Single neural network architecture for machine translation. This architecture is composed of two recural neural networks (RNN), one is the encoder and the other is the decoder. This architecture is named Seq2seq

![](attachments/Pasted%20image%2020250103162529.png)

### Encoder

In the encoding, we give embeddings and not words as inputs

![](attachments/Pasted%20image%2020250102145752.png)

### Decoder

The decoder is initialized with start symbol then the encoding of the source. Then, it outputs the probability of the next word

![](attachments/Pasted%20image%2020250102145929.png)

To construct the full output, give the previous output as input :

![](attachments/Pasted%20image%2020250102150051.png)

Problem, the argmax is computed on each word predictions. This argmax is different of the entire sentence argmax. Solution, beam decoding :

#### Beam decoding

Principle : keep track of top $k$ possible partial translations (hypotheses). $k$ is called the beam size or the search space. The more $k$ is great, the more hypothesis are made.

The hypothesis score are computed using log probability

Here is an example with $k = 2$ :

![](attachments/Pasted%20image%2020250102162604.png)

We stop expending the hypotheses when the decoder reach the stopping criterion :
- We reach the limit of time steps $T$
- We have generated $n$ possible hypotheses (hypotheses that have reach the END token)

We collect the hypothesis with the higher score but we penalize long hypothesis (i don't know why)

### For machine translation

We train the model using parallel corpus:
1. Give source sentence
2. Make prediction while computing the loss
3. Back propagate sing the loss

![](attachments/Pasted%20image%2020250102150448.png)
