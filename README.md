# Análisis de Retención por Cohortes para una Startup Tecnológica
## 1. Resumen:
Análisis de cohortes en Excel para evaluar el comportamiento de los usuarios en el modelo de suscripción mensual de un software durante el 2019 y 2020 . A través de la construcción de matrices de cohorte de retención mensual y abandono trimestral, este proyecto busca responder a una pregunta clave para el negocio: ¿la empresa cuenta con las bases necesarias para escalar la adquisición de usuarios, o debe priorizar la optimización del producto para consolidar el Product Market Fit (PMF)?
> Fuente de datos: [Proyecto 2: Retención Startup Tecnológica ](https://www.kaggle.com/datasets/datacertlaboratoria/proyecto-2-startup-tecnolgica)
## 2. Herramientas: 
- Microsoft Excel
- Power Query
- Tablas dinámicas
- Fórmulas de búsqueda y referencia
- Formato condicional para matrices de cohortes
## 3. Datos:
Contiene 330 clientes registrados (331 filas considerando el encabezado), donde cada fila representa un cliente.
El dataset está distribuido en 2 tablas: de retención mensual y de retención trimestral. En sus columnas figuran el nombre del cliente, el estado del cliente , el mes de registro, el mes de abandono (churn) y los 24 meses desde el 2019 al 2020.
  
![Gráfico de columnas de retención mensual](https://github.com/gabcadi30/analisis-cohortes-retencion-clientes-excel/blob/main/assets/data_original.png)

En las columnas mensuales:
 - **1** representa que el cliente permaneció activo durante el mes;
 - **0** representa que el cliente ya no se encontraba activo.

> 📥 [Descargar el archivo Excel del análisis](excel/analisis_cohortes_retencion_clientes.xlsx)

## 4. Preguntas a resolver:
**Pregunta Principal :**
     ¿La startup debería destinar la inversión a la adquisición de nuevos usuarios?
**Preguntas Complementarias:**
  - - ¿Cómo evoluciona la retención conforme aumenta la antigüedad de los clientes?
  - - ¿En qué periodo del ciclo de vida se concentra la mayor cantidad de abandonos?
  - - ¿Las cohortes más recientes presentan una retención mejor o peor que las anteriores?
  - - ¿Existen señales suficientes para afirmar que el producto ha alcanzado Product-Market Fit?
       
## 5. Proceso de Análisis:
Los archivos CSV fueron importados y transformados mediante Power Query. Posteriormente, el análisis se desarrolló mediante dos matrices complementarias:

1. **Matriz de retención mensual:** se agruparon los clientes según su mes de registro y se sumaron los indicadores mensuales de actividad. Las cohortes fueron alineadas según su antigüedad mediante las funciones `INDICE`, `COINCIDIR` y `COLUMNAS`. Luego se calculó el porcentaje de clientes que permaneció activo durante cada mes.

2. **Matriz de abandono o churn trimestral:** se agruparon los clientes según su trimestre de registro y el trimestre en el que abandonaron el servicio. Esta matriz permitió identificar en qué etapa del ciclo de vida se concentraron las cancelaciones.

Durante la preparación de la segunda matriz se identificaron dos registros inconsistentes: figuraban como activos, pero tenían una fecha de abandono. Ambos se conservaron en la fuente, se clasificaron como inválidos y se excluyeron únicamente del análisis de churn.

Finalmente, se aplicó formato condicional a ambas matrices para facilitar la comparación entre cohortes y reconocer patrones de retención y abandono.

> Para revisar el proceso del análisis completo y las formulas usadas, ingrese [aquí](proceso_analisis.md)

## 6. Hallazgos importantes:
![Matriz de Retencion Mensual](assets/matriz_retencion_mensual.png)
- Las cohortes de enero y febrero de 2019 presentan los mejores porcentajes de retención de largo plazo. La cohorte de enero de 2019 mantuvo activo al 63,64 % de sus clientes después de 24 meses, mientras que la cohorte de febrero conservó al 61,54 % después de 23 meses.

- Sin embargo, este comportamiento no fue uniforme entre las cohortes más antiguas. En marzo de 2019, solo el 30,77 % de los clientes permaneció activo después de 22 meses. Asimismo, al completar un año de suscripción, la cohorte de abril de 2019 registró una retención de 46,67 %, mientras que la cohorte de septiembre de 2019 alcanzó el 50 %.
  
- En 2020 se registraron 197 clientes nuevos, frente a los 133 incorporados durante 2019. Esto representa un incremento de aproximadamente 48,12 % en la captación de clientes. Sin embargo, el crecimiento en nuevas suscripciones no estuvo acompañado necesariamente de una mejor retención.

- La cohorte de mayo de 2020, que fue la segunda con mayor cantidad de clientes nuevos, mantuvo activo solo al 64 % de sus usuarios al finalizar el octavo mes. Este resultado constituyó la segunda retención más baja entre las cohortes que alcanzaron ese mismo periodo de observación.

- La retención más baja en el octavo mes correspondió a la cohorte de marzo de 2020, con apenas un 45,45 % de clientes activos. Esta cohorte había registrado un 54,55 % de retención en el sexto mes, lo que demuestra que continuó perdiendo usuarios durante los meses posteriores.

![Matriz de abandono trimestral ](assets/matriz_churn_trimestral.png)

- La matriz de abandono muestra que las mayores tasas promedio de churn se concentran durante los primeros periodos de permanencia. El tercer trimestre presenta el promedio más alto, con un 10,4 %, seguido del segundo trimestre, con un 9,8 %. A partir del cuarto trimestre, la tasa promedio comienza a disminuir, aunque se observan incrementos puntuales en algunas cohortes.

- Las cohortes registradas durante 2020 presentan, en general, mayores tasas de abandono temprano que las cohortes de 2019. Esta diferencia se observa especialmente durante el segundo trimestre: la cohorte 2020-T1 alcanzó un 14,3 % de abandono, seguida por la cohorte 2020-T3 con un 13,5 % y la cohorte 2020-T2 con un 12,7 %.

- No obstante, la tasa de abandono individual más alta de toda la matriz corresponde a la cohorte 2019-T3, que registró un 17,4 % durante su tercer trimestre de permanencia. Esta misma cohorte volvió a presentar un porcentaje elevado en el quinto trimestre, con un 13 %, lo que evidencia que su pérdida de clientes no se limitó a una sola etapa.

## 7. Conclusiones:
- El mayor volumen de clientes nuevos en el 2020 no estuvo acompañado de una mejora en su permanencia.
- Las cohortes de 2020 mostraron mayores dificultades de retención, donde el mayor riesgo de abandono se concentra entre los meses 4 y 9.
- La antigüedad de una cohorte no garantiza una mayor retención, aunque enero y febrero de 2019 destacaron por su gran porcentaje de permanencia a largo plazo.
- Finalmente, los resultados no ofrecen evidencia suficiente para afirmar que el producto haya alcanzado Product-Market Fit y tampoco se recomienda aún invertir en captación de nuevos usuarios. 

## 8. Recomendaciones:
- Implementar acciones de fidelización y acompañamiento durante los primeros tres meses e investigar las causas de abandono mediante encuestas o entrevistas.
- Comparar las características y experiencias de las cohortes con mejor y peor desempeño para identificar factores relacionados con la permanencia.
- Revisar si hubo cambios en el producto, en el perfil de los clientes captados o en el proceso de incorporación durante 2020 que pudo afectar la experiencia de los nuevos clientes.
- Finalmente, antes de incrementar la inversión destinada a captar nuevos clientes, se recomienda priorizar la mejora de la retención.
  










