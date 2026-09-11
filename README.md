# Análisis de Retención por Cohortes para una Startup Tecnológica
### 1. Resumen:
Análisis en Excel para evaluar el comportamiento de retención y abandono (churn) de los clientes de una startup . Mediante la construcción de una matriz de cohortes basada en la fecha de registro, buscamos responder una pregunta clave para el negocio: ¿la empresa cuenta con las bases necesarias para escalar la adquisición de usuarios, o debe priorizar la optimización del producto para consolidar el Product Market Fit (PMF)?
### 2. Herramientas: 
- Microsoft Excel
- Power Query
- Tablas dinámicas
- Fórmulas de búsqueda y referencia
- Formato condicional para matrices de cohortes
### 3. Datos:
Contiene 330 clientes registrados, donde cada fila representa un cliente.
Esta distribuido en 2 tablas: de retención mensual y de retención trimestral. En sus columnas figuran el nombre del cliente, el estado del cliente , el mes de registro, el mes de abandono (churn) y los 24 meses desde el 2019 al 2020.
  
![Gráfico de columnas de retención mensual](https://github.com/gabcadi30/analisis-cohortes-retencion-clientes-excel/blob/main/assets/data_original.png)

En las columnas mensuales:
 - **1** representa que el cliente permaneció activo durante el mes;
 - **0** representa que el cliente ya no se encontraba activo.

Los datos originales se encuentra en: [Proyecto 2: Retención Startup Tecnológica ](https://www.kaggle.com/datasets/datacertlaboratoria/proyecto-2-startup-tecnolgica)

### 4.Preguntas a resolver:
   - Pregunta Principal : ¿La startup debería destinar la inversión a la adquisición de nuevos usuarios?
   - Preguntas Complementarias:
  - - ¿Cómo evoluciona la retención conforme aumenta la antigüedad de los clientes?
  - - ¿En qué periodo del ciclo de vida se concentra la mayor cantidad de abandonos?
  - - ¿Las cohortes más recientes presentan una retención mejor o peor que las anteriores?
  - - ¿Existen señales suficientes para afirmar que el producto ha alcanzado Product-Market Fit?
       
### 5. Proceso de Análisis:
Los archivos CSV fueron importados y transformados mediante Power Query. Posteriormente, el análisis se desarrolló mediante dos matrices complementarias:

1. **Matriz de retención mensual:** se agruparon los clientes según su mes de registro y se sumaron los indicadores mensuales de actividad. Las cohortes fueron alineadas según su antigüedad mediante las funciones `INDICE`, `COINCIDIR` y `COLUMNAS`. Luego se calculó el porcentaje de clientes que permaneció activo durante cada mes.

2. **Matriz de abandono o churn trimestral:** se agruparon los clientes según su trimestre de registro y el trimestre en el que abandonaron el servicio. Esta matriz permitió identificar en qué etapa del ciclo de vida se concentraron las cancelaciones.

Durante la preparación de la segunda matriz se identificaron dos registros inconsistentes: figuraban como activos, pero tenían una fecha de abandono. Ambos se conservaron en la fuente, se clasificaron como inválidos y se excluyeron únicamente del análisis de churn.

Finalmente, se aplicó formato condicional a ambas matrices para facilitar la comparación entre cohortes y reconocer patrones de retención y abandono.

![Matriz de Retencion Mensual](assets/matriz_retencion_mensual.png)

![Matriz de abandono trimestrall ](assets/matriz_churn_trimestral.png)


> [Ver el proceso completo, fórmulas y capturas de pantalla](proceso_analisis.md)


