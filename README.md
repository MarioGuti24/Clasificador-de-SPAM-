# Clasificador de Spam — Proyecto Final de Aprendizaje Automático

## Descripción del proyecto

Este proyecto desarrolla un sistema de clasificación de correos electrónicos spam utilizando diferentes algoritmos de Machine Learning sobre el dataset Spambase de la UCI Machine Learning Repository.

El objetivo principal es comparar múltiples modelos de clasificación y distintos enfoques de preprocesado y selección de variables para determinar cuál ofrece el mejor rendimiento en la detección de spam.

El trabajo incluye:

- Análisis exploratorio de datos (EDA)
- Estudio de correlaciones
- Detección de outliers
- Transformaciones logarítmicas
- Selección de variables mediante correlación de Pearson
- Reducción de dimensionalidad mediante PCA
- Entrenamiento y evaluación de modelos de clasificación
- Validación cruzada
- Comparativa de resultados

---

# Dataset

Se ha utilizado el dataset:

Spambase — UCI Machine Learning Repository

- Dataset original: https://archive.ics.uci.edu/dataset/94/spambase
- Tipo de problema: Clasificación binaria
- Objetivo:
  - 1 → Spam
  - 0 → No Spam

El dataset contiene variables relacionadas con:

- Frecuencia de palabras
- Frecuencia de caracteres especiales
- Variables estadísticas sobre el contenido del email

---

# Tecnologías y librerías utilizadas

## Lenguaje

- Python 3

## Librerías principales

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
ucimlrepo
```

# Pipeline del proyecto

## 1. Carga del dataset

El dataset se descarga directamente desde `ucimlrepo` y posteriormente se transforma en un DataFrame para facilitar el análisis.

---

## 2. Limpieza y análisis inicial

Se realiza:

- Comprobación de valores nulos
- Revisión de tipos de datos
- Estadísticos descriptivos
- Distribuciones de variables

---

## 3. Análisis de correlación

Se estudia la relación entre las variables y la variable objetivo (`Class`) utilizando correlación de Pearson.

Posteriormente:

- Se aplican umbrales de correlación
- Se seleccionan las variables más relevantes
- Se generan heatmaps para visualizar dependencias

---

## 4. Detección de outliers

Se utiliza el método del IQR para detectar valores atípicos.

Dado que los datos representan frecuencias de aparición de palabras, los outliers no se eliminan, ya que contienen información útil.

Para reducir su impacto:

- Se aplican transformaciones logarítmicas

---

## 5. División Train/Test

El dataset se divide en:

- Datos de entrenamiento
- Datos de prueba

También se aplican técnicas de escalado cuando son necesarias.

---

# Modelos utilizados

## Regresión Logística

Modelo lineal utilizado como baseline principal.

---

## Árbol de Clasificación

Modelo basado en reglas de decisión.

---

## K-Nearest Neighbors (KNN)

Clasificación basada en vecinos más cercanos.

---

## Support Vector Machine (SVM)

Modelo de clasificación mediante hiperplanos óptimos.

---

## Red Neuronal (MLP)

Perceptrón multicapa para clasificación no lineal.

---

## Naive Bayes

Clasificador probabilístico basado en el teorema de Bayes.

---

# Feature Engineering con PCA

Además del pipeline basado en correlación de Pearson, se implementa un segundo enfoque utilizando:

## PCA (Principal Component Analysis)

Objetivos:

- Reducir dimensionalidad
- Eliminar multicolinealidad
- Mantener el 95% de la varianza del dataset

Posteriormente, se vuelven a entrenar todos los modelos para comparar resultados entre:

- Selección por correlación
- Reducción mediante PCA

---

# Evaluación de modelos

Las métricas utilizadas incluyen:

- Accuracy
- Precision
- Recall
- F1-Score
- Matriz de confusión
- Validación cruzada

Debido a la naturaleza del problema, se da especial importancia a:

## Precision

Minimizar falsos positivos es clave para evitar que correos legítimos sean marcados como spam.

---

# Resultados y conclusiones

## Principales conclusiones

- Todos los modelos obtuvieron resultados sólidos y consistentes.
- Los mejores resultados se obtuvieron principalmente con:
  - Regresión logística
  - Redes neuronales (MLP)
- El enfoque basado en correlación lineal presentó un rendimiento ligeramente superior al pipeline PCA.
- PCA logró mantener resultados muy competitivos reduciendo dimensionalidad y eliminando redundancias.

## Conclusión final

Ambos pipelines son válidos para resolver el problema de detección de spam. Sin embargo, la selección de variables mediante correlación lineal mostró una ligera ventaja en precisión y capacidad predictiva, aspecto especialmente importante en sistemas anti-spam.

---

# Cómo ejecutar el proyecto

## 1. Clonar el repositorio

```bash
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_REPOSITORIO>
```

## 2. Instalar dependencias

```bash
pip install pandas numpy matplotlib seaborn scikit-learn ucimlrepo jupyter
```

## 3. Ejecutar el notebook

```bash
jupyter notebook
```

Abrir:

```bash
ProyectoFinal_definitivo.ipynb
```

---

# Estructura del proyecto

```bash
├── ProyectoFinal_definitivo.ipynb
├── dataset.csv
├── README.md
```

---

# Autor

Proyecto realizado como trabajo final de Aprendizaje Automático.

---

# Referencias

- UCI Machine Learning Repository
- Scikit-learn Documentation
- Pandas Documentation
- Seaborn Documentation
