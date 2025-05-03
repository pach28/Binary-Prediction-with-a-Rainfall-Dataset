# Binary Prediction with a Rainfall Dataset | Kaggle Competition Analysis

[![Kaggle](https://kaggle.com/static/images/site-logo.svg)](https://www.kaggle.com/competitions/playground-series-s3e16)

Este repositorio contiene el análisis y los notebooks desarrollados para mi participación en la competencia "[Binary Prediction with a Rainfall Dataset](https://www.kaggle.com/competitions/playground-series-s3e16)" en Kaggle. El objetivo de la competencia fue predecir si lloverá o no al día siguiente, basándose en diversas mediciones meteorológicas.

## Objetivo de la Competencia

El desafío principal consistió en construir un modelo de clasificación binaria capaz de predecir con precisión la ocurrencia de lluvia (Sí/No) utilizando un conjunto de datos con diversas variables meteorológicas. Esto implicó el análisis de las relaciones entre las variables, el manejo de posibles desequilibrios en los datos y la selección de modelos de clasificación adecuados.

## Notebooks Incluidos

Este repositorio incluye los siguientes notebooks, que representan las etapas clave de mi análisis y modelado:

1.  **`EDA_y_Modelos_Iniciales BPRD.ipynb`**: https://colab.research.google.com/drive/1l-IcP4b3MG6fiDBAZsYjMTLDOc-R2_5Q?usp=sharing
    * **Análisis Exploratorio de Datos (EDA) Exhaustivo:** Este notebook se centra en la exploración profunda del conjunto de datos. Se analiza la distribución de las variables, se verifica si el origen de los conjuntos de entrenamiento y prueba es consistente, se examinan las correlaciones entre las características y la variable objetivo, y se generan variables dummy para codificar información categórica.
    * **Análisis del Comportamiento de los Días de Lluvia:** Se investiga el comportamiento específico de las variables en los días en que llovió, buscando patrones distintivos.
    * **Transformación de Variables:** Se aplican transformaciones a las variables para mejorar su distribución y linealidad, lo cual puede beneficiar a algunos modelos.
    * **Análisis Detallado de las Variables:** Se realiza un análisis en profundidad de cada variable, incluyendo sus promedios y distribuciones.
    * **Análisis con DABL (Data Analysis Baseline Library):** Se utiliza la librería DABL para obtener rápidamente modelos de referencia y realizar un análisis automatizado de las variables.
    * **Modelado Inicial con Machine Learning:** Se implementan modelos de clasificación como XGBoost y QDA (Quadratic Discriminant Analysis) para establecer una línea base de rendimiento.

2.  **`Ensemble_Learning_por_Clusters BPRD.ipynb`**: https://colab.research.google.com/drive/1vXxDvI4WxRPv8o5iFhvJkAMuZddbVNoY?usp=sharing
    * **Agrupamiento de Variables por Correlación (Clustering):** En este notebook, las variables se agrupan en clusters basados en su correlación. La hipótesis es que las variables dentro de un mismo cluster podrían tener patrones de relación similares con la variable objetivo.
    * **Generación de Modelos Específicos por Cluster:** Para cada cluster de variables correlacionadas, se entrena un modelo de clasificación independiente. El objetivo es que estos modelos especializados capturen mejor las relaciones específicas dentro de cada grupo de variables.
    * **Ensemble Learning con Predicciones de Clusters:** Las predicciones generadas por los modelos de cada cluster se incorporan como nuevas características al conjunto de datos original. Estas predicciones "especializadas" se combinan con las demás variables para entrenar un modelo general final.
    * **Resultados Satisfactorios en el Conjunto de Entrenamiento:** Los resultados obtenidos en el conjunto de entrenamiento utilizando esta técnica de ensemble learning por clusters mostraron una mejora en la capacidad predictiva del modelo general.

**Nota: sobre la visualización en GitHub: Este notebook puede mostrar el error 'Invalid Notebook' debido al uso de elementos interactivos (widgets) durante el análisis en Colab. GitHub no renderiza estos elementos de forma nativa. El código y los resultados estáticos son visibles, pero la interactividad se experimenta mejor al ejecutar el notebook en un entorno Jupyter o Colab.
