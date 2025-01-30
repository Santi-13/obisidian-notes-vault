The state variable declaration of our dynamics is:
$$
q_a=q
$$
$$q_{b}=\dot{q}$$
Then:
$$\dot{q_{a}} = \dot{q}=q_{b}$$
$$ \dot{q_{b}}=\ddot{q}=\dots$$

$$
\frac{d}{dt} \begin{bmatrix}
q_{a} \\
q_{b}
\end{bmatrix} = \begin{bmatrix}
q_{b} \\
-K_{p}q_{a}-K_{D}q_{b}
\end{bmatrix}
$$
$$
= \begin{bmatrix}
0_{n * n} & I_{n*n} \\
-K_{p} & -K_{D}
\end{bmatrix} \begin{bmatrix}
q_{a} \\
q_{b}
\end{bmatrix}
$$
$$
\frac{d}{dt}q=Aq
$$

This way, we can modify the eigenvalues of our dynamics, allowing us to reach most spaces.

Something important to note is that for:
$$ 
A= \begin{bmatrix}
1 & 2 \\
3  & 4
\end{bmatrix}
$$
$$
e^{At} \neq \begin{bmatrix}
e^{1t} & e^{2t} \\
e^{3t} & e^{4t}
\end{bmatrix}
$$
Some conditions for our proposed dynamics to work is that $B(q_a)$ and $\Omega$ must be invertible. For $B(q_a)$, it always tends to be, as it describes the energy of the system; In the other hand, $\Omega$ depends on the number of actuators, as it acts as a "selector" for which actuators affect our controlled dynamics $\tau$, for a sub-actuated system, $\Omega$ is not invertible as its determinant is $0$. 

