# Text Classification.pdf

The goal of classification is to find the best class for a given document

## Features selection

Feature selection (FS) : feature are recognizable and we can directly read and interpret them

**Linguistic Methods** : Identify features based on linguistic information (for example: only use adjectives)

**Statical Methods** : Identify features based on the occurrence frequency

### Mutual information

Mutual information is the amount of information that the term contains about the class :

$$I(U;C) = \sum_{e_t \in \{1,0\}} \sum_{e_c \in \{1,0\}} P(U = e_t, C=e_c) \log_2 \frac{P(U=e_t, C=e_c)}{P(U=e_t)P(C=e_c)}$$

Where:
- $U = 1$ if a given document contains the term $t$, else $=0$
- $C = 1$ if a document $d$ belongs to the class $1$, else $=0$
- $e_t$ : is document containing the term $t$ ?
- $e_d$ : is document $d$ in class?

The equation can be expressed as :

$$I(U;C) = \frac {N_{11}}{N} \log_2 \frac{NN_{11}}{N_1N_1} + \frac {N_{01}}{N} \log_2 \frac{NN_{01}}{N_0N_1} + \frac {N_{10}}{N} \log_2 \frac{NN_{10}}{N_1N_0} + \frac {N_{00}}{N} \log_2 \frac{NN_{00}}{N_0N_0}$$

Where:
- $N_{xy}$ is the number of documents having values $e_t=x$ and $e_c=y$
	- $N_{11}$ is the number of documents that contains $t$ and is in class
	- $N_{10}$ is the number of documents that contains $t$ and is not in class
	- $N_{01}$ is the number of documents that do not contains $t$ and is in class
	- $N_{00}$ is the number of documents that do not contains $t$ and is not in class
- $N_x$ is the number of documents having value $e_t = c$
	- $N_1 = N_{10} + N_{11}$ is the number of documents that contains $t$
	- $N_0 = N_{00} + N_{01}$ is the number of documents that do not contains $t$
- $N$ is the number of documents

### Chi-Squared

Chi-squared, $\chi^2$ , is used to estimate the independence between events. The more the value is big, the more the dependence is big

Two events, $A$ and $B$, are independent if $P(AB) = P(A)P(B)$

We consider $A$ as the occurrence of a term and $B$ as the occurrence of a class. The independence between $A$ and $B$ become (assuming that $A$ and $B$ are independent) :

$$\chi^2(D, t, c) = \sum_{e_t \in \{0,1\}}\sum_{e_c \in \{0,1\}} \frac{(N_{e_te_c} - E_{e_te_c})^2}{E_{e_te_c}}$$

Where:
- $N_{xy}$ is the same as the mutual information
- $E_{xy}$ is the expected frequency of $e_t = x$ and $e_c = y$
	- $E_{11}$ is the expected frequency of $t$ of documents of class
	- $E_{10}$ is the expected frequency of $t$ of documents not of class
	- $E_{01}$ is the expected frequency of not $t$ of documents of class
	- $E_{00}$ is the expected frequency of not $t$ of documents not of class

$E_{xy}$ is computed using the two previously random variables :

$$E_{x,y} = P(A = x)P(B = y)\times D$$

In our case, $D = N$ :

$$E_{xy} = P(e_t = x)P(e_c = y) \times N$$

we can thus compute the different values of $E_{xy}$ :
- $E_{11} = \frac{N_{1,1} + N_{1,0}}{N} \times \frac{N_{1,1} + N_{0,1}}{N} \times N$ 
- $E_{10} = \frac{N_{1,1} + N_{1,0}}{N} \times \frac{N_{1,0} + N_{0,0}}{N} \times N$
- $E_{01} = \frac{N_{0,1} + N_{0,0}}{N} \times \frac{N_{1,1} + N_{0,1}}{N} \times N$
- $E_{00} = \frac{N_{0,1} + N_{0,0}}{N} \times \frac{N_{1,0} + N_{0,0}}{N} \times N$

### Multinomial Naïve Bayes

Here, we talk about multinomial variant because Bernoulli model is less used

Naive-Bayes (NB) is a probabilistic classifier. It predict the best class for a document based on the probability that its terms belongs to the class

It is called naive because it makes several assumptions to facilitate the probability computations. But is works in practice

These assumption are :
- Each text document is generated by a mixture model
- There is a one to one mapping between each mixture component and the document class

A mixture model is a model that models data using several statistical distributions.

These distribution are called mixture component

(see slides to see formulas)

The probability of a document $d$ to be assigned to a class $c$ ($P(c|d)$) is proportional to the probability of a document being in class and the probability of a term occurring in document of class

To know witch class is the best for document $d$, we compute the maximum a posteriori (MAP) : 

$$c_{map} = \arg \max_{c} P(c|d)$$

after some simplification (Bayes then drop of denominator) : 

$$c_{map} = \arg \max_c P(d|c) \ P(c)$$

After some more simplification (see slides) :

$$c_{map} = \arg\max_c \hat P(c) \prod_{1\leq k \leq n_d} \hat P(t_k|c)$$

$\hat P(c) = \frac {N_c} N$ is computed using MLE

$\hat P(t|c) = \frac {T_{ct}}{\sum_{t'\in V} T_{ct'}}$ is computed as the relative frequency of term $t$ appearing in documents of class $c$. Where $T_{ct}$ is the number of times term $t$ occurs in documents of class $c$

Naive-Bayes is suitable for text classification because it do good comparison between classes. It do not compute good absolute values but we don't care, we want the comparison between values

It is suitable because :
- works well when several terms jointly contribute to the classification decision
- Robust to noise
- highly efficient
- Easy implementation