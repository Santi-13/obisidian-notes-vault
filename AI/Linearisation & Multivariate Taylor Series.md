#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
---
From the definition of the ***Taylor Series*** from [[Function Approximation]]:
$$
g(x) = \sum^\infty_{n=0} \frac{1}{n!}f^{(n)}(p)(x-p)^n
$$
We can change the notation to make it simpler, starting by analyzing the case of the first degree approximation of the function $f(x) = e^x$.
```desmos-graph
left=-5; right=2;
top=3; bottom=-0.5;
---
y=e^x
(1,e)|label:p|black
```
