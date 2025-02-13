#MachineLearning #PCA
#### By: Coursera - Mathematics for Machine Learning: PCA Week 1
---

Let's analyze the following datasets, as well as their ***[[Mean of a Dataset|expected values]]***.

```desmos-graph
left=-4; right=14;
top=2; bottom=0;
---
f(x)=1
(-1,1)|red
(3,1)|red
(7,1)|red
(1,1)|blue
(2,1)|blue
(4,1)|blue
(5,1)|blue
```
Where:
$$
D_{1}=\{ 1,2,4,5 \}, \text{E}[D_{1}]=3
$$
$$
D_{2}=\{ -1,3,7 \}, \text{E}[D_{2}]=3
$$
We observe how both sets have the same ***expected value***, even though one has points which are more spread apart from each other. Here's where the ***variance*** of the data comes in. 

The ***variance*** refers to the average square distance of each point of the *dataset* to the mean. In other words, how far away each point tends to be from the *mean*. For each *dataset*:
$$
D_{1}: \frac{(1-3)^2+(2-3)^2+(4-3)^2+(5-3)^2}{4}=\frac{10}{4}
$$
$$
D_{2}: \frac{(-1-3)^2+(3-3)^2+(7-3)^2}{3}=\frac{32}{3}
$$
Generalized, for a dataset $\{ x_{1},\dots,x_{n} \} =:X$.
$$
Var[X]=\frac{1}{n}\sum^n_{n=1}(x_{n}-\mu)^2
$$
$\text{Where:}$
$$
\mu=E[X]
$$
From here, we observe how the ***variance*** can 


---