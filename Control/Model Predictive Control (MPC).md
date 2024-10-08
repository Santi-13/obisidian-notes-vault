#MPC #ControlTheory 
#### By Melda Ulosoy [Matlab]
---
Model predictive control allows us to base a control action on how we expect the system to behave towards a goal. It utilizes a cost function to optimize the inputs of a system to reach a desired state 

MPC is often recommended for Multiple-Output Multiple-Input (MIMO) systems, as using traditional controllers to keep certain states on a reference doesn't take into account the effect of other states on it, making it very difficult to obtain the appropriate gains of the system, specially with larger models.

![[Pasted image 20241003090746.png]]

This is a main advantage of MPC controllers, as it can control the outputs of the system, while considering the interactions between inputs.

![[Pasted image 20241003091151.png]]

	Another advantage of MPC is its ability to handle constraints, 