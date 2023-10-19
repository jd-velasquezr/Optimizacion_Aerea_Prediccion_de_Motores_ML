# Optimización aérea: Predicción de motores de avión con Machine Learning

# INTRODUCCIÓN:
Bienvenido al repositorio del Proyecto de Certificación de Inteligencia Artificial "Optimización aérea: Predicción de motores de avión con Machine Learning", una iniciativa que aborda la evaluación del rendimiento de aeronaves con el fin de determinar su idoneidad para misiones específicas. El rendimiento de una aeronave es un factor crítico en la aviación, y esta certificación utiliza técnicas de inteligencia artificial para analizar y predecir el tipo de motor de una aeronave basándose en sus especificaciones de vuelo.

# DATASET:
El conjunto de datos utilizado en este proyecto consta de información de 861 aeronaves y sus características, incluyendo velocidad máxima, velocidad de crucero, alcance, entre otros. No obstante, este dataset presenta desafíos, como valores faltantes, formatos de datos variados y unidades diversas para las características.

# CARACTERÍSTICAS:
El conjunto de datos incluye diversas características, como el modelo del avión, el nombre de la empresa fabricante, el tipo de motor, la potencia del eje, la velocidad máxima, la velocidad de pérdida en condiciones desfavorables, la capacidad de combustible, entre otros.

# DESARROLLO:
El proyecto comienza con la limpieza de datos, que implica eliminar columnas no relevantes para la clasificación del tipo de motor. Luego, se convierten las etiquetas de los motores en valores numéricos. El dataset limpio se guarda como "Aircraft_Handbook.csv."

El conjunto de datos se divide en 80% para entrenamiento y 20% para validación, con una distribución ponderada basada en los tipos de motor.

El proyecto también incluye un análisis de componentes principales (PCA) para reducir la dimensionalidad de las características, seguido de la evaluación de cinco clasificadores diferentes. Se utilizan métricas como precisión, F1-Score, Recall y el coeficiente de correlación de Matthews para evaluar el rendimiento de los clasificadores.

# Regresión Logística: 
Se exploran diferentes hiperparámetros, como la norma de la penalidad y el parámetro de regularización.

# Máquinas de Soporte Vectorial (SVM): 
Se consideran múltiples funciones de Kernel, parámetros de regularización y enfoques de clasificación OvA y OvO.

# K Vecinos más Cercanos (KNN): 
Se evalúan varios parámetros, incluyendo el número de vecinos, el tamaño de hoja y la métrica de distancia.

# Naive-Bayes Gaussiano: 
Se realiza una evaluación con configuraciones predeterminadas.

# Redes Neuronales (Perceptrón Multicapa): 
Se ajustan parámetros como el tamaño de las capas ocultas, funciones de activación, el solver, el parámetro alfa de regularización y la tasa de aprendizaje.

Este proyecto es una exploración en profundidad de la aplicación de técnicas de inteligencia artificial en la clasificación de tipos de motor de aeronaves. Se espera que sea una contribución interesante y valiosa para la comunidad de la inteligencia artificial y la aviación.

**RESULTADOS**

Se realizaron pruebas con 5 diferentes clasificadores utilizando el método gridsearch cv

- Regresión logística

![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/regresion%20logistica%20p.PNG)

- Máquinas de soporte vectorial (SVM)

![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/maquinas%20de%20sop%20vec%20p.PNG)

- KNN – K vecinos más cercanos

![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/KNN%20P.PNG)

- Naive bayes gausiano

![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/naive%20bayes%20p.PNG)

- Redes neuronales

![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/perceptron%20mp.PNG)

**CONCLUSIONES**

- Entre los cinco clasificadores puestos a prueba, los dos que mejor resultado obtuvieron fueron las máquinas de soporte vectorial (SVM) y las redes neuronales, con un valor de coeficiente de correlación de Matthews dede 0.9341 y 0.9352 respectivamente. En este caso, ambos clasificadores obtuvieron una calificación relativamente alta con el dataset de pruebas con un valor muy cercano entre sí, por lo que, ambas técnicas pueden ser opciones apropiadas para dar solución al problema de clasificación.
- En general, es preciso resaltar que los clasificadores utilizados para llevar a cabo la tarea de predicción (o clasificación) entre tres diferentes tipos de motor de aeronave, tuvieron un puntaje superior a 86 %, siendo entonces el que menor puntaje obtuvo fue el clasificador de Naive Bayes gaussiano, que a pesar de que su calificación es de un 87.1 % sigue siendo un método viable para el análisis del problema en cuestión, puesto que está a una diferencia de alrededor de un 6% con los mejores clasificadores experimentados en el desarrollo del proyecto.
- Durante el desarrollo de la fase de análisis por componentes principales, a pesar de que se hizo una reducción dimensional de 16 a 14 características, al momento de reducirla a 13 o inferior a esta, la suma de la varianza explicada se reducía a menos del 90%, por tanto, con esto, es preciso afirmar que el dataset en su mayoría cuenta con características mayormente independientes, tales que una gran parte describen más del 95% de la información del dataset en cuestión, por tanto, solo fue posible reducir 2 dimensiones del total de las características entregadas sin afectar en mayor medida la pérdida de datos o información que será utilizada para el proceso de clasificación en las diferentes técnicas implementadas.
- A pesar de que las redes neuronales implementadas en el desarrollo del proyecto (MLPC de la librería de scikit) obtuvieron el mejor resultado, en efecto, son las que más tardan en finalizar el proceso de búsqueda por rejilla a través de validación cruzada para el mejor clasificador, tomando más de 3 minutos en procesar, adicionalmente, el tiempo que tarda en entrenar es de 248.57 s, lo que quiere decir que es un método computacionalmente exigente y lento para utilizar en aplicaciones con máquinas de hardware limitado, por tanto, debe requerirse pruebas previas para evaluar su viabilidad en proyectos con estas características.
