#Chairing #Note
The Barrier Lyapunov Function is given by:
$$
\frac{d}{dt}x = Ax + Bu + \underbrace{\eta}_{\text{Perturbance}}
$$
$$
u = K_{p}x+K_{D}\dot{x}
$$
If
$$
\lvert \lvert x \rvert  \rvert^2_{P}<x^+ 
$$
Another equation
$$
\frac{d^2}{dt^2}q=
M^-1 \left( -C\left( q, \frac{d}{dt}q \right) \frac{d}{dt}q - G(q) \right) + M^-1u + \eta
$$
$$
u = MK_{p}q+MK_{D} \frac{d}{dt} q + C(q, \frac{d}{dt} q) \frac{d}{dt}q + G(q)
$$
Then
$$
\frac{d^2}{dt^2}q = K_{p}q+K_{D} \frac{d}{dt} q + \eta
$$
Where
$$
x = \begin{bmatrix}
q \\
\frac{d}{dt} q
\end{bmatrix}
$$
$$
\frac{d}{dt} x = \begin{bmatrix}
0 & I \\
K_{p} & K_{D}
\end{bmatrix} x + \begin{bmatrix}
0 \\
I
\end{bmatrix}
$$
$$
\dot{V}(x_{1}, \tilde{k_{p}}, \tilde{k_{D}}) =  

\frac{2x^T P (Ax+B\eta)}{x^+ - \lvert \lvert x \rvert  \rvert^2}+

2\lambda_{1} t_{r}\{  \tilde{k_{p}} \dot{\tilde{k_{p}^T}} \} +
\dot{\lambda_{1}} t_{r} \{ \tilde{k_{p}} \tilde{k_{p}^T} \}+

2\lambda_{2}t_{r} \{ \tilde{k_{D} } \dot{\tilde{k_{D}^T}} \} +
\dot{\lambda_{2}} t_{r} \{ \tilde{k_{D} } \tilde{k_{D}^T} \}
$$
Analyzing the term
$$
2x^T P (Ax+B \eta) = x^T (PA + A^TP)x + 2x^T PB \eta + \epsilon \eta^T\eta - \epsilon \eta^T\eta + x^TQx - x^TQx
$$
$$
\begin{bmatrix}
x \\
\eta
\end{bmatrix}^T \begin{bmatrix}
PA+A^TP+Q & PB \\
B^TP & -\epsilon I
\end{bmatrix} \begin{bmatrix}
x \\
\eta
\end{bmatrix} + \epsilon \eta^T\eta - x^TQx
$$
If $\begin{bmatrix} PA+A^TP+Q & PB \\B^TP & -\epsilon I \end{bmatrix} \leq_{0}$, then:
$$
2x^T P (Ax+B \eta) \leq
\epsilon \eta^T \eta - x^T Q x
$$
