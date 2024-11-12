#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
---
When we have a multi-variable function, such as $f(x,y,z)$, but the variables themselves are a function of some other variable $t$. If we want to get the derivative of $f$ with respect to $t$, which is simply the sum of the chains relating $f$ to $t$ through each variable. This is called the ***Total Derivative***. For example:
$$
f(x,y,z)=\sin(x)e^{yz^2}
$$
$$
x=t-1 ;\text{ }y =t^2;\text{ } z=\frac{1}{t}
$$
$$
\frac{df}{dt}=\frac{\partial f}{\partial x} \frac{\partial x}{\partial t}
+ \frac{\partial f}{\partial y} \frac{\partial y}{\partial t}
+ \frac{\partial f}{\partial z} \frac{\partial z}{\partial t}
$$
This allows us to calculate the result in a piece-wise manner instead of substituting everything, which is something computers are very good at. We can generalize this concept as follows:
$$
f(x_{1}, x_{2},x_{3},\dots,x_{n})=f(\pmb{x})
$$
$$
\frac{\partial f}{\partial \pmb{x}} = \begin{bmatrix}
\frac{\partial f}{\partial x_{1}} \\
\frac{\partial f}{\partial x_{2}} \\
\frac{\partial f}{\partial x_{3}} \\
\vdots \\
\frac{\partial f}{\partial x_{n}}
\end{bmatrix} \text{ }\text{ }
\frac{\partial \pmb{x}}{\partial t} = \begin{bmatrix}
\frac{\partial x_{1}}{\partial t} \\
\frac{\partial x_{2}}{\partial t} \\
\frac{\partial x_{3}}{\partial t} \\
\vdots \\
\frac{\partial x_{n}}{\partial t}
\end{bmatrix}
$$
$$
\frac{df}{dt} =\frac{\partial f}{\partial \pmb{x}}\frac{\partial \pmb{x}}{\partial t}
$$
