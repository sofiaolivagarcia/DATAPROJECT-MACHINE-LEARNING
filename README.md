# DATAPROJECT-MACHINE-LEARNING
# Regresión y Clasificación de Estudiantes

### Objetivo del proyecto
El objetivo de este proyecto es analizar un conjunto de datos de estudiantes (`dataset_estudiantes.csv`) para **predecir el rendimiento académico** mediante técnicas de Machine Learning.

Se plantean dos objetivos principales:
1. **Regresión:** predecir la `nota_final` (valor entre 0 y 100).  
2. **Clasificación:** predecir si el alumno **aprueba o no** (`aprobado` = 1 si la nota ≥ 60).

## Contenido del proyecto

| Notebook | Descripción |
|-----------|-------------|
| `01_EDA.ipynb` | Análisis exploratorio del dataset: distribuciones, correlaciones, outliers y primeras observaciones. |
| `02_Preprocesamiento.ipynb` | Limpieza de datos, imputación de valores nulos, codificación de variables categóricas y escalado. |
| `03_Modelado.ipynb` | Modelado de regresión y clasificación. Entrenamiento, evaluación y comparación de modelos. |
| `04_Conclusiones.ipynb` | Conclusión general del proyecto y propuestas de mejora. |

## Preprocesamiento de datos

- Imputación de valores nulos:
  - **Mediana** para variables numéricas.
  - **Moda** para variables categóricas.
- División de los datos en **entrenamiento (80%) y test (20%)**.
- Guardado de los conjuntos procesados en la carpeta `Data/processed/`.

## 📈 Modelado

### Regresión (variable: `nota_final`)
- **Regresión Lineal**
  - MAE ≈ 5.8  
  - RMSE ≈ 7.2  
  - R² ≈ 0.36  
  → Mejor modelo para predecir la nota final.

- **Árbol de Decisión (Regresión)**
  - Tras regularizar (`max_depth=4`), obtiene R2 ≈ 0.24.  
  - Permite interpretar las variables más influyentes, aunque no mejora la precisión.

### Clasificación (variable: `aprobado`)
- **Regresión Logística**
  - Accuracy ≈ 0.91  
  - Precision ≈ 0.91  
  - Recall ≈ 0.99  
  - F1 ≈ 0.95  
  - ROC-AUC ≈ 0.81  
  → Modelo final elegido para clasificación.

- **Árbol de Clasificación**
  - Con `max_depth=4`, consigue métricas parecidas a la logística (ROC-AUC ≈ 0.95).  
  - Útil para conocer las variables con mayor peso en el aprobado.

## Conclusiones generales

- La **Regresión Lineal** es el mejor modelo para predecir la nota final (regresión).  
- La **Regresión Logística** es el modelo más estable y preciso para predecir el aprobado (clasificación).  
- Las variables con mayor influencia en el rendimiento son:
  - `nota_anterior`
  - `tasa_asistencia`
  - `horas_estudio_semanal`

En resumen, los modelos lineales se adaptan mejor al comportamiento de este dataset.

## Tecnologías utilizadas
- **Python 3.12**  
- **pandas**, **numpy**, **matplotlib**, **seaborn**, **scikit-learn**

## 👩‍💻 Autor/a
Sofía Oliva garcía  
Proyecto de Regresión y Clasificación – ThePower  

