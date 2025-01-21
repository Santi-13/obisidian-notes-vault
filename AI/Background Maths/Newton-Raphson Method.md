#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 5
---
The ***Newton-Raphson Method*** is an iterative approach to finding a desired solution to a equation just by evaluating the function and its derivative at certain points. Instead of having to plot the entire function. It is described as:
$$
x_{i+1} = x_{i}- \frac{f(x_{i})}{f'(x_{i})}
$$
For example, for the function $f(x)=x^3-2x+2$:
$$
f'(x_{i})=3x^2-2
$$

```desmos-graph
left=-4; right=4;
top=4; bottom=-4;
---
f(x)=x^3-2x+2
(1,e)|label:x|black
```

Suppose we want to find the point $y=0$, we start by analyzing an initial guess $x_i=-2$:

```desmos-graph
left=-4; right=4;
top=4; bottom=-4;
---
f(x)=x^3-2x+2
g(x)=3x^2-2 |red|dashed
(-2,f(-2))|label:xi|black
```

| $i$ | **$x_{i}$** | **$f(x_i)$** | **$\frac{\partial f(x_{i})}{\partial x}$** |
|:---:| ----------- | ------------ | ------------------------------------------ |
|  0  | -2          | -2           | 10                                         |
|  1  | -1.8        | -0.23        | 7.7                                        |
|  2  | -1.77       | -0.005       | 7.4                                        |
|  3  | -1.769      | -2.3E-6      |                                            |

We find, however, that this method is not infallible as a number of things can go wrong. For starters, if the desired solution is near an inflection point, the derivative will be very low, thus the movement from our initial guess will be very extreme; in the other hand, there can be initial guesses in a function that has us locked down in a closed-loop, never reaching the desired solution.