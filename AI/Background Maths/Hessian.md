#MachineLearning 

---
In some ways, the Hessian is an extension of the Jacobian vector. For the [[Jacobian]], we found all the first order derivatives of a function and collected them in a vector; for the Hessian, we will find all the second order derivatives and collect them in a matrix. For a function of $n$ variables, it would look like this:
$$
H = \begin{bmatrix}
\partial x_{1}x_{1}f & \partial x_{1}x_{2}f & \dots & \partial x_{1}x_{n}f \\
\partial x_{2}x_{1}f & \partial x_{2}x_{2}f & \dots & \partial x_{2}x_{n}f \\
\vdots & \vdots & \ddots & \vdots \\
\partial x_{n}x_{1}f & \partial x_{n}x_{2}f & \dots & \partial x_{n}x_{n}f 
\end{bmatrix}
$$
It is often easier to find the [[Jacobian]] of a function before trying to find the Hessian, let's look at an example:
$$
f(x,y,z) = x
$$