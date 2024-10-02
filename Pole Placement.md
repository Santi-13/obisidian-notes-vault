---
tags:
  - ControlTheory
  - "#PolePlacement"
---
##### By: Brian Douglas
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

We can transform the $A$ matrix into one that uses a different set of state variables to describe the system in order to more clearly see how eigenvalues affect the system. We define a matrix of eigenvectors of $A$ as $E$.

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

Where we defined a "new" $A$ matrix as a function of the selected gains. 
### Example
---
Let's analyze a system:
$$
\dot{x} = \begin{bmatrix}
0 & 1  \\
2 & -1
\end{bmatrix}
x + \begin{bmatrix}
1 \\
0
\end{bmatrix} u
$$
$$y = \begin{bmatrix}1 & 0\end{bmatrix}x$$
We first find the eigenvalues of $A$:

$$\det(A-\lambda I) = 0$$
$$
\det(\begin{bmatrix}
-\lambda & 1 \\
2 & -1-\lambda
\end{bmatrix}) = 0 \to 
\lambda^2 + \lambda - 2 = 0
$$
$$\lambda = -2,+1$$
We observe how one of the eigenvalues is unstable. Using pole placement, we know that:
$$
A_{CL} = A-Bk = \begin{bmatrix}
0 & 1 \\
2 & -1 
\end{bmatrix} - \begin{bmatrix}
1 \\
0
\end{bmatrix} \begin{bmatrix}
k_{1} & k_{2}
\end{bmatrix}
$$
$$
A_{CL} = \begin{bmatrix}
-k_{1} & 1-k_{2} \\
2 & -1
\end{bmatrix}
$$
So we can again find its eigenvalues following the same process, resulting in the characteristic equation as follows:

$$\lambda^2 + (1+k_{1})\lambda + (k_{1} + 2k_{2} -2) = 0$$
From which we can derive the needed gains to place the poles wherever we want them, in this case, for poles at $\lambda=-2,-1$, we need:
$$
(\lambda+2)(\lambda+1)=0
$$
So we find that:
$$k_{1} = 2$$
$$k_{2} = 1$$
For more complex systems, this approach becomes unsustainable. Luckily, Matlab provides an easy way to make this, simply using the `place()` command.

```
% System matrices
A = [0 1; 2 -1];
B = [1; 0];
C = [1 0];
D = 0;

% Desired eigenvalues
P = [-2 -1];

% Gains
K = place(A,B,P);

% Closed loop system dynamics
A_cl = A - B*K;
```

Another thing that has been left unaddressed is the gain $k_r$ which is simply used to scale the reference to reduce steady state error, it is based on the inverse of the factor of the steady-state of the closed loop system.

![[Pasted image 20240924120933.png]]

We can get it very simply in Matlab as follows:

```
% Closed loop system
sys_cl = ss(A_cl,B,C,D);

% Check step response
step(syscl);

% Solve for Kr
Kdc = dcgain(sys_cl);
Kr = 1 / Kdc; 

% Create and check scaled system
sys_cl_scaled = ss(A_cl,B*kr,C,D);
step(sys_cl_scaled);
```

### Flashcards
---
**What is the difference between a controller using pole placement or LQR and a typical controllers?**:: Typical controllers take the error signal and actuate on it. In the other hand, pole placement allows us to directly modify the eigenvalues of the system by scaling the state of the system via a matrix $K$, as well as adjust the reference point via a scaling factor $K_r$ to avoid steady-state error.
<!--SR:!2024-09-29,3,250-->
**What is the difference between feeding back the state $x$ of the system versus the output $y$ of it?**:: The difference comes from the availability of the system, as well as the complexity that is required and wanted for it. To make a state-feedback controller, for example, it is necessary to have a model of the system and for all the state to be observable and measurable (or able to be estimated); While for an output-feedback controller, the output is always observable and measurable, providing a more simple approach at the cost of less precision.
<!--SR:!2024-09-29,3,250-->
**What does the eigenvalues of a system tells us about its behavior?**:: They indicate the way the system dissipates energy, the real part of $\lambda$ modifies the stability of the system and the speed it converges to steady-state, while the imaginary part makes the system oscillate.
<!--SR:!2024-09-29,3,250-->

