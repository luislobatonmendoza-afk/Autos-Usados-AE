#Clasificación de Precios de Autos Usados con Machine Learning

Este proyecto implementa un sistema de aprendizaje supervisado para clasificar los precios de autos usados en tres categorías:

Económicos

Medios

Premium

El modelo fue desarrollado en Google Colab, utilizando el dataset público de Kaggle y técnicas de preprocesamiento, normalización y clasificación con Random Forest.

#🧠 Tecnologías Utilizadas

Python 3

Google Colab

Pandas

Numpy

Scikit-learn

Matplotlib / Seaborn

KaggleHub (para descargar dataset automáticamente)

#📝 Estructura del Proyecto
documentacion/
codigo/
pruebas/
README.md

#⚙ Cómo Ejecutar el Proyecto

Clonar el repositorio:

git clone https://github.com/<tu-usuario>/clasificacion-autos-usados-ml.git


Instalar dependencias:

pip install -r requirements.txt


Abrir el notebook en Google Colab o Jupyter:

autos_usados.ipynb


Ejecutar todas las celdas.

#🚗 Modelo Entrenado

El modelo final utilizado fue:

Random Forest Classifier

200 árboles

Accuracy final: ~73%

Validación cruzada K-Fold: estable

#📊 Resultados del Sistema

Matriz de confusión

Reporte de clasificación

Importancia de variables

Pruebas de predicción con predecir_auto()
