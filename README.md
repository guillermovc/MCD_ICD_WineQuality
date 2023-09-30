# Clasificación de la calidad del vino mediante aprendizaje automático con base en características fisicoquímicas

Este proyecto es parte del curso "Introducción a la Metodología de Ciencia de Datos" de la Maestría en Ciencia de Datos. Su objetivo principal es aplicar la metodología CRISP-DM (*Cross-Industry Process for Data Mining*) para abordar un problema específico. Para ello, utilizaremos una base de datos bien conocida que contiene valores de múltiples propiedades fisicoquímicas de diferentes vinos, junto con su clasificación en términos de calidad. Siguiendo las directrices de CRISP-DM, entrenaremos y validaremos un modelo con el fin de predecir la calidad de un vino basándonos en sus características.

## Integrantes del equipo
* Axel Castro Fonseca
* José Carlos Barreras Maldonado
* Guillermo Velazquez Coronado
* Misael Gonzáles Soria

## CRISP-DM

CRISP-DM, abreviatura de *Cross-Industry Process for Data Mining*, es una metodología ampliamente reconocida en el campo de la minería de datos que proporciona un marco estructurado para abordar proyectos de minería de datos de manera efectiva. Este enfoque se basa en un proceso jerárquico que comprende varias fases, desde la comprensión del negocio hasta la implementación de soluciones basadas en datos. A continuación, se describen las principales fases de CRISP-DM:

| Fase                    | Descripción                                                                                                                                                   |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Comprensión del Negocio | En esta fase inicial, se evalúan los objetivos y recursos disponibles desde una perspectiva empresarial. Se define el objetivo de la minería de datos y se crea un plan de proyecto.                 |
| Comprensión de los Datos | Esta fase implica la recopilación y exploración de datos de diversas fuentes, así como la verificación de la calidad de los datos.                                      |
| Preparación de los Datos | Aquí, se seleccionan los datos pertinentes, se lleva a cabo la limpieza de datos y se pueden crear atributos adicionales según sea necesario para el modelado.     |
| Modelado                | En esta etapa, se seleccionan y aplican técnicas de modelado para construir modelos predictivos o descriptivos. La elección de técnicas depende del problema y los datos disponibles. |
| Evaluación              | Los resultados del modelo se comparan con los objetivos empresariales y se evalúa su calidad. Se determinan las acciones a seguir y se revisa el proceso en general.                |
| Despliegue              | La fase de despliegue implica la implementación de los resultados del modelo en la práctica. Puede incluir la planificación, el monitoreo y el mantenimiento de soluciones basadas en datos. |

CRISP-DM sigue siendo una metodología estándar en proyectos de minería de datos debido a su enfoque estructurado y su capacidad para guiar a los equipos a lo largo de todas las etapas críticas de un proyecto de análisis de datos.

<p align="center">
  <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/eba4fea1-b953-4eb7-8331-3b816e8fcb9f" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 1: Metodología CRISP-DM. Imagen tomada de Plotnikova et al., 2022.</em>
</p>

### Comprensión del negocio 

El incremento en la popularidad del vino presenta oportunidades significativas, pero también desafíos. La certificación de vinos y la evaluación de su calidad son elementos clave en este contexto. La certificación no solo garantiza la autenticidad del vino y previene la adulteración ilegal, sino que también asegura la calidad para el mercado del vino. La evaluación de la calidad del vino es un componente crítico, ya que puede ayudar a mejorar el proceso de producción y permitir la estratificación de los vinos en categorías, lo que resulta útil para la fijación de precios y la toma de decisiones.

La evaluación de la calidad del vino a menudo implica la realización de pruebas fisicoquímicas y sensoriales. Sin embargo, la evaluación del sabor es un desafío, ya que las percepciones sensoriales humanas son complejas y la relación entre los análisis fisicoquímicos y las evaluaciones sensoriales no siempre es evidente.

Este proyecto se basa en la aplicación de técnicas de minería de datos bajo el esquema CRISP-DM para predecir las preferencias de sabor del vino. Se utiliza un conjunto de datos amplio que incluye muestras de vino de la compañia *vinho verde*, tanto blanco como tinto, de Portugal. El enfoque principal es entrenar un modelo que pueda predecir la calidad del vino en función de sus propiedades fisicoquímicas y sensoriales.

