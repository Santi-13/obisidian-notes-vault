#ComputaciónCognitiva 

---


En el caso de una clasificación entre dos casos $[0, 1]$, en el que en esta particular instancia, la respuesta correcta es 0. 
$$
\frac{\partial y_{m}(\alpha)}{\partial h_{m}} =
\frac{\partial}{\partial h_{m}}\left[ \frac{e^{h_{m}(\alpha)}}{\sum_{i=0}^c e^{h_{m}(i)}} \right] = \frac{\partial}{\partial h_{m}} \left[ \frac{e^{h_{m}(\alpha)}}{e^{h_{m}(\alpha)}+e^{h_{m}(1)}} \right]
$$

Considerando que la derivada de una división se define como:
$\partial$