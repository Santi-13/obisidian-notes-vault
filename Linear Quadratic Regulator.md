#LQR #ControlTheory 
##### By Brian Douglas
---
LQR is a type of optimal controller that is based on the state-space representation.  We can compare it with a controller using [[Pole Placement]]. 

![[Pasted image 20240925115804.png]]

We observe how both of them are full state feedback controllers and have a similar structure. The main difference comes from one of the shortcomings of the [[Pole Placement]] method, which is how we can place the poles of our system wherever we want but, how do we know where is the best place to put them?

LQR helps us find the optimal $k$ by choosing characteristics based on performance and effort. We do this by defining a cost function that values certain characteristics above others, to help us find the optimal gains.

$$
J = \int_{0}^\infty (x^TQx + u^TRu)dt 
$$
Where:
$$
\begin{matrix}
Q = Performance-Gain \\
R = Effort-Gain 
\end{matrix}
$$
This cost function helps change more comprehensively the gains of our system based on qualities we desire from a system by simply changing the Q and R matrices. Rather than thinking on pole locations, we get to optimize based on the balance of performance and actuator effort we want.

We define the cost function as an integral to measure the area under the curve, as a bigger area means a worse performance (i.e. more time to reach a goal).

![[Pasted image 20241002121812.png]]

And then we square the states to only work with positive values, this also has the secondary effect of making it a quadratic function, which always has a definite minimum.

![[Pasted image 20241002121938.png]]