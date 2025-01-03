# MT Evaluation.pdf

## Evaluation

Evaluation aim to determine how good is a machine translation system. There is two kind of translation quality :
- Adequacy : is the meaning kept ?
- Fluency : is the grammar correct ?

Human evaluation : not so good because human disagree between them.

We want to have a automatic metric. Here are some metric criterion :
- Cost efficient
- Adaptable
- Relevant
- Consistent
- Correct

### Precision-Recall

Precision recall metric is based on gold-standard (reference). It compute the precision and the recall and congregates them in the f-measure. It only compare words with the reference. If a word is not in the reference, the score decreases

Problem: it do not look at the meaning of the sentence, so, it is not correct

### Word Error Rate (WER)

WER metric look to the number of step to transform the output into the gold standard (reference).

To compute the step cost, it depend on the type of step (the cost is associated to the type) : Substitution, insertion, deletion.

![](attachments/Pasted%20image%2020250102174124.png)

### BLEU

BLEU is computed using :

$$\log BLEU = min\left(1-\frac r c, 0\right) + \sum_{n=1}^N w_n \log p_n$$

It penalizes too short translations using $min\left(1-\frac r c, 0\right)$ where $r$ is the reference length and $c$ the output length

It measure the N-gram precision using $\sum_{n=1}^N w_n \log p_n$ where $N$ is the precision ($N=4$ is BLEU-4)

Simplified version of BLEU-4 :

$$BLEU = \min\left(1, \frac{output length}{reference length}\right) \left(\prod_{i=1}^4 precision_i\right)^{\frac 1 4}$$

![](attachments/Pasted%20image%2020250102181200.png)

The limitation is that it overlooks semantics. The meaning can be false :

![](attachments/Pasted%20image%2020250102181337.png)