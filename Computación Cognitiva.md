#ComputacionCognitiva
#### Conceptos Básicos -
---
**Aprendizaje automático (Machine Learning).** Es un área de las ciencias de la computación que "da a las maquinas la habilidad de aprender una tarea sin necesidad de ser programadas explícitamente para ello" (Arthur Samuel).

**Sistemas Inteligentes.** Es aquel capaz de "adaptarse" a cambios en su entorno, modificando su comportamiento para seguir pudiendo hacer su tarea, así como mejorarlo a través de la experiencia.

> Se dice que un *sistema A* aprendió de la *experiencia E* a realizar una *tarea T* con medida de *rendimiento P*, si su rendimiento en la realización de la *tarea T* (medido por la *variable P*) mejoró a través de la *experiencia E*.

**Sistema.** Corresponde a un modelo matemático que genera una salida a partir de un conjunto de datos de entrada.

**Tarea.** Corresponde al proceso de abstracción de la información de entrada para producir una respuesta de salida o deseada.

**Error.** Es una función o medida cuantitativa que permite medir el desempeño del modelo en la realización de la tarea.

**Experiencia.** El conocimiento adquirido por el sistema a través del entrenamiento, es normalmente almacenado en los parámetros internos del modelo.

**Plasticidad.** Es la capacidad que tiene un modelo para deformarse y adaptarse a la salida deseada.

**Aprendizaje Supervisado.** Se aprende de un maestro o ejemplos cuyo comportamiento deseado se conoce.
1. El maestro y el modelo son sometidos a una entrada o vector de entrenamiento, produciendo respuestas separadas.
2. El maestro provee la respuesta deseada y se compara para producir la señal de error.
3. Se ajustan los parámetros del modelo bajo la influencia del vector de entrenamiento y la señal de error.
4. Se repite iterativamente.

![[Pasted image 20240919200652.png]]
**Aprendizaje no Supervisado.** Aprende de la información directamente sin una respuesta esperada.
1. El modelo es sometido a datos desconocidos.
2. Intenta agrupar aquellos datos con características similares en *clases* o *clústers*.
3. Eventualmente aprende a clasificar los datos en función de sus características, volviéndose más robusto conforme aumentan la cantidad de datos.

![[Pasted image 20240919201004.png]]
**Aprendizaje Reforzado.** Aprender a prueba y error de la interacción con la información o el entorno.
1. El modelo es sometido a datos desconocidos, produciendo una *interacción*.
2. Una función adicional llamada *función de costo* es creada para evaluar la interacción del modelo, premiando aquellas acciones hechas correctamente y castigando a aquellas hechas incorrectamente.
3. Eventualmente, el modelo aprende a interactuar con la información por medio de la *prueba y error*.

![[Pasted image 20240919201204.png]]
#### Tareas de Aprendizaje -
---
**Clasificación.** El modelo produce una salida discreta. Clasifica datos según sus características.
![[Pasted image 20240919204207.png]]
**Regresión.** El modelo produce una salida continua, que puede o no ser variante en el tiempo. 
![[Pasted image 20240919204225.png]]
**Transcripción.** El modelo realiza identificación de señales complejas, como reconocimiento de audio o video.  
### Flashcards -
---
¿Qué es aprendizaje automático?:: Es un área que "da a las maquinas la habilidad de aprender una tarea sin necesidad de ser programadas explícitamente para ello" (Arthur Samuel).
<!--SR:!2024-10-05,9,250-->
<!--SR:!2024-09-22,3,250-->
¿Qué es un sistema inteligente?:: Aquel que puede "adaptarse" a cambios en su entorno, modificando su comportamiento para seguir pudiendo hacer su tarea, así como mejorarlo a través de la experiencia.
<!--SR:!2024-09-28,2,230-->
¿Qué es plasticidad?:: Es la capacidad que tiene un modelo a deformarse para adaptarse a la salida deseada.
<!--SR:!2024-09-28,2,230-->
¿Qué tipos de aprendizaje hay y de que tratan?
?
**Aprendizaje Supervisado.** Se aprende de un maestro o ejemplos cuyo comportamiento deseado se conoce.
**Aprendizaje no Supervisado.** Aprende de la información directamente sin una respuesta esperada.
**Aprendizaje Reforzado.** Aprender a prueba y error de la interacción con la información o el entorno.
<!--SR:!2024-09-29,2,210-->
