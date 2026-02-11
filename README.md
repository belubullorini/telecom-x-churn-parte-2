<p align="center">
  <img src="assets/Banner-telecomX.gif" alt="Banner del proyecto" width="600">
</p>

![Estado](https://img.shields.io/badge/estado-en%20desarrollo-yellow)
![Lenguaje](https://img.shields.io/badge/lenguaje-Python-blue)
![Licencia](https://img.shields.io/badge/licencia-MIT-green)
![Última actualización](https://img.shields.io/badge/actualizado-2026--02--11-purple)

# 📊 Telecom X – Predicción de Churn (Parte 2)

Proyecto desarrollado dentro del **desafío Telecom X** del programa **ONE Oracle Next Education**.  
Este proyecto se enfoca en la **construcción de modelos predictivos** para anticipar la cancelación de clientes (churn), utilizando técnicas de **machine learning**, preparación de datos, análisis de correlación y evaluación de modelos.

---

## 🧾 Índice

- [📌 Estado del proyecto](#-estado-del-proyecto)
- [🎯 Propósito del análisis](#-propósito-del-análisis)
- [🗂 Estructura del proyecto](#-estructura-del-proyecto)
- [🛠️ Preparación de los datos](#-preparación-de-los-datos)
- [📊 Análisis exploratorio y correlación](#-análisis-exploratorio-y-correlación)
- [🤖 Modelado predictivo](#-modelado-predictivo)
- [📈 Evaluación de modelos](#-evaluación-de-modelos)
- [🧠 Interpretación de variables](#-interpretación-de-variables)
- [🚀 Instrucciones para ejecutar](#-instrucciones-para-ejecutar)
- [📝 Conclusiones finales](#-conclusiones-finales)
- [👩‍💻 Autoría](#-autoría)

---

## 📌 Estado del proyecto
🛠️ En desarrollo  
Incluye preparación de datos, análisis exploratorio, entrenamiento de modelos y evaluación de métricas.

---

## 🎯 Propósito del análisis

El objetivo principal es **predecir la cancelación de clientes (churn)** a partir de variables relevantes del negocio.

Se busca:

- Construir modelos predictivos de clasificación  
- Comparar modelos con y sin normalización  
- Evaluar el rendimiento con métricas adecuadas  
- Identificar las variables más importantes en la predicción  
- Apoyar la toma de decisiones estratégicas para reducir la pérdida de clientes  

📌 Este proyecto simula el rol de una científica de datos en un entorno real de negocio, aplicando **preprocesamiento**, **modelado** y **evaluación de modelos de machine learning**.

---

## 🗂 Estructura del proyecto

```text
telecom-x-churn-parte-2/
│
├── data/
│   └── datos_tratados.csv          # Datos limpios provenientes de la Parte 1
│
├── images/                         # Gráficos del EDA y correlaciones
│   ├── correlacion_numericas.png
│   ├── boxplot_antiguedad_churn.png
│   ├── boxplot_gasto_churn.png
│   └── matriz_confusion.png
│
├── notebooks/
│   └── TelecomX_Parte2.ipynb        # Notebook principal con EDA y modelos
│
├── LICENSE                         # Licencia MIT del proyecto
└── README.md                       # Documentación del proyecto
```

---

## 🛠️ Preparación de los datos

El flujo de preparación de los datos incluye las siguientes etapas:

- Carga del archivo CSV con los datos tratados de la Parte 1  
- Eliminación de columnas irrelevantes (por ejemplo, identificadores únicos)  
- Clasificación de variables en categóricas y numéricas  
- Codificación de variables categóricas mediante one-hot encoding  
- Verificación de la proporción de churn para analizar el desbalance de clases  
- Separación de los datos en conjuntos de entrenamiento y prueba  
- Aplicación de balanceo de clases únicamente sobre el conjunto de entrenamiento para evitar data leakage  
- Normalización / estandarización de variables numéricas para modelos sensibles a la escala  

Estas decisiones permiten asegurar que los modelos se entrenen sin introducir sesgos y que las métricas obtenidas reflejen un desempeño realista.

---

## 📊 Análisis exploratorio y correlación

Se realiza un análisis exploratorio de los datos (EDA) para comprender la distribución de las variables y su relación con la cancelación de clientes (churn).

Entre las principales acciones se incluyen:

- Análisis de la proporción de clientes que cancelan vs los que permanecen  
- Visualización de variables clave como antigüedad, pago mensual y pago total en función del churn  
- Construcción de una matriz de correlación para variables numéricas  
- Análisis dirigido mediante boxplots y scatterplots para detectar patrones relevantes  

Estos análisis permiten identificar qué variables podrían tener mayor impacto en la cancelación y sirven como base para la etapa de modelado.

---

## 🤖 Modelado predictivo

Se construyen dos modelos con enfoques distintos para comparar desempeño:

- **Regresión Logística**: modelo sensible a la escala de las variables, por lo que requiere normalización previa. Permite además interpretar los coeficientes como impacto de cada variable en la probabilidad de churn.  
- **Random Forest**: modelo basado en árboles, no sensible a la escala de las variables, capaz de capturar relaciones no lineales y medir importancia de variables.

El conjunto de datos se divide en:

- **Entrenamiento (70%)**  
- **Prueba (30%)**

El balanceo de clases se aplica solo sobre el conjunto de entrenamiento para evitar fuga de información (data leakage).

Los modelos se evalúan utilizando:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- Matriz de confusión  

---

## 📈 Interpretación de resultados

Para interpretar los modelos se analizan:

- **Regresión Logística**: coeficientes de las variables, donde el signo indica si aumentan o disminuyen la probabilidad de churn y el valor absoluto indica la magnitud del impacto.  
- **Random Forest**: importancia de variables basada en la reducción de impureza en los árboles.

La comparación entre ambos enfoques permite identificar factores consistentes que influyen en la cancelación de clientes.

---

## 📝 Conclusiones y recomendaciones

A partir del análisis y el modelado se concluye que:

- Existen variables contractuales y de facturación con fuerte impacto en la cancelación.  
- El uso de modelos con distintos supuestos (lineal vs no lineal) permite obtener una visión más robusta del problema.  
- La combinación de métricas y análisis de importancia de variables ayuda a transformar resultados técnicos en decisiones de negocio.

### Recomendaciones estratégicas:

- Incentivar contratos de mayor duración.  
- Diseñar acciones específicas para clientes con mayor riesgo de churn.  
- Revisar la oferta de servicios asociados a mayor probabilidad de cancelación.  
- Implementar monitoreo continuo de métricas de retención para ajustar estrategias.


