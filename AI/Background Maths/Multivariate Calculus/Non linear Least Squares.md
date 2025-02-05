#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 6
---
We can further optimize the process of obtaining the ***fitting parameters*** for a given function introduced in ***[[Linear Regression]]*** with a method called ***Steepest Descent***, which let's us minimize our parameters by iteratively updating them based on the **error** they generate.

Let's start by analyzing a simple non-linear function with a given number of parameters:
$$
y(x;a_{k}) = (x-a_{1})^2+a_{2}, \text{k} =1\dots m
$$
Which is **nonlinear** about $a_{1}$ as simply doubling this value doesn't double the value of the evaluated function.

If we want to fit these parameters to $i$ number of data. So, for each point of $x$ data, there is a $y$, bui