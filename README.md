# 📊 Challenge_TelecomX_LATAM2

## 📌 Descripción del Proyecto
Este proyecto aborda el análisis de **churn (evasión de clientes)** para una empresa ficticia de telecomunicaciones, **TelecomX LATAM**.  
El objetivo principal es **identificar los factores que llevan a la cancelación de clientes y construir modelos predictivos** que permitan anticipar estos casos.

---

## 📂 Estructura del Proyecto
- **Dataset limpio**: `telecomx_clean.csv`  
  Archivo con 7043 registros y ~21 columnas, sin identificadores irrelevantes ni inconsistencias.
  
- **Notebook principal**: Google Colab con todo el flujo de trabajo:
  1. Limpieza y preprocesamiento de datos.
  2. Análisis exploratorio y visualización.
  3. Preparación para modelado.
  4. Entrenamiento de modelos predictivos.
  5. Evaluación de resultados.
  6. Interpretación de variables.
  7. Conclusiones y recomendaciones.

---

## 🔎 Flujo de Trabajo

### 1. Limpieza y Preparación
- Conversión de `TotalCharges` a numérico, reemplazo de valores vacíos con `0.0`.
- Unificación de categorías (ej: `"No internet service"` → `"No"`).
- Eliminación de columnas irrelevantes como `customerID`.

### 2. Exploración de Datos
- **Matriz de correlación** con *heatmap*.  
- **Boxplots** para comparar:
  - `tenure` × Churn  
  - `TotalCharges` × Churn  
- **Scatter plot**: `MonthlyCharges` vs. `tenure` coloreado por Churn.

### 3. Preparación para Modelado
- Codificación de variables categóricas con **One-Hot Encoding**.  
- Balanceo de clases con **SMOTE**.  
- División en **train/test** (estratificado).

### 4. Modelado Predictivo
Se implementaron dos modelos:

- **Regresión Logística** (requiere normalización con `StandardScaler`).
- **Random Forest** (no requiere normalización).

Ambos fueron evaluados con:
- Accuracy
- Precisión
- Recall
- F1-score
- Matriz de confusión

### 5. Comparación de Resultados
- **Random Forest** → Mejor *accuracy* y *recall*. Riesgo de **overfitting** si no se ajustan parámetros.  
- **Regresión Logística** → Más interpretable, pero puede sufrir **underfitting** en patrones no lineales.  

### 6. Interpretación de Variables
- **Regresión Logística**: análisis de coeficientes (signo y magnitud).  
- **Random Forest**: ranking de importancia de variables basado en reducción de impureza.  
- **Propuesta**: combinar ambos → RF para predicción + RL para explicar resultados.

---

## ⚙️ Instrucciones de Uso
1. Abrir el [notebook en Google Colab](https://colab.research.google.com/drive/1JvI3OKIZ7tsnT3bbDEm1Lht9ozG0jQwD?usp=sharing).  
2. Subir el archivo `telecomx_clean.csv`.  
3. Ejecutar las celdas en orden para:
   - Preprocesar los datos.
   - Visualizar patrones.
   - Entrenar y evaluar modelos.
4. Ajustar hiperparámetros para optimizar resultados si es necesario.

---

## ✅ Conclusiones y Recomendaciones
- El **Random Forest** mostró mejor desempeño en la predicción del churn.  
- La **Regresión Logística** aporta interpretabilidad valiosa para entender los factores clave.  
- Se recomienda usar un **modelo híbrido**: RF para producción y RL para reportes ejecutivos.  
- Incluir más datos históricos y pruebas con modelos avanzados (XGBoost, SVM, redes neuronales) podría mejorar la predicción.

---

✍️ **Autor:** Proyecto académico — Challenge LATAM 2025  
