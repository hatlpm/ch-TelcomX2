# 📑 Informe Ejecutivo del Proyecto "Predicción de Churn – Telecom X"

## 1. Contexto y Objetivo

Telecom X enfrenta una alta tasa de cancelación de clientes (churn), lo que afecta su rentabilidad y crecimiento. El objetivo principal es identificar los factores que impulsan el churn y construir modelos predictivos robustos para anticipar qué clientes tienen mayor probabilidad de abandonar la empresa, permitiendo así intervenciones de retención más efectivas.

---

## 2. Resumen de Hallazgos Principales

- **Tamaño y estructura del dataset:** 7,267 registros y 21 variables, con información demográfica, servicios contratados, historial de pagos y estado de churn.
- **Desbalance de clases:** 71% de clientes no hacen churn, 25.7% sí, y 3% de registros vacíos en la variable objetivo (fueron eliminados para el análisis).
- **Variables críticas para el churn:**
  - **Tipo de contrato:** El 55% de los clientes tiene contrato "Month-to-month", segmento con mayor fuga.
  - **Antigüedad (tenure):** Clientes con menos de 12 meses tienen hasta 3 veces más probabilidad de churn.
  - **Servicios adicionales:** No contar con OnlineSecurity, TechSupport o DeviceProtection incrementa el riesgo.
  - **Método de pago:** "Electronic check" tiene la tasa de churn más alta (~34% de los clientes).
  - **Tipo de internet:** "Fiber optic" presenta mayor churn que "DSL".
  - **Cargos mensuales altos y cargos totales bajos:** Perfil típico de cliente nuevo y de alto riesgo.
- **Variables poco relevantes:** Género y tener múltiples líneas telefónicas no muestran impacto significativo en el churn.

---

## 3. Modelos Desarrollados y Comparación

| Modelo                | AUC   | Recall | Precision | F1   | Observaciones |
|-----------------------|-------|--------|-----------|------|--------------|
| **Random Forest**     | 0.84  | 0.76   | 0.56      | 0.64 | Buen balance entre interpretabilidad y desempeño. |
| **XGBoost**           | 0.85  | 0.82   | 0.54      | 0.64 | Mejor desempeño general, especialmente en recall y AUC. |
| **Red Neuronal (MLP)**| 0.84  | 0.83   | 0.49      | 0.60 | Útil, pero menor desempeño que los modelos de árboles. |

- **XGBoost** es el modelo con mejor desempeño global, aunque Random Forest es más interpretable para el negocio.
- Todos los modelos fueron validados con cross-validation y ajuste de pesos para el desbalance de clases.

---

## 4. Recomendaciones de Negocio

1. **Migrar contratos "Month-to-month" a planes anuales** mediante incentivos y descuentos.
2. **Promover servicios adicionales** (seguridad, soporte, protección de dispositivos) con bundles y ofertas para clientes nuevos.
3. **Campañas dirigidas a clientes con "Electronic check"** para migrar a métodos automáticos (tarjeta/crédito) con beneficios iniciales.
4. **Programa de fidelización por antigüedad:** recompensas a los 6 y 12 meses para reducir churn temprano.
5. **Alertas proactivas:** disparar intervenciones cuando un cliente cumpla condiciones críticas (tenure bajo, contrato M2M, Electronic check).

---

## 5. Segmentos de Clientes en Riesgo

El análisis de los datos y la interpretación de los modelos permiten identificar perfiles específicos de clientes con mayor probabilidad de churn. Estos segmentos son prioritarios para campañas de retención y acciones personalizadas:

### a) Clientes con contrato "Month-to-month", menos de 12 meses de antigüedad y método de pago "Electronic check"
Este grupo concentra la mayor tasa de cancelación. Son clientes nuevos, con baja fidelidad y expuestos a la fricción de pagos manuales.  
**Acción recomendada:** Ofrecer incentivos para migrar a contratos anuales y métodos de pago automáticos.

### b) Usuarios de internet "Fiber optic" sin servicios adicionales (OnlineSecurity, TechSupport, DeviceProtection)
Presentan una tasa de churn superior al promedio, posiblemente por percibir poco valor agregado o enfrentar problemas técnicos.  
**Acción recomendada:** Promocionar bundles de servicios de seguridad y soporte, y realizar seguimiento proactivo de satisfacción.

### c) Clientes con cargos mensuales altos y cargos totales bajos
Perfil típico de clientes nuevos que contratan paquetes premium, pero que no logran integrarse o percibir valor en los primeros meses.  
**Acción recomendada:** Implementar onboarding personalizado y seguimiento durante los primeros 3-6 meses.

### d) Clientes sin dependientes ni pareja, especialmente "Senior Citizens"
Este segmento muestra mayor propensión al churn, posiblemente por menor uso de servicios o menor percepción de necesidad.  
**Acción recomendada:** Ofrecer beneficios exclusivos y comunicación personalizada para aumentar el engagement.

### e) Clientes sin servicio de internet
Aunque su tasa de churn es baja, representan una oportunidad para upselling de servicios digitales.

> **Conclusión de la sección:**  
> La segmentación permite priorizar recursos y diseñar campañas de retención mucho más efectivas, enfocadas en los perfiles con mayor riesgo y potencial de impacto.

---

## 6. Conclusión

El churn en Telecom X es predecible con alta precisión (AUC hasta 0.85 con XGBoost). Las variables controlables (tipo de contrato, servicios extra y método de pago) ofrecen palancas directas para reducir la fuga. Implementar las recomendaciones puede recortar el churn anual en 8-12 puntos porcentuales, generando un impacto financiero significativo.

**Próximo hito:** Desplegar el modelo XGBoost en producción y lanzar campañas de retención segmentadas en el próximo trimestre.

---

