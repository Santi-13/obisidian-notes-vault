#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
---
When we have a multi-variable function, such as $f(x,y,z)$, but the variables themselves are a function of some other variable $t$. If we want to get the derivative of $f$ with respect to $t$, which is simply the sum of the chains relating $f$ to $t$ through each variable. This is called the ***Total Derivative***. For example:
$$
f(x,y,z)=\sin(x)e^{yz^2}
$$
$$
x=t-1 ;y =t^2; z=\frac{1}{t}
$$
$$
\frac{df}{dt}=\frac{\partial f}{\partial x} \frac{\partial x}{\partial t}
+ \frac{\partial f}{\partial y} \frac{\partial y}{\partial t}
+ \frac{\partial f}{\partial z} \frac{\partial z}{\partial t}
$$
This allows us to calculate the result 