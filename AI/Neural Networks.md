#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
---
In short, a neural network is a mathematical function, which takes a variable in, and gives another variable back, where both of these variables could be vectors.

![[Pasted image 20241115094159.png]]
$$\pmb y =f(\pmb x)$$
Let's analyze the most simple feed-forward neural network possible.

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

If we add an additional neuron, we now need to differentiate neurons on the same *layer*, and also define the new activation function as the sum of the inputs.

![[2nd Simplest NN]]
$$
a^{(1)}=\sigma(w_{0}a^{(0)}_{0}+w_{1}a^{(0)}_{1}+b)
$$
We can see how we can generalize this function as the sum of $n$ inputs, but also as the dot product between two vectors.
$$
a^{(1)}=\sigma(\pmb w \cdot \pmb a^{(0)}+b)
$$
The complexity augments when we have multiple output neurons, as the number of inputs doubles, each with its own weights, and with their own bias.

![[3rd Simplest NN]]
$$
a_{0}^{(1)}=\sigma(\pmb w_{0} \cdot \pmb a^{(0)}+b_{0})
$$
$$
a_{1}^{(1)}=\sigma(\pmb w_{1} \cdot \pmb a^{(0)}+b_{1})
$$
---
$$
\pmb a^{(1)}=\sigma(\pmb W^{(1)} \pmb a^{(0)}+ \pmb b^{(1)})
$$
This way, we have a vector of output neurons, which is a function of a matrix of weights, multiplied by a vector of inputs and added to a bias vector.

The complexity may scale as the network becomes more complex, which means adding more ***hidden layers*** to our network,

![[4th Simplest NN]]$$
\pmb a^{(1)}=\sigma(\pmb W^{(1)} \cdot \pmb a^{(0)}+ \pmb b^{(1)})
$$$$
\pmb a^{(2)}=\sigma(\pmb W^{(2)} \cdot \pmb a^{(1)}+ \pmb b^{(2)})
$$
$$
\pmb a^{(L)}=\sigma(\pmb W^{(L)} \cdot \pmb a^{(L-1)}+ \pmb b^{(L)})
$$

A classic approach to training these kind of neural networks is called ***back-propagation***, as it first looks at the **output** neurons and then it works back *through* the network. Initially, we set all weights and biases as a random number, we then calculate the **cost**, or **error**, of the passed data compared to our training data, and make adjustments, trying to minimize this error and finding the right set of weights and bias that best match the model to our training data.