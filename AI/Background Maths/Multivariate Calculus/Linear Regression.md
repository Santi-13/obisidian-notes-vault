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
As you can see, we can get a lot of information from this model, such as the **residuals** $r_i$ or the **center of mass** or mean $\bar{x}$ & $\bar{y}$:
$$
r_{i} = y_{i} - mx_{i}-c
$$
$$
\bar{x}=\frac{ \sum_{i=0}^{k} x_{i}  }{ k} 
$$
To find the optimal values for my **fitting parameters**, we can take a measure of the overall *quality* of the fit by a quantity named **chi squared** ($\chi^2$), which is the sum of the squares of the **residuals**:
$$
\chi^2 = \sum_{i} r_{i}^2 = \sum_{i} (y_{i} - mx_{i}-c)^2
$$
We square it so we can equally penalize data points which are *above* or *below* the fit's line.

From here, we notice this is a very simple ***minimization*** problem, as we need to find the lowest possible error for our fit. One way to approach this problem is to solve it explicitly, as we know that the minimum would be where the ***gradient*** of the function is $0$, so:
$$
\nabla \chi^2 = \begin{bmatrix}
\frac{\partial \chi^2}{\partial m} \\
\frac{\partial \chi^2}{\partial c}
\end{bmatrix} = \begin{bmatrix}
0 \\
0
\end{bmatrix} = \begin{bmatrix}
-2\sum_{i}x_{i}(y_{i} - mx_{i}-c) \\
-2\sum_{i}(y_{i} - mx_{i}-c)
\end{bmatrix}
$$
Then by simply analyzing the rows, we can calculate the ***fitting parameters***. For the second row, we get that:
$$
\frac{\partial\chi^2}{\partial c} = -2 \sum (y_i - mx_i - c) = 0
$$
$$
\sum (y_i - mx_i - c) = 0
$$
$$
\sum y_{i}-m \sum x_{i} = nc
$$
$$
\text{Where n = number of data points}
$$
$$
c = \frac{\sum y_{i}-m \sum x_{i} }{n}
$$
$$
c = \bar{y}-m \bar{x}
$$
Following a similar procedure, we end up coming with a solution to $m$ as well.
$$
m = \frac{\sum(x-\bar{x})y}{\sum(x-\bar{x})^2}
$$
It is also very important to have in mind that you can also find the ***uncertainties*** in the parameters (normally called $\sigma$), which are important to quote when doing a fitting of data. In this case:
$$
\sigma_{c} \approx \sigma_{m} \sqrt{ \bar{x}^2+\frac{1}{n}\sum_{i} (x-\bar{x})^2 }
$$
$$
\sigma_m^2 \approx \frac{\chi^2}{\sum(x-\bar{x})^2(n-2)}
$$
One issue that may become apparent is that our y-intercept value $c$ is dependent on $m$. If we plot out $\chi^2$ we may observe this relation.
![[Pasted image 20250130104632.png]]

The dependence of 𝑐 on 𝑚 can skew the $\chi^2$ analysis and make error estimation less reliable. To address this, we can recast the problem using the center of mass $(\bar{x},\bar{y})$ as the new origin of our coordinate system. This transformation involves expressing $𝑦$ and $𝑥$ as deviations from their respective means: $y-\bar{y}=𝑚(𝑥−\bar{x})$ In this form, we are effectively predicting the deviation of 𝑦 from its mean $(y-\bar{y})$ based on the deviation of 𝑥 from its mean $( 𝑥−\bar{x} )$. In this centered system, the new y-intercept $𝑏$ represents the expected deviation in $𝑦$ when $x$ is at its mean ( $𝑥=\bar{x}$ ). Since the data is centered, this deviation is ideally zero, making $𝑏=0$ in the transformed equation. When working outside the center of mass frame to predict $𝑦$ from $𝑥$, we can express the transformed equation as: $𝑦−\bar{y}=𝑚(𝑥−\bar{x})+𝑏$. Since it's been established that $𝑏=0$ at the center of mass, and we know that $𝑦=\bar{y}$ when $𝑥=\bar{x}$ , substituting these values yields: $\bar{y}=𝑚(\bar{x}−\bar{x})+𝑏$, which simplifies to $\bar{y} = b$. Therefore, we can use $𝑏=\bar{𝑦}$ in the transformed equation to predict $𝑦$ from $𝑥$: $𝑦=𝑚(𝑥−\bar{x})+\bar{y}$ By centering the data, we decouple the slope ($𝑚$) and the intercept, facilitating a cleaner error analysis using the chi-squared method. This approach also simplifies the calculation of uncertainties in the fitted parameters.
