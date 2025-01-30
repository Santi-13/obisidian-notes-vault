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