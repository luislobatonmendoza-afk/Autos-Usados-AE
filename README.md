# 🚗 Clasificación de Precios de Autos Usados con Machine Learning

Este proyecto implementa un sistema completo de Aprendizaje Supervisado cuyo objetivo es clasificar vehículos usados en tres categorías de precio: Económicos, Medios y Premium. El modelo fue desarrollado en Google Colab utilizando un dataset de Kaggle y técnicas de preprocesamiento, normalización y clasificación con Random Forest, cumpliendo con los lineamientos del curso de Aprendizaje Estadístico.

---

## 🧠 Tecnologías Utilizadas

- Python 3
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- KaggleHub

---

## 📂 Estructura del Repositorio

El repositorio está organizado de la siguiente manera:

documentacion/  
└── informe_proyecto.pdf (opcional)

codigo/  
├── autos_usados.ipynb  
├── autos_usados.py  
└── requirements.txt

pruebas/  
├── matriz_confusion.png  
├── importancia_variables.png  
└── pruebas_prediccion.md

README.md

---

## ⚙️ Cómo Ejecutar el Proyecto

### 1. Clonar el repositorio

git clone https://github.com/<TU-USUARIO>/clasificacion-autos-usados-ml.git

### 2. Instalar dependencias

pip install -r requirements.txt

### 3. Abrir el Notebook

Puede ejecutarse desde Google Colab o Jupyter Notebook. El archivo principal es autos_usados.ipynb.

### 4. Ejecutar todas las celdas

El notebook realiza automáticamente la descarga del dataset, preprocesamiento, normalización, entrenamiento del modelo Random Forest, evaluación del sistema, generación de métricas y pruebas reales mediante una función interactiva de predicción.

---

## 🔍 Descripción del Modelo

### ✔ Preprocesamiento aplicado

- Eliminación de valores nulos
- Eliminación de duplicados
- Limpieza de atributos numéricos
- Conversión de datos categóricos mediante LabelEncoder
- Normalización parcial de variables numéricas

### ✔ Etiquetado del precio

El precio fue transformado en tres categorías usando percentiles:
- Económico (0-33%)
- Medio (34-66%)
- Premium (67-100%)

### ✔ División del dataset

- 80% entrenamiento
- 20% prueba

### ✔ Modelo final implementado

Modelo: Random Forest Classifier  
Parámetros clave:  
- n_estimators = 200  
- random_state = 42  

### ✔ Resultados del modelo

- Accuracy: 73%
- F1-score balanceado
- Estabilidad entre ejecuciones

---

## 📊 Resultados del Sistema

El repositorio incluye:

### ✔ Matriz de Confusión
Ubicada en pruebas/matriz_confusion.png

### ✔ Importancia de Variables
Ubicada en pruebas/importancia_variables.png

Variables más influyentes:
- Año del vehículo
- Kilometraje
- Marca
- Transmisión
- Tipo de combustible

### ✔ Reporte de Clasificación
Incluye precisión, recall y F1-score por clase.

### ✔ Pruebas manuales
Incluidas en pruebas/pruebas_prediccion.md  
La función predecir_auto() permite ingresar datos reales de vehículos.

---

# 🚀 Deploy del Sistema (Descripción Técnica)

Aunque no se construyó una aplicación web, se deja planteada la arquitectura de despliegue recomendada:

## ▶ 1. Exportación del Modelo

import joblib  
joblib.dump(rf, "modelo_autos.joblib")

## ▶ 2. API REST con FastAPI (estructura recomendada)

from fastapi import FastAPI  
import joblib  
import pandas as pd  

app = FastAPI()  
modelo = joblib.load("modelo_autos.joblib")  

@app.post("/predecir")  
def predecir(data: dict):  
 entrada = pd.DataFrame([data])  
 pred = modelo.predict(entrada)[0]  
 return {"categoria_predicha": pred}

