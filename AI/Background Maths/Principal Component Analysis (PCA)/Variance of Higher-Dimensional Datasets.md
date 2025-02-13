#MachineLearning #PCA
#### By: Coursera - Mathematics for Machine Learning: PCA Week 1
---
The intuitive definition of the ***[[Variance of 1D Datasets|Variance]]*** we explored doesn't really work in high dimensions, and *squaring* vectors is not really define.

In the example of a 2d dataset, we may be able to compute the ***variance*** of each dimension, but we may also be interested in the relationship between this variables. This is where the concept of a ***covariance*** between these components comes into play. The ***covariance*** between a dimension $x$ and $y$ is defined as follows:
$$
\text{cov}[x,y] = \text{E}[(x-\mu_{x})(y-\mu_{y})]
$$$\text{Where:}$
$$
\mu_{x}=\text{E}[x]
$$