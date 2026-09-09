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
