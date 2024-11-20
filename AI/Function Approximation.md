#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
---
When working with complex functions, computing the whole function for each value is simply not worth it, specially when working between certain values of the graph. For this reason, we use ***function approximation*** to create a simpler polynomial equivalent.

```desmos-graph
left=-5; right=3;
top=4; bottom=-8;
---
y=1*x^4+3.0*x^3+0.5*x^2
y=0|dashed|red
(0,0)|label:(0,0)|black
y=3*x^2|dashed
y=2*(x+0.1)^3|dashed
```

The ***Taylor (or Power) Series*** is a way of approximating functions. It is also called power series because it is simply composed of coefficients in front of increasing powers of $x$, so a generalized expression may be:
$$
g(x) = a + bx + cx^2 +dx^3 + \dots
$$
Where the equation may go on infinitely, depending on the function we're considering. For normal applications however, it is usually fine to use the first terms of the series. Starting from a single term, we call these expressions the zeroth, first, second, and third approximations, which are also in turn called *truncated series*.
$$g_{0}(x) = a$$
$$g_{1}(x) = a + bx$$
$$g_{2}(x)= a + bx + cx^2$$
$$g_{3}(x) = a +
