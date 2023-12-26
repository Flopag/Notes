# Chapter 2: Classification and regression trees

> What is the computational complexity of the learning algorithm?

$$O(nN\log N)$$

Where:
- $n$ is the number of attributes
- $N$ is the number of samples

> How do we handle (continuous) numerical input variables?

We descretize the attribute by searching the biggest reduction of impurity

> Explain the optimal splitting algorithm

To get the best split, we must compare all attributes by computing the reduction of impurity of each of them and taking the biggest

> What are the 2-3 main changes to make to implement regression tree learning with respect to decision tree learning?

- The prediction of a leaf is the average of the outputs
- The impurity become the variance of the output given the learning sample

> How to adapt this approach to general loss-functions $l(\bullet , \bullet)$?

TBD

> Discuss theoretical asymptotic ($N \rightarrow \infty$) properties?

If the number of sample is near infinite, the tree will never be able to grow (if we don't limits the depth)

> Discuss computational complexity and interpretability

The tree permit an obvious interpretability and to see the usefulness of each attributes