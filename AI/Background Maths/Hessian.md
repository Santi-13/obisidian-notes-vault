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
f(x,y,z) = x^2yz
$$
It's [[Jacobian]] is:
$$
J= \begin{bmatrix}
2xyz, &x^2z, & x^2y
\end{bmatrix}
$$
Then we can do a "partial derivative" of the Jacobian to find the Hessian:
$$
H = \begin{bmatrix}
2yz & 2xz & 2xy \\
2xz & 0 & x^2 \\
2xy & x^2 & 0
\end{bmatrix}
$$
We notice that the matrix is symmetrical across the leading diagonal. This will always be true if the function is continuous, meaning it has no sudden step changes. When passing the function an $(x,y,z)$ coordinate, it tells us something about that point in the space. To further analyze what the Hessian tells us, let's analyze a 2D example:
$$
f(x,y)=x^2+y^2
$$
$$
J=[2x, 2y]
$$
$$
H=\begin{bmatrix}
2 & 0 \\
0 & 2
\end{bmatrix}
$$
If we were to not know the original function, we could easily find a zero-gradient point using only the Jacobian by using the point $(0,0)$. The **Hessian** helps us find whether this point is either a maximum, a minimum or a saddle point. If the determinant of $H$ is positive ($|H|=+$), then the point is either a minimum or maximum, which we can determine by looking at the upper-left value of the **Hessian** matrix (positive is maximum, negative is minimum); Whereas, if $|H|=-$, then the point is a saddle point.

Now, in real life, we have to ask ourselves what to do in case of non-ideal scenarios: Multi-dimensional functions, discontinuous functions, unknown functions and noisy functions. These scenarios can greatly impact the time it takes for us to compute a solution. One area of mathematics specialized in developing approximate solutions for problems that don't have an explicit formula, or that do, but calculating it would take forever: **Numerical Methods**.

One particular approach useful in the case of high-dimensional problems comes from *rise over run* approximation of the **derivative**, calculated over a finite interval. 

![[Pasted image 20241111142348.png]]
$$
x_{gradient} 
$$
