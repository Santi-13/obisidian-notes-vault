#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 4
---
From the definition of the ***Taylor Series*** from [[Function Approximation]]:
$$
g(x) = \sum^\infty_{n=0} \frac{1}{n!}f^{(n)}(p)(x-p)^n
$$
We can change the notation to make it simpler, starting by analyzing the case of the first degree approximation of the function $f(x) = e^x$.
$$
g_{1}(x)=f(p) + f'(p)(x-p)
$$

```desmos-graph
left=-5; right=2;
top=3; bottom=-0.5;
---
f(x)=e^x
g(x)=f(0.5)+f'(0.5)*(x-0.5)|dashed
(1,e)|label:x|black
(0.5, f(0.5))|label:p|black
```
Essentially what we are doing is that we are saying that, starting from the height at the point $p$, as you move away from $p$, the corresponding change in height is equal to the *distance* from $p$ times the gradient for the function at $p$. We can then rewrite the equation in terms of $p$, to make this easier to understand.
$$
g_{1}(p+\Delta p)=f(p) + f'(p)\Delta p
$$
$$\text{Where:}$$
$$\Delta p = x-p $$
As we have everything in terms of $p$, we may as well change it to a more common and general notation using $x$:
$$
g_{1}(x+\Delta x)=f(x) + f'(x)\Delta x
$$
We can of course change our ***Taylor Series*** notation as well:
$$
g(x+\Delta x) = \sum^\infty_{n=0} \frac{1}{n!}f^{(n)}(x)\Delta x^n
$$
The process of ***linearisation*** simplifies complex equations to linear approximations, in order to make calculations easier. We note that the terms we ignore of the ***Taylor Series*** when using the first order approximation are powers of $\Delta x$, so we may notice that the linearisation works best for small spaces around $x$, as a small $\Delta x$ would become even smaller as it is multiplied by itself, so the error of our approximation to the real function would become less. We can quantify the *error* to our equation to see how accurate our approximation is, we normally choose the next ignored term. $$ 
 f(x+\Delta x)= f(x) +f'(x)(\Delta x)+O(\Delta x^2)
 $$
In this case, we see that the first order approximation is *second-degree accurate*. 

By rearranging the terms of the series to isolate the first order gradient, we can notice something interesting.
$$
f'(x) =  \frac{f(x+\Delta x) -f(x)}{\Delta x} + O(\Delta x)
$$
We see an equation similar to the ***Rise over run*** method, as well as our *error term*, which is in the first order. Simply put, the *forward difference* method is *first-order accurate*.

Now let's analyze a ***Multivariate Taylor Series*** case, starting with two dimensions, where a function $f$ is a function of the two variables $x$ and $y$:
$$
f(x+\Delta x,y+\Delta y)=e^{-(x^2+y^2)}
$$
```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-2,2], [-2,2], [0,1.2]]
axis: false
keepAspectRatio: true
elements: [
	{type: functiongraph3d, def: ["f:2.72**(-(x**2+y**2))", [-2,2], [-2,2]]}
]
```

We can intuitively say that our approximations will be similar as they were in one dimension, just that instead of a line or curve, we'll get a *surface*.

```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-2,2], [-2,2], [0,1.2]]
axis: false
keepAspectRatio: true
elements: [
	{type: slider, def: [[8,3],[10,3],[0,0.0,1]], att: {name: "y"}},
	{type: slider, def: [[8,4],[10,4],[0,0.0,1]], att: {name: "x"}},
	{type: functiongraph3d, def: ["f:2.72**(-(x**2+y**2))", [-2,2], [-2,2]], att: {strokeColor: blue, strokeOpacity: 2.0, name: "aaa"} },
	{type: functiongraph3d, def: ["f:2.72**(-(e1**2+e0**2))", [-2,2], [-2,2]], att: {strokeColor: orange, strokeOpacity: 0.6 }},
	{type: functiongraph3d, def: ["f:2.72**(-(e1**2+e0**2) ) * ( 1 - 2*e1*(x-e1)-2*e0*(y-e0) )", [-2,2], [-2,2]], att: {strokeColor: purple, strokeOpacity: 0.6, visible: true }},
]
```

The ***Taylor series expansion*** of the function goes as follows, for the zeroth approximation, it is the orange flat surface with the same height as the function at our expansion point.
$$
g_{0}=f(x,y)
$$
The first order approximation includes a gradient in the flat surface, which will depend on the gradient in both the $x$ and $y$ axes. 
$$
g_{1}= f(x,y) + (\partial_{x}f(x,y)\Delta x+ \partial_{y} f(x,y) \Delta y)
$$
By rearranging the first order term into matrices, we can see similarities with a [[Jacobian]].
$$
g_{1}= f(x,y) + 
\begin{bmatrix}
\partial_{x}f(x,y),\partial_{y} f(x,y)
\end{bmatrix} \begin{bmatrix}
\Delta x \\
\Delta y
\end{bmatrix}
$$
$$
g_{1} = f(x,y) + J_{f} \Delta \pmb x 
$$
Naturally, our second order term would be the partial derivative of the partial derivatives of the inputs, or in other words, the [[Hessian]].
$$
g_{2}= f(x,y) + (\partial_{x}f(x,y)\Delta x+ \partial_{y} f(x,y) \Delta y) +
\frac{1}{2}(\partial_{xx}f(x,y) \Delta x^2 +2\partial_{xy}f(x,y)\Delta x\Delta y + \partial_{yy} f(x,y) \Delta y^2)
$$
$$
g_{1}= f(x,y) + 
\begin{bmatrix}
\partial_{x}f(x,y),\partial_{y} f(x,y)
\end{bmatrix} \begin{bmatrix}
\Delta x \\
\Delta y
\end{bmatrix} + \frac{1}{2} \begin{bmatrix}
\Delta x, \Delta y
\end{bmatrix} \begin{bmatrix}
\partial_{xx} f(x,y), \partial_{xy} f(x,y) \\
\partial_{xy} f(x,y), \partial_{yy} f(x,y)
\end{bmatrix} \begin{bmatrix}
\Delta x \\
\Delta y
\end{bmatrix} 
$$
$$
g_{2} = f(x,y) + J_{f}\Delta \pmb x +  \frac{1}{2}\Delta \pmb x^t H_{f} \Delta \pmb x
$$
