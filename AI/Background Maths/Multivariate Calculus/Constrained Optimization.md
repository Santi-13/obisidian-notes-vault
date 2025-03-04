#MachineLearning #MultivariateCalculus
#### By: Coursera - Mathematics for Machine Learning Week 5
---
***Constrained optimization*** refers to finding the *minima* or *maxima* of a function along a constrained *path*. A **contour map** is a graphical representation of a three-dimensional surface on a two-dimensional plane. It uses **contour lines** to connect points of equal value, such as elevation or temperature. 

![[Pasted image 20250128105325.png]]

A french mathematician named **Lagrange** noticed that when the **contours** just *touch* the *path*, then you'll have found the *maximum* or *minimum* point. He also noticed that when the contour touches the *path*, the vector perpendicular to the **contour** is in the same direction as the vector of the *path* itself. So we want to find the grad that is perpendicular to both the *path* and the *function*.

So we want to maximize the function $f(x,y) = x^2y$ subject to some constraint equation $g(x,y)=x^2+y^2=a^2$.

![[Pasted image 20250128111456.png]]
So we want to solve for any case in which $\nabla g$ is perpendicular to $\nabla f$. So we need to solve for $\nabla f=\lambda \nabla g$, where $\lambda$ is called the **Lagrange multiplier**.
$$
\nabla f=\lambda\nabla g
$$
$$
\begin{bmatrix}
2xy \\
x^2
\end{bmatrix} = \lambda \begin{bmatrix}
2x \\
2y
\end{bmatrix}
$$
Along with the *constraint equation*, we have three equations for three unknown variables. So we solve:
$$
1.\text{ } 2xy = \lambda 2x \implies y = \lambda
$$
$$
2. \text{ } x^2=\lambda 2y\implies x=\pm \sqrt{ 2 } y
$$
$$
3. \text{ } x^2+y^2=a^2 \implies 3y=a^2 \implies y= \pm \frac{a}{\sqrt{ 3 }}
$$
$$
\text{Solutions } 
\frac{a}{\sqrt{ 3 }} \begin{bmatrix} \sqrt{ 2 } \\ 1 \end{bmatrix},
\frac{a}{\sqrt{ 3 }} \begin{bmatrix} \sqrt{ 2 } \\ -1 \end{bmatrix},
\frac{a}{\sqrt{ 3 }} \begin{bmatrix} -\sqrt{ 2 } \\ 1 \end{bmatrix},
\frac{a}{\sqrt{ 3 }} \begin{bmatrix} -\sqrt{ 2 } \\ -1 \end{bmatrix},
$$
Plotting on $f(x,y)$:
$$
f(x,y) \to \frac{2a^3}{3\sqrt{ 3 }}, 
-\frac{2a^3}{3\sqrt{ 3 }},
 \frac{2a^3}{3\sqrt{ 3 }},
 -\frac{2a^3}{3\sqrt{ 3 }}
$$
We then notice how the solutions with a positive $y$ value are the maximums, and the negative ones are the minimums.