La capacidad de predecir la calidad del vino con precisión puede tener un valor sustancial para los catadores y enólogos, mejorando la velocidad y precisión de sus evaluaciones. Además, el conocimiento generado puede utilizarse para optimizar el proceso de producción y ajustar las estrategias de comercialización, lo que puede tener un impacto positivo en la rentabilidad.

La relevancia de este proyecto en el contexto de Portugal se manifiesta en su posición destacada en el mercado del vino. Esta relevancia puede extrapolarse a otros países productores de vino, como México, y a nivel global. La capacidad de mejorar la calidad del vino y adaptarse a las preferencias cambiantes de los consumidores es de interés en todo el mundo. Además, la metodología de minería de datos aplicada aquí puede ser relevante para una variedad de industrias más allá del sector del vino, lo que amplía su alcance y aplicabilidad.

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/56eb3842-4cb9-48a6-8b9b-e45722f7cded" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 2: Publicidad de Vinho Verde. Imagen tomada de Puckette, 2019.</em>
</p>

### Comprensión de los datos

Los datos que utilizamos contienen información sobre las variantes de vino "Vinho Verde" de Portugal, incluyendo tanto vinos tintos como blancos, recolectados de mayo del 2004 a febrero del 2006. La captura de datos se realizó mediante un sistema computarizado que gestionaba automáticamente el proceso de análisis de muestras de vino desde las solicitudes del productor hasta el análisis sensorial y de laboratorio. Cada muestra fue evaluada por un mínimo de tres catadores sensoriales y las evaluaciones se realizaron a ciegas para evitar sesgos. Las puntuaciones se calificaron en una escala del 0 (muy malo) al 10 (excelente). La variable *quality* en ambos conjuntos de datos se calculó como el promedio de estas evaluaciones sensoriales.

