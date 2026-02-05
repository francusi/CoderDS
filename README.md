# 🚌 Predicción de Demanda de Transporte Público - Rosario (2026)

![Estado del Proyecto](https://img.shields.io/badge/Estado-Finalizado-success)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Lib](https://img.shields.io/badge/Library-Scikit--Learn-orange)

## 📋 Descripción del Proyecto
Este proyecto de Data Science tiene como objetivo predecir la cantidad de viajes diarios en el sistema de transporte público de la ciudad de Rosario para el año **2026**. 

Se utilizaron datos históricos de la tarjeta **SUBE** (2023, 2024 y 2025) para entrenar un modelo de Machine Learning capaz de capturar la estacionalidad compleja de la ciudad, incluyendo ciclos lectivos, días laborales y feriados nacionales.

## 🎯 Objetivo
Proporcionar una estimación certera de la demanda futura para ayudar en la planificación operativa y estratégica de las empresas de transporte (**Rosario Bus** y **Movi**).

## 🛠️ Tecnologías y Herramientas
* **Lenguaje:** Python
* **Análisis de Datos:** Pandas, NumPy
* **Visualización:** Seaborn, Matplotlib
* **Machine Learning:** Scikit-Learn (Random Forest Regressor)
* **Ingeniería de Features:** Librería `holidays` (para feriados de Argentina)

## ⚙️ Metodología

### 1. Limpieza y Transformación (ETL)
* Unificación de datasets anuales (2023-2025).
* Conversión de tipos de datos temporales.
* Tratamiento de valores atípicos.

### 2. Ingeniería de Características (Feature Engineering)
Para mejorar la precisión del modelo, se crearon variables de contexto específicas para Rosario:
* **`ES_FERIADO`**: Detección automática de feriados argentinos usando la librería `holidays`.
* **`TIPO_DIA_REAL`**: Segmentación inteligente que agrupa "Sábados", "Domingos" y "Feriados" como días de descanso, diferenciándolos de los días hábiles.
* **Variables Temporales**: Desglose de día de la semana, mes y día del año para capturar estacionalidad (ej: receso escolar de invierno).

### 3. Modelado y Validación Temporal
A diferencia de los enfoques tradicionales, **no se utilizó una división aleatoria (random split)** para evitar el "data leakage" (viaje en el tiempo).
* **Entrenamiento:** Datos de 2023 y 2024.
* **Validación (Test):** Datos de 2025.
* **Modelo:** `RandomForestRegressor`.

## 📊 Resultados

El modelo alcanzó un **Error Porcentual (MAPE) de ~17%** en el conjunto de validación (2025), un valor robusto considerando la variabilidad externa (paros de transporte, clima) no incluida en el dataset.

### Comparativa: Realidad 2025 vs Predicción 2026
*(Aquí puedes pegar la imagen de tu gráfico final comparativo)*
![Gráfico Comparativo][https://github.com/francusi/Proyecto_SUBE/issues/1#issue-3903034507]

> **Observación:** El modelo captura correctamente la caída de demanda en los meses de **Enero/Febrero** (vacaciones de verano) y la "muesca" en **Julio** (receso invernal), demostrando que ha aprendido el comportamiento social de la ciudad.

## 🚀 Cómo ejecutar este proyecto

1.  Clonar el repositorio:
    ```bash
    git clone [https://github.com/francusi/Proyecto_SUBE.git](https://github.com/francusi/Proyecto_SUBE.git)
    ```
2.  Instalar dependencias:
    ```bash
    pip install pandas scikit-learn seaborn holidays
    ```
3.  Ejecutar el Notebook `ProyectoSUBERosario.ipynb`.

## ✒️ Autor
**Franco** - *Data Scientist Junior / BI Analyst*
* [LinkedIn](https://www.linkedin.com/in/franco-barrionuevo/)
* [GitHub](https://github.com/francusi)

---
