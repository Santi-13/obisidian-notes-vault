#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
---
In short, a neural network is a mathematical function, which takes a variable in, and gives another variable back, where both of these variables could be vectors.

![[Pasted image 20241115094159.png]]
$$\pmb y =f(\pmb x)$$
Let's analyze the most simple neural network possible.

![[Simplest Neural NN]]
Where:
$$
a^{(1)}=\sigma(wa^{(0)}+b)
$$
$a \implies \text{"Activity"}$
$w \implies \text{"Weight"}$
$b \implies \text{"Bias"}$
$\sigma \implies \text{"Activation function"}$

The reason we use $\sigma$ instead of other sensible term is because it gives neural networks their association to the brain. Neurons receive electrical stimulation from their neighbors and, when the sum of these stimulations goes beyond a certain threshold, the neuron activates and stimulates its neighbors in return.

 A function that has this threshold holding characteristic is the *hyperbolic tangent*.
 ![[Pasted image 20241115100721.png]]
$$
\sigma(x) = \tanh(x) = \frac{e^x-e^{-x}}{e^x+e^{-x}}
$$
This function belongs to a family of similar functions with this characteristic "s" shape called **sigmoids**. 

If we add an additional neuron, we now 
![[Second Simplest NN]]
