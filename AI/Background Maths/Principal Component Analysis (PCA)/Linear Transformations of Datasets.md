#MachineLearning #PCA
#### By: Coursera - Mathematics for Machine Learning: PCA Week 1
---
When working with datasets, we need to know how transforming the dataset (either by **stretching** or **shifting** the *dataset*) affects our quantities of interest (the ***[[Mean of a dataset|mean]]*** & the ***[[Variance of Higher-Dimensional Datasets|(co)variance]]***).

Consider three datasets:
$$
D=\{ -1,2,3 \}
$$
$$
D'= D+2 = \{ 1,4,5 \}
$$
$$
D''= 2D=\{ -2,4,6 \}
$$
```desmos-graph
left=-4; right=14;
top=2; bottom=0;
---
f(x)=1
(-1,1)|black|label:D
(2,1)|black
(3,1)|black
(1,1)|blue|label:D'
(4,1)|blue
(5,1)|blue
(-2,1)|orange|label:D''
(4,1)|orange
(6,1)|orange
```
