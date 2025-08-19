**Análisis de Evasión de Clientes**

**1. Introducción**

**Objetivo:** El objetivo de este análisis es identificar patrones de cancelación de clientes para mejorar la retención.


**2. Limpieza y Tratamiento de Datos**
Se realizaron los siguientes pasos para preparar el dataset:

Carga y normalización del JSON con json_normalize para convertir columnas anidadas en planas.

Valores nulos:

Eliminación de registros donde Churn estaba vacío (224 registros eliminados).

Conversión de account.Charges.Monthly y account.Charges.Total a tipo numérico, eliminando 11 registros con problemas.

Duplicados: verificación de customerID (0 duplicados).

Consistencia de categorías:

Reemplazo de No phone service y No internet service por No.

Unificación de valores binarios: Yes → 1, No → 0.

Renombrado y estandarización de columnas:

Ejemplo: Meses_Contrato, Cargos_Mensuales, Cargos_Totales, Gasto_Diario.

Creación de nuevas columnas:

Gasto_Diario como promedio diario de facturación mensual.


**3. Análisis Exploratorio de Datos**

**3.1 Estadísticas descriptivas de variables numéricas**

**Datos:** 7.032 clientes, sin duplicados ni valores nulos relevantes. Variables incluyen demográficas, tipo de contrato, métodos de pago, servicios y consumo.

Meses_Contrato: promedio 32.4, mediana 29, máximo 72.

Cargos_Mensuales: promedio 64.8, mediana 70.35.

Cargos_Totales: gran dispersión (std=2266), clientes con consumos muy distintos.

Gasto_Diario: promedio 2.16, mediana 2.34

**3.2 Distribución de evasión general**
Aproximadamente 26.6% de los clientes han cancelado su servicio.

**3.3 Distribución de Churn según variables categóricas**

Clientes con contratos Month-to-month presentan mayor tendencia a cancelar.

Métodos de pago como Electronic check se asocian a mayor Churn.

Servicios adicionales reducen la probabilidad de evasión.

**3.4 Distribución de Churn según variables numéricas**
Clientes con menor tiempo de contrato y menor gasto diario tienden a cancelar más.

Clientes con contratos largos y mayor facturación tienen menor probabilidad de Churn.

**Conclusiones:**

La evasión total es del 26.6%, un área relevante de mejora.

Factores de riesgo de Churn: contratos cortos, menor gasto diario, pocos servicios contratados.

Variables como género o edad no muestran un patrón tan marcado, mientras que tipo de contrato y método de pago sí.

La variable con mayor influencia negativa sobre Churn es Meses_Contrato, indicando que contratos más largos ayudan a retener clientes.

El gasto mensual y diario tiene un efecto positivo pero débil sobre la evasión.

La cantidad de servicios contratados no muestra impacto significativo directo sobre el Churn.

**Recomendaciones**

**1. Programas de retención temprana:** incentivos durante los primeros meses de suscripción.

**2. Ofertas personalizadas:** paquetes de servicios combinados para aumentar valor percibido.

**3. Fidelización continua:** comunicación proactiva, recordatorios de beneficios y mejoras de servicio.

**4. Monitoreo constante:** actualizar análisis y métricas de Churn regularmente para detectar cambios en tendencias.
