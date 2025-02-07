#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 6
---
We can further optimize the process of obtaining the ***fitting parameters*** for a given function introduced in ***[[Linear Regression]]*** with a method called ***Steepest Descent***, which let's us minimize our parameters by iteratively updating them based on the **error** they generate.

Let's start by analyzing a simple non-linear function with a given number of parameters:
$$
y(x;a_{k}) = (x-a_{1})^2+a_{2}, \text{k} =1\dots m
$$
Which is **nonlinear** about $a_{1}$ as simply doubling this value doesn't double the value of the evaluated function.

Say we want to fit these parameters to $i$ number of data. So, for each point of $x$ data, there is a $y$, but there's also an uncertainty ($\pmb \sigma$). We can sketch this values out.

```graph
bounds: [-1, 10, 10, -1]
keepAspectRatio: true
elements: [ 
	{type: boxplot, def: [[2.5,3,3,3,3.5], 5, 0.5], 
	att: {withLabel: true, label, name: "sigma_i"}},
	{type: point, def: [1,8], att: {withLabel: false}},
	{type: point, def: [2,5], att: {withLabel: false}},
	{type: point, def: [3,3], att: {withLabel: false}},
	{type: point, def: [4,2], att: {withLabel: false}},
	{type: point, def: [5,3], att: {withLabel: false}},
	{type: point, def: [6,5], att: {withLabel: false}},
	{type: point, def: [7,8], att: {withLabel: false}}
]
```

We can define a *goodness of fit* parameter $\chi^2$ as:
$$
\chi^2 = \sum^n_{i} \frac{[y_{i}-y(x_{i};a_{k})]^2}{\sigma^2}
$$
As we can see, the division by $\sigma$ penalizes my uncertain data points in my sum of chi-squared so they don't affect the fit too much. If we don't know the uncertainties, we can simply set $\sigma$ as $1$. Of course, the *minimum* of $\chi^2$ would be when:
$$
\nabla \chi^2=0
$$
In the case when we can't solve the $\chi^2$ equation analytically, or we simply don't want to, we use the ***Steepest Descent*** method, going down the *contours* by simply updating our *parameters vector*.
$$
a_{next}=a_{cur} - c \nabla \chi^2
$$
$\text{Where:}$
$c \to \text{Constant to say how aggresive we want each iteration to be.}$

And we keep on repeating that until we either get to an acceptable threshold of $\chi^2$, the value of $\chi^2$keeps repeating itself, or until the number of iterations gets too large. Anyway, in order to find the minimum, we need to differentiate $\chi^2$ with respect to its *parameters*.
$$
\frac{d \chi^2}{da_{k}} = \sum^n_{i=1} -2 \frac{[]}{\sigma^2} \frac{dy}{da_{k}}
$$