Para este proyecto los datos se obtuvieron del siguiente [enlace](https://archive.ics.uci.edu/dataset/186/wine+quality), en donde están almacenados en el archivo *wine-quality.zip*. Estos datos conforman un total de 6497 instancias u observaciones y 11 carácterísticas. Debido a cuestiones de privacidad y logística, solo se proporcionan variables físico-químicas (entradas) y la ya mencionada variable de calidad (la salida), sin información sobre tipos de uva, marca de vino, precio de venta, etc. Las clases están ordenadas y no están equilibradas; hay muchas más muestras de vinos de calidad media que de muy alta o muy baja calidad. Se pueden utilizar algoritmos de detección de valores atípicos para identificar los pocos vinos excelentes o pobres. También, no se sabe si todas las variables de entrada son relevantes, por lo que podría ser interesante probar métodos de selección de características. No hay valores faltantes en los datos.

| Variable                | Rol            | Tipo      | Descripción                                                            | Valores Faltantes |
|-------------------------|-----------------|-----------|------------------------------------------------------------------------|-------------------|
| fixed_acidity           | Característica | Continua  | Ácidos orgánicos de baja volatilidad inherentes a la muestra.          | No                |
| volatile_acidity        | Característica | Continua  | Ácidos orgánicos de cadena corta, especialmente ácido acético.         | No                |
| citric_acid             | Característica | Continua  | Ácido cítrico usado como suplemento ácido en la fermentación.          | No                |
| residual_sugar          | Característica | Continua  | Azúcares naturales que quedan en el vino después de la fermentación.   | No                |
| chlorides               | Característica | Continua  | Sales con cloro que contribuyen al sabor, añadiendo un toque salado.   | No                |
| free_sulfur_dioxide     | Característica | Continua  | Dióxido de azufre que no está unido químicamente a otras sustancias.   | No                |
| total_sulfur_dioxide    | Característica | Continua  | Total de dióxido de azufre, incluyendo el unido a otras sustancias.     | No                |
| density                 | Característica | Continua  | Masa por unidad de volumen de vino o mosto a temperatura fija.           | No                |
| pH                      | Característica | Continua  | Medida de acidez o alcalinidad de una solución.                          | No                |
| sulphates               | Característica | Continua  | Sulfitos o dióxido de azufre como conservante añadido en el vino.       | No                |
| alcohol                 | Característica | Continua  | Porcentaje de alcohol en el vino.                                        | No                |
| quality                 | Objetivo        | Entero    | Puntuación de calidad del vino, promedio de evaluaciones sensoriales en una escala de 0 a 10. | No                |

Antes de profundizar en el análisis de los datos, es importante destacar que se consideraron por separado los vinos tintos y blancos debido a sus diferencias en sabor y composición. Con esto en mente, se construyeron dos conjuntos de datos: uno con 1599 ejemplos tintos y otro con 4898 blancos. Por simplificación, los pasos presentados a partir de este punto correponden únicamente al conjunto de datos de vino tinto. 

Primero, verificamos que nuestros datos estén completos y no contengan valores faltantes:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/efc2cffb-5a8c-4cd7-b4c4-84507dbfac21" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 3: Análisis de valores perdidos por característica.</em>
</p>

Como siguiente paso obtenemos los estadísticos básicos de cada variable en nuestros datos: 

| index | fixed acidity | volatile acidity | citric acid | residual sugar | chlorides | free sulfur dioxide | total sulfur dioxide | density | pH  | sulphates | alcohol | quality |
|-------|---------------|-------------------|-------------|----------------|-----------|--------------------|----------------------|---------|-----|-----------|---------|---------|
| count | 1599.0        | 1599.0            | 1599.0      | 1599.0         | 1599.0    | 1599.0             | 1599.0               | 1599.0  | 1599.0 | 1599.0    | 1599.0  | 1599.0  |
| mean  | 8.3196        | 0.5278            | 0.2710      | 2.5388         | 0.0875    | 15.8749            | 46.4678              | 0.9967  | 3.3111 | 0.6581    | 10.4230 | 5.6360  |
| std   | 1.7411        | 0.1791            | 0.1948      | 1.4099         | 0.0471    | 10.4602            | 32.8953              | 0.0019  | 0.1544 | 0.1695    | 1.0657  | 0.8076  |
| min   | 4.6           | 0.12              | 0.0         | 0.9            | 0.012     | 1.0                | 6.0                  | 0.9901  | 2.7400 | 0.3300    | 8.4     | 3.0     |
| 25%   | 7.1           | 0.3900            | 0.0900      | 1.9            | 0.070     | 7.0                | 22.0                 | 0.9956  | 3.2100 | 0.5500    | 9.5     | 5.0     |
| 50%   | 7.9           | 0.5200            | 0.2600      | 2.2            | 0.079     | 14.0               | 38.0                 | 0.9968  | 3.3100 | 0.6200    | 10.2    | 6.0     |
| 75%   | 9.2           | 0.6400            | 0.4200      | 2.6            | 0.090     | 21.0               | 62.0                 | 0.9978  | 3.4000 | 0.7300    | 11.1    | 6.0     |
| max   | 15.9          | 1.5800            | 1.0         | 15.5           | 0.611     | 72.0               | 289.0                | 1.0037  | 4.0100 | 2.0       | 14.9    | 8.0     

A continuación, evaluamos la distribución de las calidades del vino en el conjunto de datos:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/d6f4bba2-3d25-473b-908c-f19c836d25ed" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 4: Frecuencia de cada calidad de vino.</em>
</p>

Tal como se mencionó anteriormente, se observa que la presencia de valores extremos es mínima, con una mayor abundancia de vinos de calidad intermedia.

Posteriormente, analizamos la dispersión de las características para las distintas calidades de vino:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/fb4f3395-6dfd-421b-b4cc-b6876e1def8e" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 5: Boxplots con los valores de cada una de las características para los vinos de las distintas calidades.</em>
</p>

Finalmente, obtenemos la matriz de correlación para comprender mejor las relaciones entre las características:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/88bd843f-0a99-4ecb-a93d-d43fcde7ea43)" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 6: Matriz de correlación.</em>
</p>

Este análisis inicial es el punto de partida esencial para la preparación de los datos. Proporciona una visión general de nuestros datos de vino tinto, ayudándonos a comprender su estructura y a identificar tendencias clave. Esta comprensión previa es crucial antes de abordar la limpieza y transformación de los datos en la siguiente etapa del proyecto.

