# Info Retrieval and VSM.pdf

## Document scoring

A document should be ranked higher if it contains more terms that match the input query. To do so, we assign a score from 0 to 1.

### bag of Word Model

Document are represented as collection of independent terms. 

Example:

```
d1 = {brunch, liège, brunch, liège, brunch, brunch, liège, belgium, antwerp, beer, food, drink, eat, gastro}
```

### Jaccard Coefficient

The jaccard index represent the overlapping of two sets. We compute it counting the number of element that appear in the two sets divided by the number of elements in the sets.

Limitations:
- Do not take occurrence frequency into account
- Does not normalize the document lengths (so, longer documents will be penalized)

## Computing Document-Query Matching Scores

To get more information from the documents, we will use vector space model (VSM) that count the number of occurrence of a world in the document and link it to this word.

So, the word is the dimension and the occurrence the value.

Example:

![](attachments/Pasted%20image%2020241227113703.png)

### Proximity Metrics

The Euclidean distance permit to measure the distance between two vectors :

For two vectors $\vec x = (x_1, x_2, ..., x_n)$ and $\vec y = (y_1, y_2, ..., y_n)$ , the Euclidean distance between them is:

$$d_{euc} = \sqrt{\sum_{i=1}^n ( x_i - y_i )^2}$$

Limitations:
- Euclidean distance is large for vectors of different size (so, longer documents are penalized)

### Angular Measures

Instead of computing the Distance between two vectors, that will penalize long vectors, we compute the angle between two vectors. So, we only look where the vector points and not what value it has. That don't penalize big vectors.

To do so, we compute the dot product between the two vectors:

$$x \bullet y = \sum_{i=1}^n x_iy_i = ||x|| \ ||y|| \cos\theta$$

This can be transformed to get the angle $\theta$ :

$$\theta = \cos^{-1} {\frac {\sum_{i=1}^n x_iy_i}{||x|| \ ||y||}}$$