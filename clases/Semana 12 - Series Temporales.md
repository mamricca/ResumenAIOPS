- Gran parte de los datos operacionales tienen una dimensión temporal, por lo que una observación generalmente no puede entenderse sin considerar el pasado.
  
  Una [Serie Temporal](<../conceptos/Serie Temporal.md>) es una secuencia ordenada de observaciones donde cada una está asociada a un instante de tiempo. Sobre una serie temporal podemos preguntarnos si existe una tendencia, ciclos o [Estacionalidad](<../conceptos/Estacionalidad.md>), qué parte corresponde a [Ruido Blanco](<../conceptos/Ruido Blanco.md>), si existen anomalías o incluso predecir valores futuros mediante [Forecasting](<../conceptos/Forecasting.md>).
  
  La correlación mide la relación entre dos variables aleatorias, mientras que la [Autocorrelación (ACF)](<../conceptos/Autocorrelación (ACF).md>) mide la correlación de una serie consigo misma desplazada en el tiempo. Ese desplazamiento se denomina [Lag](<../conceptos/Lag.md>).
  
  La [Autocorrelación (ACF)](<../conceptos/Autocorrelación (ACF).md>) grafica la autocorrelación para distintos lags. Esto permite responder si la serie tiene memoria, si los valores recientes ayudan a predecir los futuros, si existen patrones repetitivos o si la serie se comporta como ruido.

- Una ACF que cae rápidamente implica poca memoria temporal.
- Una ACF alta durante muchos lags indica tendencia o persistencia.
- Picos periódicos en la ACF indican [Estacionalidad](<../conceptos/Estacionalidad.md>).
  
  Ejemplos:
- **Ruido Blanco:** no existe tendencia ni estacionalidad, ya que las observaciones son independientes y la ACF es cercana a cero para todos los lags mayores que 0.
- **Tendencia con Ruido:** la serie presenta un crecimiento o decrecimiento sostenido. Observaciones cercanas suelen parecerse y la ACF permanece alta durante muchos lags.
- **Estacionalidad con Ruido:** el patrón se repite periódicamente y la ACF presenta picos separados por el período de la serie.
  
  Para convertir una [Serie Temporal](<../conceptos/Serie Temporal.md>) en un dataset tabular se utilizan [Sliding Windows](<../conceptos/Sliding Windows.md>). Cada ventana de tamaño fijo se transforma en una fila del dataset, permitiendo utilizar algoritmos tradicionales de Machine Learning.
- ## Tipos de Anomalías
- [Point Anomaly](<../conceptos/Point Anomaly.md>): una observación individual es claramente diferente de las demás.
- [Contextual Anomaly](<../conceptos/Contextual Anomaly.md>): el valor solo es anómalo debido al contexto temporal (por ejemplo, romper un patrón estacional).
- [Collective Anomaly](<../conceptos/Collective Anomaly.md>): ninguna observación individual parece anómala, pero el patrón completo sí, como un memory leak o una degradación progresiva.
- ## Suavizado de Series
  
  Las métricas operacionales suelen contener ruido, que puede ocultar tendencias, cambios de comportamiento o anomalías.
  
  El [Moving Average (MA)](<../conceptos/Moving Average (MA).md>) reemplaza cada observación por el promedio de una ventana de valores recientes. Esto reduce el ruido y hace más visibles las tendencias, aunque introduce cierto retraso temporal.
  
  Sobre una ventana móvil pueden calcularse estadísticas como la media y el desvío estándar.
  
  Comparando una observación con su contexto reciente mediante el [Rolling Z-Score](<../conceptos/Rolling Z-Score.md>) podemos detectar valores inusuales. Valores de |z| > 3 suelen considerarse posibles anomalías.
  
  El [Exponentially Weighted Moving Average (EWMA)](<../conceptos/Exponentially Weighted Moving Average (EWMA).md>) asigna mayor peso a las observaciones recientes, por lo que responde más rápido a cambios que un promedio móvil simple.
- ## [Forecasting](<../conceptos/Forecasting.md>)
  
  El objetivo del forecasting es estimar valores futuros de una serie temporal a partir de las observaciones pasadas.
  
  Algunos métodos simples son:
- **Naive:** predice que el próximo valor será igual al último observado. Es un baseline fuerte cuando la serie cambia lentamente.
- [Moving Average (MA)](<../conceptos/Moving Average (MA).md>): predice utilizando el promedio de las últimas observaciones. Reduce el ruido, pero responde lentamente a cambios bruscos.