### Preparación de los datos  

Después de haber realizado un análisis exhaustivo de la situación actual de nuestros datos, avanzamos con la etapa de preparación de los mismos. Esta fase, en el marco de la metodología CRISP-DM, tiene como objetivo garantizar que los datos estén en el formato adecuado y sean apropiados para su análisis posterior. Esto implica, entre otras cosas, la limpieza de datos, la selección de variables relevantes y la transformación de los datos según sea necesario. En esta etapa, generalmente se abordan problemas relacionados con los datos faltantes, pero como se demostró en la etapa anterior, en este caso no es necesario realizar esta tarea. La preparación de los datos sienta las bases esenciales para el modelado de datos y es crucial para obtener resultados precisos y significativos en cualquier proyecto de minería de datos.

Como primer paso en nuestra fase de preparación de datos, abordamos la desigual distribución de las distintas calidades de vino en nuestro conjunto. Como se evidenció anteriormente, carecemos de observaciones de las calidades más extremas, es decir, 1, 2 y 9, y observamos una escasez de muestras para las calidades 3, 4 y 8. En contraste, la mayoría de las instancias se concentran en las calidades 5, 6 y 7.

Para mitigar esta disparidad y mejorar la capacidad de generalización de nuestro modelo, optamos por crear tres nuevas categorías ordinales: "low" (baja calidad, que engloba las calidades 3 y 4), "med" (calidad media, que incluye las calidades 5 y 6) y "high" (alta calidad, que comprende las calidades 8 y 9). Si bien esta solución implica una disminución en la granularidad de nuestras predicciones al agrupar las calidades en estas tres categorías, contribuye a equilibrar las proporciones entre las distintas calidades en nuestros datos. A su vez, para poder llevar a cabo el entrenamiento del modelo sin problemas, a cada una de las nuevas categorías le asignamos un valor numerico, tal como se muestra en la siguiente tabla: 

| quality | quality_cat | quality_ord |
|---------|------------|------------|
| 3       | low        | -1         |
| 4       | low        | -1         |
| 5       | med        | 0          |
| 6       | med        | 0          |
| 7       | high       | 1          |
| 8       | high       | 1          |

Una vez hecha esta transformación, volvemos a analizar la frecuencia con la que aparece cada una de las nuevas categorías en nuestros datos:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/3e53134c-7b86-4be5-a95f-6fee30085d09" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 7: Frecuencia de cada nueva categoría de calidad de vino.</em>
</p>

Este enfoque nos permitirá abordar de manera más efectiva el reto de modelar la calidad del vino y ofrecerá una mayor estabilidad en las predicciones al considerar estas categorías amplias en lugar de calidades individuales.

Para continuar con la preparación de datos, calculamos nuevamente la matriz de correlación con nuestras nuevas categorías:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/4006789f-eba7-4674-a2e2-b7853c453e3f" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 8: Matriz de correlación con las nuevas categorías de calidad.</em>
</p>

Observamos que algunas variables tienen una correlación bastante débil con la variable objetivo *quality_ord*. Establecemos un valor umbral de correlación de |0.1| y eliminamos todas las variables cuya correlación con *quality_ord* no supere este umbral. También identificamos que las variables *fixed_acidity* y *citric_acid* presentan una correlación de 0.67 entre ellas. Dado que están altamente correlacionadas y ambas llevan inormación relacionada con la acidez del vino, podemos conservar solo una de estas dos variables sin perder información explicativa en relación con *quality*. Para tomar esta decisión, comparamos la correlación de cada una con la variable objetivo y seleccionamos la que tenga el nivel de correlación más alto. En este caso, la variable *citric_acid* obtuvo el valor más alto, que es 0.23. Por lo tanto, eliminamos *fixed_acidity* y obtenemos una nueva matriz de correlación:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/9052b675-2f05-40d1-b16b-edd59d91bb5c" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 9: Matriz de correlación sin variables pobremente correlacionadas con quality, ni altamente correlacionadas entre sí.</em>
</p>

