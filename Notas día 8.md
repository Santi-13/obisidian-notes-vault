$$
V(x_{1}, \tilde{k_{p}}, \tilde{k_{D}}) = \frac{1}{2} \lvert \lvert x \rvert  \rvert^2_{p}+\lambda_{1}\underbrace{t_{r}\{  \tilde{k_{p}} \tilde{k_{p}^T} \}}_{Frobenius}+ \lambda_{2} \underbrace{t_{r}}_{Traza} \{ \tilde{k_{D} } \tilde{k_{D}^T} \} 

$$
$\text{Where:}$
$$
\tilde{k_{p}} = k_{p}(t) -k_{p}^*
$$
$$
\tilde{k_{D}}=k_{D}(t)-k_{D}^*
$$

We need to set our equation so it includes its distance to the barrier with radius $x^+$:
$$
\underbrace{ \lambda_{i} =\lambda_{i0}\left( \frac{x^+ - \lvert \lvert x \rvert  \rvert^2}  {x^+} \right) }_{\text{Direct Barrier LF}}
$$
Where:
$$
\underbrace{\lambda_{i0}\to \infty}_{\text{Prescribed Kristic}}
$$
We can also change the first term of our equation:
$$
V(x_{1}, \tilde{k_{p}}, \tilde{k_{D}}) = 
\ln\left( \frac{x^+}{x^+ - \lvert \lvert x \rvert  \rvert^2 }  \right) +
\lambda_{1}\underbrace{t_{r}\{  \tilde{k_{p}} \tilde{k_{p}^T} \}}_{Frobenius}+ 
\lambda_{2}t_{r} \{ \tilde{k_{D} } \tilde{k_{D}^T} \} 
$$We get the derivative:
$$
\dot{V}(x_{1}, \tilde{k_{p}}, \tilde{k_{D}}) = 
\left( \frac{x^+- \lvert \lvert x \rvert  \rvert^2}{x^+  }  \right) \frac{(-x^+ ) (-2x^T\dot{x})}{(x^+ - \lvert \lvert x \rvert  \rvert^2)^2}+

2\lambda_{1} t_{r}\{  \tilde{k_{p}} \dot{\tilde{k_{p}^T}} \} +
\dot{\lambda_{1}} t_{r} \{ \tilde{k_{p}} \tilde{k_{p}^T} \}+

2\lambda_{2}t_{r} \{ \tilde{k_{D} } \dot{\tilde{k_{D}^T}} \} +
\dot{\lambda_{2}} t_{r} \{ \tilde{k_{D} } \tilde{k_{D}^T} \}
$$
$$
\dot{V}(x_{1}, \tilde{k_{p}}, \tilde{k_{D}}) =  \frac{2x^T\dot{x}}{x^+ - \lvert \lvert x \rvert  \rvert^2}+

2\lambda_{1} t_{r}\{  \tilde{k_{p}} \dot{\tilde{k_{p}^T}} \} +
\dot{\lambda_{1}} t_{r} \{ \tilde{k_{p}} \tilde{k_{p}^T} \}+

2\lambda_{2}t_{r} \{ \tilde{k_{D} } \dot{\tilde{k_{D}^T}} \} +
\dot{\lambda_{2}} t_{r} \{ \tilde{k_{D} } \tilde{k_{D}^T} \}
$$


