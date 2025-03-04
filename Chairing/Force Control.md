#Explanation #Chairing 

One reason to use ***Force Control*** in robotics system is that they *interact* with their environment, which means that the forces they apply to their surroundings are applied back to them, which may cause unintended side effects if not considered in their control laws.

To use ***Force Control*** means that I can make an interaction of my system with its environment behave according to the desired task.

We define as a **kinematic constraint** as an object that *constraints* the geometric paths that can be followed by the *end-effector*. This situation corresponding to contact with a stiff surface, is generally referred to as *constrained motion*.

In other cases, the contact task is characterized by a dynamic interaction that can be:
- Inertial (pushing a block)
- Dissipative (sliding on a surface with friction)
- Elastic (pushing against an elastically compliant wall)

### From Indirect Force Control to Hybrid Force/Motion Control

***Indirect Force Control*** refers to **impedance control (or admittance control)**, where the deviation of the end-effector motion from the desired motion due to the interaction with the environment is related to the contact force through a mechanical impedance/admittance with adjustable parameters.

To do this, we assume a reference frame $\Sigma_{e}$ at the end of the end-effector. A position vector $p_{e}$ and a rotation matrix $R$ from the origin. This allows us to find either a velocity, position, or force vector that originates from the end-effector, in terms of the origin.

It's velocity is denoted by a $6 \times 1$ vector $v_c = \begin{bmatrix}\dot{p}_{c}  \\ \omega_{c}\end{bmatrix}$, where $\dot{p}_{c}$  is the translational velocity, and $\omega_{c}$ is the rotational velocity. And can be computed from the $n$\*1 joint velocity vector $\dot{q}$ using the linear mapping:
$$
v_{c} = J(q) \dot{q}
$$
![[Diagram Force Transformations]]

The **force** $f_{e}$ and moment $m_e$ applied by the end-effector to the environment are the components of the wrench $h_e$.
$$
h_{e} = \begin{bmatrix}
f_{c}^T, m_{e}^T
\end{bmatrix}
$$
It is useful t o consider the operational space formulation of the dynamic model of a rigid robot manipulator in contact with the environment.
$$
\underbrace{ \Lambda(q)\dot{v}_{c} + \Gamma(q,\dot{q})v_{c} + \eta(q) }_{ \text{Newton's Second Law} } = \underbrace{ h_{c} - h_{e} }_{ \text{Force Differences} }
$$

Where:
$$
\Lambda(q) = (J(q)H^{-1}(q)J^T(q))^{-1}
$$
