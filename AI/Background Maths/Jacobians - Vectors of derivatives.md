#MachineLearning
#### By: Coursera - Mathematics for Machine Learning 
---
When you have a single function of many variables:
$$
f(x_{1},x_{2},x_{3},\dots)
$$
The Jacobian of that function can be described as a vector of the partial derivatives of the function.
$$
J=\left[ \frac{\partial f}{\partial x_{1}}, \frac{\partial f}{\partial x_{2}},\frac{\partial f}{\partial x_{3}},\dots\right]
$$
By convention, we write this as a row vector, instead of a column vector. Let's analyze an example to gather some deeper intuition on the subject. For a function:
$$
f(x,y,z)=x^2y+3z
$$
It's Jacobian vector looks like:
$$
J=[2xy,x^2,3]
$$
This vector describes which variables affect the rate of change of each variable in the function, for example, the vector tells us that:
- How $f(x,y,z)$ changes with respect to $x$, depending on the magnitude of $2xy$, that is, as the product becomes larger, changes in $x$ become more significant.
- How the significance in changes in $y$ are proportional to $x^2$.
- How $z$ always increase or decrease the function's value by $3$ units.
