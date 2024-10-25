#ComputacionCognitiva 

---
Las *redes neuronales artificiales* son modelos matemáticos simplificados de las neuronas biológicas que intentan simular las capacidades del cerebro en tareas como: visión, clasificación, control moto-sensorial, etc.

El conocimiento este se almacena dentro de los **parámetros** o **pesos** del modelo.

Una *neurona* es una unidad de procesamiento de información compuesta de tres elementos principales:
- Un conjunto de **sinápsis** o enlaces de conexión, donde cada una está caracterizada por un peso $w_i$. El cual, determina la fuerza de su conexión con otras neuronas.
- Un **sumador** para unir las señales de entrada, escaladas por su peso sináptico.
- Una **función de activación**, para limitar la señal de salida.

![[Pasted image 20241022205004.png]]
![[Pasted image 20241022204915.png]]
Cada neurona tiene tantas dendritas como haya neuronas en la capa anterior. Todas las entradas provenientes de la capa anterior se suman en la neurona receptora (en su *núcleo*). El núcleo de la neurona suma los valores con la función:
$$
h=\sum_{i}w_{i}x_{i}+b
$$
Dónde:
- $h$ es el valor de la neurona receptora.
- $x_{i}$ es cada entrada a la neurona.
- $w_{i}$ es el peso de cada entrada, que se modifica durante el entrenamiento.
- $b$ es el bias de la neurona.

La salida se ajusta a un rango de valores por medio de una **función de activación**, a fin de que la neurona se "*active*" bajo ciertas condiciones o para "*estabilizar*" la salida. De esta forma, las funciones de activación intentan representar la capacidad de las neuronas a reaccionar a diferentes estímulos, además de que ayuda a añadir un comportamiento **no lineal** al modelo.

![[Pasted image 20241024200234.png]]

Podemos definir una **capa** de neuronas entonces de la siguiente manera:

![[Pasted image 20241024201418.png]]
Donde cada elemento es una matriz de elementos:
$$
x 
$$

$$
h_{1} = w_{1}x+b_{1}
$$
$$
y_{1}=f(h_{1})
$$
