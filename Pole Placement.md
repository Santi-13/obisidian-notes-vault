---
tags:
  - control
---
---
A way to develop a feedback controller for a model using state space equations is using a method called *Pole Placement* or *Full State Feedback*, which is rarely used in the industry, specially compared with other methods such as *[[Linear Quadratic Regulator]]* *(LQR)* or $H_\infty$. It serves as a general approach to feedback control using state space equations so it's worth spending some time on.

As we know, the state space representation of the system is:

$\dot x = Ax + Bu$

Where $Ax$ captures the dynamics of the system and $Bu$ represents how it responds to external inputs. We know that the controller's job is to modify the $A$ matrix to change the dynamics and drive the system to stability, it does this by changing the eigenvalues of the $A$ matrix, effectively changing the poles to a negative real part.

$eigenvalues(A) = poles-of-the-system$

We can start by analyzing a simple example:

$\dot x = Ax = \begin{bmatrix}0 & 1\\2 & -1\end{bmatrix}x$

Which can also be written as:

$\dot x_1 = x_2$
$\dot x_2 = 2x_1 - x_2$

We can transform the $A$ matrix into one that uses a different set of state variables to describe the system in order to more clearly see how eigenvalues affect the system. We define a matrix of eigenvectors $E$.

$x = Ez$

$E = \begin{bmatrix}-0.45 & 0.71\\0.89 & 0.71\end{bmatrix}$ 

$\tilde A = E^{-1}AE$  
$\dot z = \tilde Az$

$\dot z = \begin{bmatrix}-2 & 0\\0 & 1\end{bmatrix}z$

Where $\tilde A$ is a diagonal matrix comprised of the systems eigenvalues $\lambda$. Now, it is important to understand that both $A$ and $\tilde A$ describe the same system in the same way, its just that the second one is described using a set of state variables that are independent of each other, and are dependent of their own state.

$\dot z_1 = -2z_1$
$\dot z_2 = z_2$

Where the solution to a differential equation like this is:

$z_n = Ce^{\lambda t}$

Where $z_n$ indicates a given state, $C$ its value at $t=0$, and $\lambda$ is the respective eigenvalue. In other words, if you start with some energy or you add it from an external input, the equation indicates how the state changes. $\lambda$ serves to change how the energy is dissipated or grows, this gives us the reason on why the poles have to be in the negative real part.

![[Pasted image 20240924113959.png]]

We then can use pole placement to change the poles of the system, either to make it stable (by driving the real part to the negatives), or to reduce oscillations (by reducing the imaginary part). We can analyze how to drive the poles by analyzing the representation of the system.

![[Pasted image 20240924114439.png]]

We see how our state equation becomes:

$\dot{x}=Ax+B(r*k_{r}-k*x)$
$\dot{x}=Ax-Bkx+Brk_{r}$
$\dot{x}=(A-Bk)x + BrK_{r}$

Where we defined a "new" $A$ matrix as a function of the selected gains. Let's analyze an example!