Luego, procedemos a analizar nuevamente la dispersión de las variables en nuestro nuevo conjunto de datos:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/861132ac-b74a-41eb-8885-41bd50d5caeb" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 10: Boxplots de nuestras características filtradas y transformadas.</em>
</p>

Observando estas gráficas podemos identificar claramente la presencia de valores atípicos u *outliers* en nuestros datos. Para su eliminación probamos el algoritmo *Local Outlier Factor* (LOF). El LOF se basa en la idea de que los valores atípicos tienen una densidad local significativamente menor en comparación con sus vecinos. Este algoritmo calcula un "Factor de Densidad Local" para cada punto de datos al comparar su densidad local con la densidad local de sus vecinos. Los puntos con un factor LOF significativamente mayor que 1 se consideran valores atípicos, lo que significa que tienen una densidad local más baja en comparación con sus vecinos. LOF es especialmente útil para identificar valores atípicos que pueden no ser obvios en un contexto global.

El resultado de aplicar este algoritmo fue que 56 observaciones fueron identificadas como *outliers*. A continuación se presenta la distribución de nuestras variables antes y después de la eliminación de estos valores atípicos:

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/50ea391b-4525-4ecc-b08e-1f82d4e67b0d" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 10: Boxplots de nuestras características filtradas antes y después de eliminar valores atípicos.</em>
</p>

Con nuestros datos preparados, tras haber eliminado variables poco relevantes,  valores atípicos y tras haber transformado nuestro datos, estamos listos para ingresar a la fase de modelado. En la próxima etapa, desarrollaremos y evaluaremos modelos para comprender la calidad del vino tinto y sus predictores clave. Exploraremos diversas técnicas de modelado en busca de las más efectivas en la predicción de la calidad del vino.

### Modelado 

Para abordar la tarea de predecir la calidad del vino, hemos seleccionado el modelo de *Random Forest*. Este método es una técnica de ensamblaje que combina múltiples árboles de decisión independientes. Cada árbol es entrenado en un subconjunto aleatorio de los datos y utiliza una selección aleatoria de características. Cuando se realiza una predicción, cada árbol emite su propia clasificación y, finalmente, la clase más votada se convierte en la predicción del modelo. Esta estrategia de voto mayoritario y aleatorización en la selección de datos y características mejora significativamente la precisión y la capacidad de generalización del modelo.

Para llevar a cabo el entrenamiento de nuestro modelo, dividimos nuestros datos en dos conjuntos: uno de entrenamiento, que representa el 90% de los datos (1395 muestras), y otro de validación, que comprende el 10% restante (155 muestras). A continuación, aplicamos el método de validación cruzada de k iteraciones con k=5. En este proceso, el conjunto de entrenamiento se divide en cinco subconjuntos excluyentes. Luego, se realizan cinco iteraciones, en cada una de las cuales uno de estos subconjuntos se utiliza como conjunto de prueba, mientras que los cuatro restantes se utilizan como subconjuntos de entrenamiento. Esto nos permite evaluar el rendimiento del modelo en cinco configuraciones diferentes, obteniendo un promedio de precisión y error en el conjunto de entrenamiento. La validación cruzada de k iteraciones nos proporciona una evaluación más robusta y confiable de la capacidad de generalización de nuestro modelo.

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/0e5d8fa1-f57e-41b6-9261-30a79aa3835c" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 12: Proceso de entrenamiento y validación del modelo. Imagen tomada de Caughlin, 2020.</em>
</p>

<p align="center">
   <img src="https://github.com/guillermovc/MCD_ICD_WineQuality/assets/90294947/5ef4ce1f-fd42-45fb-9e42-6abfc9451c22" alt="Descripción de la imagen">
</p>

<p align="center">
  <em>Figura 13: Validación cruzada con K iteraciones. Imagen tomada de Shen, 2020.</em>
</p>

### Evaluación

En esta sección, evaluaremos el desempeño de nuestro modelo de Random Forest en la tarea de predecir la calidad del vino tinto. Para esto, utilizaremos una herramienta fundamental conocida como la "matriz de confusión". Esta matriz es una tabla que nos brinda información sobre el rendimiento de nuestro modelo al comparar sus predicciones con los valores reales del conjunto de validación. Cabe recordar que los valores asociados a cada categoría de calidad son: -1 (baja calidad, que engloba las calidades 3 y 4), 0 (calidad media, que incluye las calidades 5 y 6) y 1 (alta calidad, que comprende las calidades 8 y 9). 

