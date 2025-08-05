# 📊 Predicción de Churn en Clientes de Telecomunicaciones - Telecom X

Este proyecto utiliza técnicas de ciencia de datos para analizar y predecir la cancelación de clientes (churn) en una empresa de telecomunicaciones ficticia llamada **Telecom X**. El objetivo es identificar los factores que influyen en la pérdida de clientes y construir modelos predictivos que permitan a la empresa tomar acciones proactivas para retenerlos.

## 📚 Tabla de Contenidos

- [📝 Descripción del Problema](#descripción-del-problema)
- [🔎 Metodología](#metodología)
- [📈 Análisis Exploratorio](#análisis-exploratorio)
- [🧹 Preprocesamiento](#preprocesamiento)
- [🤖 Modelado](#modelado)
- [🏆 Resultados](#resultados)
- [⚙️ Requisitos](#requisitos)
- [📄 Informe Completo](#informe-completo)

## 📝 Descripción del Problema

Telecom X enfrenta una alta tasa de cancelación de clientes, lo que afecta su rentabilidad y crecimiento. El objetivo principal es predecir qué clientes tienen mayor probabilidad de abandonar la empresa, permitiendo así intervenciones de retención más efectivas.

## 🔎 Metodología

Se sigue la metodología **CRISP-DM**:
1. Carga y limpieza de datos desde una API pública.
2. Análisis exploratorio y segmentación de clientes.
3. Preprocesamiento y transformación de variables.
4. Modelado predictivo (Random Forest y Redes Neuronales).
5. Evaluación y explicación de resultados.

## 📈 Análisis Exploratorio

- El dataset contiene 7,032 clientes y 21 variables, incluyendo datos demográficos, servicios contratados, historial de pagos y estado de churn.
- Se identifican variables clave como tipo de contrato, antigüedad, cargos mensuales/totales, servicios adicionales y método de pago.
- Se observa que los contratos mes a mes, menor antigüedad y ciertos métodos de pago están asociados a mayor churn.

## 🧹 Preprocesamiento

- Limpieza de datos nulos y transformación de variables categóricas y numéricas.
- Eliminación de variables con alta multicolinealidad.
- Balanceo de clases y preparación de datos para modelado.

## 🤖 Modelado

- **Random Forest**: Optimización de hiperparámetros y ajuste de pesos para clases desbalanceadas.
- **Red Neuronal**: Arquitectura simple con ajuste de pesos de clase.
- Evaluación con métricas como AUC-ROC, F1-score, precisión y recall.

## 🏆 Resultados

- El modelo Random Forest alcanzó un **AUC-ROC de 0.84** y un recall del 79% para la clase churn.
- Las variables más importantes son: tipo de contrato, antigüedad, cargos totales, tipo de internet y método de pago.
- Se identificaron segmentos de clientes con mayor riesgo de churn, permitiendo estrategias de retención personalizadas.

## ⚙️ Requisitos

- Python 3.x
- pandas, numpy, scikit-learn, matplotlib, seaborn, xgboost, lightgbm, tensorflow

## 📄 Informe Completo

Puedes consultar el informe detallado del análisis y resultados en el siguiente enlace:

[📑 Informe PDF del Proyecto](./informeTELCOMX2Alura.md)
