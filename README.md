# Clasificación de la calidad del vino mediante aprendizaje automático con base en características fisicoquímicas

Este proyecto forma parte de la materia Introducción a la Metodología de Ciencia de Datos de la Maestría en Ciencia de Datos. El objetivo del mismo es emplear la metodología *Cross-Industry Process for Data Mining* (CRISP-DM) en el abordaje de una problemática particular. Se utilizará una base de datos con los valores de múltiples propiedades fisicoquímicas de distintos vinos, junto con su clasificación en términos de calidad. A partir de estos datos, siguiendo las pautas marcadas en CRISP-DM, se entrenará y validará un modelo para predecir la calidad de un vino con base en sus características. 

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
