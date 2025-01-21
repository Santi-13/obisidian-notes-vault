#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 5
---
The ***Newton-Raphson Method*** is an iterative approach to finding a desired solution to a equation just by evaluating the function and its derivative at certain points. Instead of having to plot the entire function. It is described as:
$$
x_{i+1} = x_{i}- \frac{f(x_{i})}{f'(x_{i})}
$$
For example, for the function:
```desmos-graph
left=-4; right=4;
top=4; bottom=-4;
---
f(x)=x^3-2x+2
(1,e)|label:x|black
```
Suppose we want to find the point $y=0$
