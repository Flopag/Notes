# TFIDF.pdf

## Term-Frequency Inverse-Document Frequency (TFIDF)

- Term-frequency : The more mentions of a query there is the more relevant document is
	- Drawback: unimportant terms will grow the score
- Inverse-Document Frequency : The less mentions of a query there is in all documents the more relevant term is

The tfidf is the combination of these two gives the weight to a term $t$ in document $d$:

$$tf-idf_{t,d} = tf_{t,d} \times idf_t = tf_{t,d} \times \log \frac{N}{df_t}$$

Where:
- $tf_{t,d}$ is the number of occurrence of term $t$ in document $d$ (term frequency)
- $df_t$ is the number of document that contains $t$
- $idf_t = \log \frac{N}{df_t}$ is the inverse-document frequency
- $N$ is the number of documents of the collection

We can read this as: the weight of term $t$ in document $d$ is the occurrence of $t$ in $d$ times the logarithm of the number of document divided by the number of occurrence of $t$ in all documents