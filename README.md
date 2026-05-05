# 🍷 Análisis y Preparación de Dataset de Vinos (Machine Learning)

## Descripción del proyecto

Este proyecto tiene como objetivo trabajar con un dataset de vinos para desarrollar habilidades en **análisis de datos, limpieza (data cleaning)** y preparación para modelos de **machine learning** en Python.

El enfoque principal no es solo entrenar modelos, sino **entender los datos, detectar problemas reales y tomar decisiones justificadas**, como se haría en un entorno profesional.

---

## Objetivos

* Analizar la calidad de los datos
* Detectar valores erróneos y outliers
* Gestionar valores faltantes (missing values)
* Preparar el dataset para futuros modelos de machine learning
* Documentar decisiones de limpieza de datos

---

## Análisis realizado

### Exploración inicial

* Uso de `describe()` para entender distribución de variables
* Identificación de variables irrelevantes (como ID)
* Detección de valores extremos y sospechosos

---

### Problemas detectados

#### 1. Valores artificiales

* Presencia de valores como `9999` en variables como **Azúcar**
* Identificados como posibles *missing values codificados*

#### 2. Valores negativos no válidos

* Variables como:

  * `Azucar`
  * `Alcohol`
* Presentan valores negativos, lo cual no tiene sentido físico

#### 3. Outliers extremos

* Valores máximos irreales que distorsionan:

  * media
  * desviación estándar

#### 4. Valores faltantes distribuidos

* Filas con múltiples variables incompletas

---

## Estrategia de limpieza

### 1. Eliminación de filas muy corruptas

* Se eliminan filas con **más de 2 valores faltantes**
* Justificación:

  * Bajo porcentaje del dataset
  * Difícil imputación fiable

---

### 2. Tratamiento de valores artificiales

* Valores como `9999` → convertidos a `NaN`
* Identificados como *missing disfrazados*

---

### 3. Creación de variables auxiliares

* Ejemplo:

  * `Azucar_missing_flag`
* Permite al modelo aprender si un dato faltaba originalmente

---

### 4. Imputación de datos

* Variables numéricas:

  * imputación mediante **mediana** (robusta frente a outliers)
* Variables categóricas:

  * imputación con **moda** o categoría `"Unknown"`

---

### 5. Tratamiento de valores negativos

* Evaluación de:

  * cantidad
  * distribución
* Decisión:

  * convertir a `NaN` o eliminar según el caso

---

## Estado actual del dataset

* Datos inconsistentes tratados
* Valores faltantes gestionados
* Dataset preparado para:

  * encoding
  * entrenamiento de modelos

---

## Próximos pasos

* Codificación de variables categóricas
* Separación en train/test
* Entrenamiento de modelos de clasificación
* Evaluación de rendimiento
* Optimización y selección de modelo

---

## Tecnologías utilizadas

* Python
* Pandas
* NumPy
* Matplotlib / Seaborn
* Scikit-learn

---

## Aprendizajes clave

* La limpieza de datos es más importante que el modelo
* No todos los outliers deben eliminarse
* Los valores faltantes requieren análisis, no solo imputación automática
* Las decisiones deben estar siempre justificadas

---

## Estructura del proyecto

```
proyecto-vinos
 ┣  Vinos_code.ipynb
 ┣  DatosVino.csv
 ┗  README.md
```

