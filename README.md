# TelecomX_Parte2

## Descripción:
El objetivo del proyecto fue la cración de modelos de machine learning que puedan identificar eficientemente a clientes con mayor probabilidad de cancelar sus servicios con Telecom X a través de la preparación de los datos contenidos en el archivo tratado generado en la entrega del reporte TelecomX_LATAM, sobre el cuál se hizo una codificación de variables, normalización, análisis de correlación, etc. Para posteriormente crear 2 modelos predictivos, entrenarlos y evaluarlos y así poder generar recomendaciones estratégicas basadas en la interpretación de los resultados obtenidos con los modelos

## Tabla de contenidos del proyecto:
1. Exploración y preparación de Datos
   * Encoding.
   * Verificación de la proporción de cancelaciones.
   * Normalización de Datos.
2. Correlación y selección de variables
3. Separación de Datos.
4. Creación de Modelos
   * Random Forest
     + Evaluando el modelo Random Forest Classifier
   * Regresión Logística.
     + Evaluando el modelo de Regresión Logística.
   * Balanceo de Clases y uso de datos balanceados en los modelos.
     + Para Random Forest.
     + Para Regresión Logística.
5. Análisis de la importancia de variables.
6. Conclusiones.

## Principales librerías utilizadas:
1. Pandas
2. Scikit-learn
4. Seaborn
5. Matplotlib
6. Plotly

## Hallazgos:
Ambos modelos tuvieron mejor desempeño con balanceo de clases y el modelo Random Forest tuvo un mejor desempeño que el de Regresión logística como se detalla a continuación:

🔹 Regresión Logística (Clase 1)
   + Precision: 0.57
   + Recall: 0.66
   + F1: 0.62
   + Accuracy: 0.78

🔹 Random Forest (Clase 1)
   + Precision: 0.76
   + Recall: 0.84
   + F1: 0.80
   + Accuracy: 0.89

Como podemos ver, Random Forest mejora:
+18 puntos en recall (0.66 → 0.84)
+19 puntos en F1
+11 puntos en accuracy
+19 puntos en precision

Lo cuál indica una mejora estructural.
Random Forest predice mejor la cancelación ya que esta está determinada por relaciones no lineales y porque existe una interacción entre variables
Al analizar la importancia de las variables en ambos modelos podemos ver que:
  * Los clientes con menor antiguedad y con contratos mes a mes son los más propensos a cancelar, lo cuál es reforzado por la alta correlación entre estas dos variables y la correlación significativa entre cada una de ellas        con el "Churn".
  * De igual forma vemos una importante influencia de la variable "Charges_Montly" (costo mensual) lo cuál indica que esta variable también influye en la decisión de cancelación de los clientes.

La importancia de las variables arrojada por los modelos así como las correlaciones entre variables obtenidas son consistentes con el análisis de Datos y el informe realizado en la entrega previa (TelecomX_LATAM).

## Recomendaciones hechas:
  * Migración a contratos de uno o 2 años: Ofrecer mayores beneficios para clientes que contraten los servicios por al menos un año y de igual forma ofrecer incentivos a aquellos clientes que cambien su contrato mensual a un       contrato por uno o dos años. Estos beneficios pueden ser descuentos, precios preferenciales, mejoras en el tipo de servicio, etc.
  * Evaluación de clientes que cumplan con las características de poco tenure, contrato mes a mes, con costos mensuales elevados más las indicadas en el reporte TelecomX_Latam implementando el modelo Random Forest para             predecir la cancelación, generando alertas y así dar prioridad a esos clientes en las campañas de retención/conslidación de la relación de negocios.

Al implementar estas recomendaciones junto con las propuestas en el informe TelecomX_LATAM, la empresa mejorará la consolidación de la relación de negocios con clientes actuales y nuevos clientes lo que llevará a reducir el número de cancelaciones existente y a la vez, servirá para incrementar la calidad de los serivicios y atención ofrecida por la compañía a sus clientes.
