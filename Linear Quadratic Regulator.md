#LQR
##### By Brian Douglas
---
LQR is a type of optimal controller that is based on the state-space representation.  We can compare it with a controller using [[Pole Placement]]. 

![[Pasted image 20240925115804.png]]

We observe how both of them are full state feedback controllers and have a similar structure. The main difference comes from one of the shortcomings of the [[Pole Placement]] method, which is how we can place the poles of our system wherever we want but, how do we know where is the best place to put them?

LQR helps us find the optimal $k$ by choosing characteristics based on performance and effort. We do this by defining a cost function that values certain characteristics above others, to help us find the optimal gains.

$$
J = \int_{0}^\infty (x^TQx + u^Ru)dt 
$$
Where:
$$
\begin{matrix}
Q = Performance-Gain \\
R = Effort-Gain 
\end{matrix}
$$
