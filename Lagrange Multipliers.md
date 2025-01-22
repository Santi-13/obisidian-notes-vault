#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 5
---
Similar to what we learned about the ***[[Newton-Raphson Method & Gradient Descent]]***, we can try something called ***Constrained Optimization***, which basically means finding the minima or maximum of a function *constrained* by another equation. For example, for the function $f(x)$ constrained by $g(x)$:
$$
f(x)=\exp\left( -\frac{2x^2+y^2-xy}{2} \right)
$$
$$
g(x) = x^2+3(y+1)^2-1=0
$$
![[Pasted image 20250122112011.png]]

![[Pasted image 20250122112039.png]]
This function has two minima and maxima. To find them, we use what we call ***Lagrange Multipliers***, which make use of the fact that the minima and maxima on the curve (or path) are found where the constraint is parallel to the contours of the function. Since they are parallel, the gradient of both will be parallel too, just not of the same magnitude exactly. So we can write the gradient of the constraint function $g(x)$ as a magnitude of $\nabla f(x)$:
$$
\nabla f(x)=\lambda \nabla g(x)
$$
$$
\begin{bmatrix}
\frac{\partial f}{\partial x} \\
\frac{\partial f}{\partial y}
\end{bmatrix} = \lambda \begin{bmatrix}
\frac{\partial g}{\partial x} \\
\frac{\partial g}{\partial y}
\end{bmatrix}
$$
This equation, along with $g