|              | Predicción -1 | Predicción 0 | Predicción 1 |
|--------------|---------------|--------------|--------------|
| Real -1      |       0       |      6       |      0       |
| Real 0       |       1       |     122      |      5       |
| Real 1       |       0       |     15       |      6       |

La matriz de confusión se compone de tres partes principales: verdaderos positivos (VP), verdaderos negativos (VN), falsos positivos (FP) y falsos negativos (FN). Estos elementos nos ayudan a medir la capacidad del modelo para clasificar correctamente las muestras en diferentes categorías de calidad. *Accuracy* o exactitud, precisión, *recall* o sensibilidad y puntuación F1 son métricas clave que se derivan de la matriz de confusión y nos brindan información detallada sobre el rendimiento del modelo. 

- Exactitud (E): Mide la proporción de predicciones correctas realizadas por el modelo en relación con el total de predicciones. Es una métrica global que refleja la capacidad del modelo para clasificar correctamente todas las categorías. Una alta exactitud indica que el modelo tiene un buen rendimiento general en la clasificación de las muestras, independientemente de su etiqueta. Su ecuación es: $$E = \frac{VP + VN}{VP + VN + FP + FN}$$

- Precisión (P): Mide la proporción de predicciones positivas realizadas por el modelo que fueron realmente correctas. Refleja la capacidad del modelo para no etiquetar incorrectamente ejemplos negativos como positivos. Una alta precisión indica que el modelo tiene una baja tasa de falsos positivos y, por lo tanto, es preciso en la clasificación de las muestras positivas. Su ecuación es: $$P = \frac{VP}{VP + FP}$$

- Sensibilidad (S): Mide la proporción de ejemplos positivos reales que el modelo predijo correctamente. Refleja la capacidad del modelo para identificar con precisión todos los ejemplos positivos. Una alta sensibilidad indica que el modelo tiene una baja tasa de falsos negativos y es capaz de capturar la mayoría de las muestras positivas. Su ecuación es: $$S = \frac{VP}{VP + FN}$$

- Puntuación F1: Es una métrica que combina precisión y sensibilidad en un solo valor, permitiendo equilibrar la importancia de estas dos métricas. Es especialmente útil cuando las clases están desequilibradas en el conjunto de datos. La puntuación F1 alcanza su valor máximo de 1 cuando tanto la precisión como la sensibilidad son perfectas. Su ecuación es: $$F1 = \frac{2 \cdot (P \cdot S)}{P + S}$$

En cuanto al cálculo de estas métricas para cada una de las categorías de nuestros datos, los resultados se detallan en la siguiente tabla:

| Categoría  | Precisión | Sensibilidad |   F1   | Observaciones |
|------------|-----------|--------------|--------|---------------|
|     -1     |   0.00    |     0.00     |  0.00  |       6       |
|      0     |   0.85    |     0.95     |  0.90  |      128      |
|      1     |   0.55    |     0.29     |  0.37  |       21      |

Además, se calculó un promedio ponderado de estas métricas, que tiene en cuenta el desbalance existente en la cantidad de datos de cada categoría:

|    Métrica   | Promedio ponderado |
|--------------|-------|
|   Presición  | 0.78  |
| Sensibilidad | 0.83  | 
|  F1 |  0.79  |        

Finalmente, la métrica global de exactitud arrojó un valor de 0.83, lo que indica la proporción de predicciones correctas en relación con el total de observaciones.

Nuestro modelo muestra un rendimiento aceptable en la tarea de clasificación de calidad de vinos, con una exactitud global del 83%. Sin embargo, es esencial tener en cuenta la desigualdad en la cantidad de observaciones entre las categorías. En el caso de la calidad más baja (-1) y la calidad más alta (1), debido a su menor representación en el conjunto de datos, el modelo enfrenta desafíos para clasificar con precisión estas categorías. La precisión y la sensibilidad para estas categorías extremas son más bajas en comparación con la categoría intermedia (0).

