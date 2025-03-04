#Chairing #Note
Tracking.
$$
\lvert \lvert x^* - x \rvert  \rvert \to 0, \lvert  \lvert x^* - x \rvert  \rvert \leq \lvert \lvert x^* \rvert  \rvert + \lvert \lvert x \rvert  \rvert < 2x^+    
$$
$$
V_{1}(\Delta, \tilde{K_{p}}, \tilde{K_{D}}) \leq V(\Delta,\tilde{K_{p}}, \tilde{K_{D}},t)\leq V_{2} (\Delta,\tilde{K_{p}}, \tilde{K_{D}})
$$
Encontrar frontera inferior de la desigualdad:
$$
? \leq \ln\left(  \frac{1}{ 1-z} \right) \leq \frac{z}{1-z}
$$
Simulate the following system in Simulink:
$$
\dot{x} = Ax+B(u+n)
$$
$\text{Where:}$
$$
A = \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix}, B = \begin{bmatrix}
0 \\
1
\end{bmatrix}
$$
$$
x^* = \begin{bmatrix}
4\cos(2t) \\
-8\sin(2t)
\end{bmatrix}
$$
$$
n = 2\sin(2t) \sin(2 \lvert \lvert x \rvert  \rvert ) \cos(3 \lvert \lvert x \rvert  \rvert)
$$
$$
u = K_{p} (x^*-x)+K_{D}(\dot{x^*}-x)
$$
To simulate the system, let:
$$
x = \begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix}
$$
Then the state equations become:
$$
\dot{x}_{1} = x_{2}
$$
$$
\dot{x}_{2} = -2x_{1}-3x_{2}+u+n
$$


---
$$
V = \frac{1}{2} \lvert \lvert q \rvert  \rvert^2_{P}=\frac{1}{2}q^T Pq
$$
$$ V(x) = \frac{1}{2} (x - x*) \top P (x - x^*) $$

$$
\frac{d}{dt} V(q) = \left(\nabla_{q} V(q), \frac{d}{dt} q  \right) <0
$$
$$
= (Pq, Aq)
$$
$$
=q^TP^TAQ
$$
$$
=0.5 q^TP^TAQ + 0.5q^TA^TPQ
$$