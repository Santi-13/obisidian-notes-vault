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
Cada neurona tiene tantas dendritas como haya neuronas en la capa anterior. Todas las entradas provenientes de la capa anterior se suman en la neurona receptora (en su *núcleo*), siendo modificadas por un peso $w_{j}$ donde $j$ es el número de entradas, este peso es el que modificamos durante el entrenamiento del modelo. El nù