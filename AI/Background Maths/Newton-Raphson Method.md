#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 5
---
The ***Newton-Raphson Method*** is an iterative approach to finding a desired solution to a equation just by evaluating the function and its derivative at certain points. Instead of having to plot the entire function. It is described as:
$$
x_{i+1} = x_{i}- \frac{f(x_{i})}{f'(x_{i})}
$$
For example, for the function:
```desmos-graph
left=-5; right=2;
top=3; bottom=-0.5;
---
f(x)=x^3
g(x)=f(0.5)+f'(0.5)*(x-0.5)|dashed
(1,e)|label:x|black
(0.5, f(0.5))|label:p|black
```