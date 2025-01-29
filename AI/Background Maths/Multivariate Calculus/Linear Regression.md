#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 6
---
***Linear Regression*** is a tool that is essential for understanding and analyzing data effectively. Basically, it gives us a way to give a sensible shape to our data to start understanding and working with it.

When given an amount of data to be fitted, we may propose a model based on some knowledge we have about the interactions or attributes of the data, or we may also propose a model based on how the data looks. Here's a simple linear fit of some data:

![[Pasted image 20250129122906.png]]

We can model the straight line as a function of the $i$ observations $x_i$ and a vector of the **fitting parameters**, in this case, these are $m$ and $c$.
$$
y = y(x;a_{i})=mx_{i}+c
$$
$$
a = \begin{bmatrix} m \\ c \end{bmatrix}
$$
As you can see, we can get a lot of information from this model, such as the **residuals** $r_i$ orthe **center of mass** or mean $\bar{x}$ & $\bar{y}$:
$$
r_{i} = y_{i} - mx_{i}-c
$$
$$
\bar{x}=\frac{ \sum_{i=0}^{k} x_{i}  }{ k} 
$$
To find the optimal values for my **fitting parameters**, I can take a measure of the overall *quality* of the fit by a quantity named **chi squared** ($\chi^2$), which is the sum of the squares of the **residuals**:
$$
\chi^2 = \sum_{i} r_{i}^2
$$
We square it so we can equally penalize data points which are *above* or *below* the fit's line.