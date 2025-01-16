#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
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
