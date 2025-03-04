#Chairing #Explanation
The ***Lyapunov*** function is part of the ***Lyapunov Stability Theory***, which describes a scalar function $V$ that helps determine the stability of an equilibrium point.

Consider a system:
$$
\mathrm{x}  = \begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix}
$$
$$
\mathrm{\dot{x}} = A \mathrm{x}
$$
To propose a ***Lyapunov function***, we need it to fulfill these conditions:
.
	a)  $V(\mathrm{x}) > 0, \forall \mathrm{x} \in \mathrm{X}, \mathrm{X} \to R^+$
	b) $V(\mathrm{x}^{eq}) = 0$
	c) $\frac{d}{dt} V(\mathrm{x}) <0 \text{ for all }\mathrm{X} \text{ except } \mathrm{x}^{eq}$
.
A common proposal for $V(\mathrm{x})$ is:
$$
V(\mathrm{x}) = \frac{1}{2} \lvert \lvert \mathrm{x} \rvert  \rvert_{P}^2  
$$
Where $\lvert \lvert \mathrm{x} \rvert \rvert^2_{P}$ representes the **quadratic** form associated with the positive definite matrix $P$. We can decompose the **quadratic Euclidean norm** into its ***[[Quadratic Norm Representation|matrix notation]]*** as follows:
$$
V(\mathrm{x}) = \frac{1}{2} \mathrm{x}^T P \mathrm{x} , P\neq 0
$$
#### a)  $V(\mathrm{x}) > 0, \forall \mathrm{x} \in \mathrm{X}, \mathrm{X} \to R^+$

From the definition of the ***[[Positive Definite Matrix]]***, we know that for this to be achieved, we need $P$ to be a positive definite matrix.
$$
\text{Only if } P>0
$$
#### b) $V(\mathrm{x}^{eq}) = 0$

Similarly, if the **equilibrium point** is $0$, then its simple to see that this condition is achieved.
$$
V(\mathrm{x}^{eq}) = \frac{1}{2} (\mathrm{x}^{eq})^T P \mathrm{x}^{eq} = 0
$$
If the **equilibrium point** is different than zero, then:


#### c)$\frac{d}{dt} V(\mathrm{x}) <0 \text{ for all }\mathrm{X} \text{ except } \mathrm{x}^{eq}$

Because of the *chain rule*, we get the *time derivative* of $V(\mathrm{x})$ as:
$$
\frac{d}{dt} V(\mathrm{x}) = \langle \nabla_{x} V(\mathrm{x}), \frac{d}{dt} \mathrm{x} \rangle  
$$
From ***[[Matrix Calculus Derivative Rules]]***, we get that the derivative or *gradient* of $V(\mathrm{x})$ is $P \mathrm{x}$, so the inner product becomes:
$$
\frac{d}{dt} V(\mathrm{x}) = \langle P \mathrm{x}, A \mathrm{x} \rangle  
$$
Considering both $P\mathrm{x}$ & $A\mathrm{x}$ are $2 \times 1$ vectors, we need to transpose the first one to be able to apply the inner product, basically:
$$
\frac{d}{dt} V(\mathrm{x}) = (P\mathrm{x}) \cdot (A\mathrm{x}) = (P\mathrm{x})^T (A\mathrm{x})
$$
Considering that:
$$
(P\mathrm{x})^T = \mathrm{x}^T P^T 
$$
$$
\frac{d}{dt} V(\mathrm{x}) = \mathrm{x}^T P^T A \mathrm{x} = 0.5 \mathrm{x}^TP^TA\mathrm{x} + 0.5 \mathrm{x}^TP^TA\mathrm{x}
$$
Because $\mathrm{x}^T P^T A \mathrm{x}$ is a **scalar**, its transpose is equal to itself, so:
$$
(\mathrm{x}^T P^T A \mathrm{x})^T = \mathrm{x}^TA^TP\mathrm{x}
$$
Then we can do:
$$
\frac{d}{dt} V(\mathrm{x}) = 0.5 \mathrm{x}^TP^TA\mathrm{x} + 0.5 \mathrm{x}^TA^TP\mathrm{x} 
$$
$$
\frac{d}{dt} V(\mathrm{x}) = 0.5 \mathrm{x}^T \underbrace{ (P^TA + A^TP) }_{ -Q } \mathrm{x} 
$$
So we arrive at the conclusion that $Q$ must be symmetric and **greater** than $0$ to guarantee ***real eigenvalues***.
