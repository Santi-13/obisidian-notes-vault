#ComputaciónCognitiva 

---

Definimos nuestra salida como:
$$
h_{m} = ax + b
$$
Donde:
$h_{m} \in \mathbb{R}^c$
$a \in \mathbb{R}^{c*d}$
	$h_{m} \in \mathbb{R}^c$
$h_{m} \in \mathbb{R}^c$
Y la clase como:
$$
y_{m} = \frac{e^{h_{m}}}{\sum_{i=0}^c e^{h_{m}(i)}}
$$
En el caso de una clasificación entre dos casos $[0, 1]$, en el que en esta particular instancia, la respuesta correcta es 0. 
$$
\frac{\partial y_{m}(\alpha)}{\partial h_{m}} =
\frac{\partial}{\partial h_{m}}\left[ \frac{e^{h_{m}(\alpha)}}{\sum_{i=0}^c e^{h_{m}(i)}} \right] = \frac{\partial}{\partial h_{m}} \left[ \frac{e^{h_{m}(\alpha)}}{e^{h_{m}(\alpha)}+e^{h_{m}(1)}} \right]
$$

Considerando que la derivada de una división se define como:
$$\frac{\partial}{\partial x}\left( \frac{u}{v} \right) = \frac{v *du - u*dv}{v^2}$$
Entonces:
$$
\frac{\partial y_{m}(\alpha)}{\partial h_{m}(\alpha)} =
\frac{\partial}{\partial h_{m}(\alpha)} \left[ \frac{e^{h_{m}(\alpha)}}{\sum_{i=0}^c e^{h_{m}(i)}} \right] =
\frac{ \sum_{i=0}^c e^{h_{m}(i)} * e^{h_{m}(\alpha)} - e^{h_{m}(\alpha)} * e^{h_{m}(\alpha)} }{ (\sum_{i=0}^c e^{h_{m}(i)})(\sum_{i=0}^c e^{h_{m}(i)}) }
$$
$$
\frac{\partial y_{m}(\alpha)}{\partial h_{m}(\alpha)} =
\frac{ e^{h_{m}(\alpha)}\left( \sum_{i=0}^c e^{h_{m}(i)}  - e^{h_{m}(\alpha)} \right) }{ \left( \sum_{i=0}^c e^{h_{m}(i)} \right)\left( \sum_{i=0}^c e^{h_{m}(i)} \right) }
$$
$$
\frac{\partial y_{m}(\alpha)}{\partial h_{m}(\alpha)} =
\frac{ y_{m}\left( \sum_{i=0}^c e^{h_{m}(i)}  - e^{h_{m}(\alpha)} \right) }{   \sum_{i=0}^c e^{h_{m}(i)} } =
y_{m}(\alpha)(1-y_{m}(\alpha))
$$
Y por el lado contrario, obteniendo la derivada parcial de la otra clasificación:
$$
\frac{\partial y_{m}(\alpha)}{\partial h_{m}(i)} =
\frac{\partial}{\partial h_{m}(i)} \left[ \frac{e^{h_{m}(\alpha)}}{\sum_{i=0}^c e^{h_{m}(i)}} \right] =
\frac{ \sum_{i=0}^c e^{h_{m}(i)} * e^{h_{m}(\alpha)} - e^{h_{m}(\alpha)} * e^{h_{m}(\alpha)} }{ (\sum_{i=0}^c e^{h_{m}(i)})(\sum_{i=0}^c e^{h_{m}(i)}) }
$$

$$
\sum_{i=0}^c e^{h_{m}(i)}
$$