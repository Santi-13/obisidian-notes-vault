To the system dynamics we add the uncertainty $v$:
$$
\dot{q}=Aq+v
$$
Example.
$$
\lvert \lvert v \rvert  \rvert \leq v^+\lvert \lvert q \rvert  \rvert  
$$
For the lyapunov function:
$$
V(q) = \frac{1}{2} \lvert \lvert q \rvert  \rvert^2_{P}=\frac{1}{2} q^T Pq 
$$

The time derivative of $V(q)$ satisifies
$$
\frac{d}{dt} V(q)= \frac{1}{2} q^T P \frac{d}{dt}q 
$$