# Clasificación de la calidad del vino mediante aprendizaje automático con base en características fisicoquímicas

Este proyecto forma parte de la materia Introducción a la Metodología de Ciencia de Datos de la Maestría en Ciencia de Datos. El objetivo del mismo es emplear la metodología *Cross-Industry Process for Data Mining* (CRISP-DM) en el abordaje de una problemática particular. Se utilizará una reconocida base de datos con los valores de múltiples propiedades fisicoquímicas de distintos vinos, junto con su clasificación en términos de calidad. A partir de estos datos, siguiendo las pautas marcadas en CRISP-DM, se entrenará y validará un modelo para predecir la calidad de un vino con base en sus características. </p>

## Integrantes del equipo
* Axel Castro Fonseca
* José Carlos Barreras Maldonado
* Guillermo Velazquez Coronado
* Misael Gonzáles Soria

## CRISP-DM

CRISP-DM, abreviatura de *Cross-Industry Process for Data Mining*, es una metodología ampliamente reconocida en el campo de la minería de datos. Proporciona un marco estructurado para abordar proyectos de minería de datos de manera efectiva. Este enfoque se basa en un proceso jerárquico que comprende varias fases, desde la comprensión del negocio hasta la implementación de soluciones basadas en datos. A continuación, se presentan las fases clave de CRISP-DM y sus descripciones:

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
  <em>Figura 1: Metodología CRISP-DM</em>
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
  <em>Figura 2: Publicidad de Vinho Verde tomada de: https://winefolly.com/deep-dive/vinho-verde-the-perfect-poolside-wine-from-portugal/</em>
</p>

### Comprensión de los datos

### Preparación de los datos

### Modelado 

### Evaluación

### Implantación

## Referencias

- Plotnikova, V., Dumas, M., & Milani, F. P. (2022). Applying the CRISP-DM data mining process in the financial services industry: Elicitation of adaptation requirements. Data & Knowledge Engineering, 139, 102013. https://doi.org/10.1016/j.datak.2022.102013
- Schröer, C., Kruse, F., & Gómez, J. M. (2021). A Systematic Literature Review on Applying CRISP-DM Process Model. Procedia Computer Science, 181, 526-534. https://doi.org/10.1016/j.procs.2021.01.199








# Proyecto
- Contar que usaremos K-Fold
- usando la metodología Crisp-DM
- subconjuntos de entrenamiento, validación y prueba

# Algo más que crean que debe ir en el `readme` o algun reordenamiento.

# Docker
Si gustan dejenme esta parte a mi (Guillermo).  
Aquí explicaré como utilizar Docker para bajar un entorno listo en el que puedas correr la libreta jupyter con tu navegador.
  
**Vayan incluyendo librerias que usen y sepan que no son de la librería estandar en el archivo `requirements.txt`**