Para las categorías de calidad extremas, se observa que la métrica F1, que combina precisión y sensibilidad, tiene un valor más bajo. Esto indica que el modelo lucha por encontrar un equilibrio entre etiquetar correctamente los ejemplos de estas categorías y evitar falsos positivos. Dado que las categorías extremas son menos representadas en los datos, el modelo puede tener dificultades para aprender patrones significativos.

Para futuros trabajos, es crucial abordar la desigualdad en la distribución de clases. Esto podría lograrse mediante la recopilación de más datos para las categorías menos representadas, el uso de técnicas de balanceo de clases o la exploración de algoritmos de clasificación que manejen mejor conjuntos de datos desequilibrados. Además, la selección cuidadosa de características y la optimización de hiperparámetros podrían contribuir a mejorar el rendimiento del modelo, especialmente en la clasificación de categorías extremas. 

### Implantación

En la fase de implantación, consideramos cómo nuestros resultados pueden ser aplicados en un contexto empresarial. A pesar de ser un proyecto académico, sus hallazgos pueden tener un impacto significativo en la industria del vino y en otros sectores relacionados.

La capacidad de predecir la calidad del vino con precisión a partir de sus características fisicoquímicas tiene el potencial de mejorar la toma de decisiones en la producción y comercialización de vinos. Las bodegas y productores pueden utilizar modelos similares para evaluar y optimizar sus procesos, lo que puede resultar en vinos de mayor calidad y una mejor respuesta a las necesidades cambiantes del mercado.

Aunque nuestro enfoque se centró en datos obtenidos de la industria vinícola portuguesa, los principios y técnicas de minería de datos pueden aplicarse en diversas industrias para resolver problemas similares. Por lo tanto, estos resultados académicos pueden servir como punto de partida para futuras aplicaciones prácticas en el mundo empresarial, contribuyendo a la mejora de productos y procesos en un mercado global altamente competitivo.

## Referencias

- Caughlin, D. (2020). k-Fold Cross-Validation [Video]. YouTube. https://www.youtube.com/watch?app=desktop&v=kituDjzXwfE
- Cortez, P., Cerdeira, A., Almeida, F., Matos, T., & Reis, J. (2009). Modeling wine preferences by data mining from physicochemical properties. Decision Support Systems, 47(4), 547-553. https://doi.org/10.1016/j.dss.2009.05.016
- Laura-Ochoa, L. (2019). Evaluación de Algoritmos de Clasificación utilizando Validación Cruzada. Proceedings of the 17th LACCEI International Multi-Conference for Engineering, Education, and Technology: “Industry, Innovation, and Infrastructure for Sustainable Cities and Communities”. The 17th LACCEI International Multi-Conference for Engineering, Education, and Technology: “Industry, Innovation, and Infrastructure for Sustainable Cities and Communities”. https://doi.org/10.18687/LACCEI2019.1.1.471
- Puckette, M. (2019). Beginner’s Guide To Vinho Verde Wine. Wine Folly. https://winefolly.com/deep-dive/vinho-verde-the-perfect-poolside-wine-from-portugal/
- Parmar, A., Katariya, R., & Patel, V. (2019). A Review on Random Forest: An Ensemble Classifier. En J. Hemanth, X. Fernando, P. Lafata, & Z. Baig (Eds.), International Conference on Intelligent Data Communication Technologies and Internet of Things (ICICI) 2018 (Vol. 26, pp. 758-763). Springer International Publishing. https://doi.org/10.1007/978-3-030-03146-6_86
- Plotnikova, V., Dumas, M., & Milani, F. P. (2022). Applying the CRISP-DM data mining process in the financial services industry: Elicitation of adaptation requirements. Data & Knowledge Engineering, 139, 102013. https://doi.org/10.1016/j.datak.2022.102013
- Schröer, C., Kruse, F., & Gómez, J. M. (2021). A Systematic Literature Review on Applying CRISP-DM Process Model. Procedia Computer Science, 181, 526-534. https://doi.org/10.1016/j.procs.2021.01.199
- Shen, Z. (2020). 3 min de Machine Learning: Cross Vaildation. Zitao's Web. https://zitaoshen.rbind.io/project/machine_learning/machine-learning-101-cross-vaildation/
