# Word Embeddings.pdf

Word embeddings is the representation of words that are suitable for model inputs. That is not a token but something more, it do not permit to return to the initial input, it does translate a meaning, not a word.

There is one embedding per token. For words that do not have tokens, we attribute them a default token

## One hot Encoding

Representation of a word using vector of the same size as the vocabulary, full of $0$ but at the position of the index of the token.

ChatGPT says that it is not an embedding (but the course say nothing)

![](attachments/Pasted%20image%2020250104162048.png)

Limitations:
- The dimensions can be big
- Not intuitive
- Do not have meaning (is not really an embedding (chatGPT))

## Get meaning of words

### Count based context vectors

To get meaning, we can use a Term-Document Matrix : a matrix that count the number of term apparition given a document :

![](attachments/Pasted%20image%2020250104172748.png)

In this matrix, if two rows are similar, it means that their context are similar, so, their meaning should be too

To get similarities of contexts, we can use the [cosine similarity](Info_Retrieval_and_VSM.md) between rows

Issue :
- Defining context
- Computing the matrix values

### Neural based context vectors

### Word2Vec

Word2Vec use a model to make the context vector. At each iteration :
1. Run the model
2. Evaluate
3. Backpropagate

#### Continuous Bag of Words (CBOW)

This algorithm learn to predict target $w$ from context $c$ (example, a sentence)

It input the one hot encoding of the context : $x^{(c)}$. and output the one hot encoding of the target : $w^{(w)}$

We define two matrices using the embedding size $n$ and the vocabulary $V$ :
- The input matrix :

$$V \in \Re^{n \times |V|}$$

Where columns ($v_i$) represents word, the $n$-dimensional embedded vector


- The output matrix :

$$U \in \Re^{|V| \times n}$$

Where rows ($u_i$) represents word

Use of this algorithm :
1. Generate one hot vectors for input
2. Learn embedded input vector
3. Average it
4. Get the scores making the dot product of the average and the input matrix
5. $\hat y = Softmax$ the result to get probabilities ($softmax(M, i) = \frac{e_{m_i}}{\sum_{k=1}^M e^{m_k}}$)
6. if $\hat y \neq y =$ the one hot encoding of the target, backpropagate, else, stop 
7. The vectors at hidden layers are the word embeddings

Problem:
- the update is proportional to vocabulary size

Solution: update only a random subset of words

improvement : use of negative sampling (change the loss function) from :

$$J_{t,j}(\theta) = -u^T_{cute}v_{cat} + log \sum_{w\in V} exp(u^T_wv_{cat})$$

to :

$$J_{t,j}(\theta) = -log \ \sigma (u^T_{cute}v_{cat}) - \sum_{w\in \{w_{i1}, w_{i2}, ..., w_{iK}\}} log \ \sigma(-u^T_wv_{cat})$$

#### SG

SG predict context words given target word using window of size $m$ as context

(see calculus in slides)

Influence of widow size :
- Larger window size : Topical similarity
- Smaller window size : Syntactic similarity

#### ChatGPT

**CBOW :**

- Predicts the **target word** given its **context words**.
- Aggregates the embeddings of the context words and uses them to predict the central word.
- Example: In the sentence "The cat sat on the mat," for the target word "sat," the context words would be ["The," "cat," "on," "the," "mat"]. The model uses these words to predict "sat."
- **Objective**: Maximize P(wt∣context)P(w_t | context)P(wt​∣context), where wtw_twt​ is the target word, and "context" represents the surrounding words.

**Skip-gram (SG) :**

- Predicts the **context words** given the **target word**.
- Focuses on the target word and tries to predict which words are likely to appear near it in the sentence.
- Example: For the target word "sat," the model predicts the surrounding context words ["The," "cat," "on," "the," "mat"].
- **Objective**: Maximize P(context∣wt)P(context | w_t)P(context∣wt​), where wtw_twt​ is the target word.

**2. Key Differences**

| **Feature**          | **CBOW**                                              | **Skip-gram (SG)**                                             |
| -------------------- | ----------------------------------------------------- | -------------------------------------------------------------- |
| **Prediction Task**  | Predict the target word from context words            | Predict context words from the target word                     |
| **Focus**            | Prioritizes frequent words (smoothed by averaging)    | Works better with rare words (focuses on single pairs)         |
| **Training Speed**   | Faster (computes an average of context embeddings)    | Slower (processes each context-target pair separately)         |
| **Accuracy**         | May perform better for frequent words                 | Handles rare words and infrequent contexts better              |
| **Context Size**     | Uses all surrounding context words (a "bag" of words) | Treats each context-target pair independently                  |
| **Complexity**       | Less computationally expensive                        | More computationally intensive                                 |
| **Example Use Case** | Useful for general tasks with balanced corpora        | Useful for capturing rare word semantics and specific contexts |

---

**3. Advantages and Disadvantages**

**CBOW:**

**Advantages:**

- Faster to train due to the averaging of context words.
- Suitable for large datasets with frequent words.

**Disadvantages:**

- Averages context embeddings, potentially losing information about word order or specific dependencies.
- May struggle to represent rare words accurately since it tends to focus more on frequent words.

**Skip-gram:**

**Advantages:**

- Handles rare words well because it creates separate context-target pairs.
- Captures more specific word relationships and fine-grained semantics.

**Disadvantages:**

- Slower to train because it generates multiple predictions for each target word (one for each context word).
- Requires more data to effectively learn embeddings for frequent and infrequent words.

## GloVe

(i don't think we must know that, to do if time)