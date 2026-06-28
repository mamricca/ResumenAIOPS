# Clase 9 - Detección estadística de anomalías y modelos generativos

- ## [Anomalía](<../conceptos/Anomalía.md>)
- Una anomalía es una **observación poco compatible con el comportamiento habitual del sistema**.
- Estadísticamente, es un evento que ocurre con **baja probabilidad bajo un modelo de comportamiento normal**.
- Los sistemas suelen presentar patrones repetitivos (CPU, latencia, tráfico, KPI), por lo que los datos normales se concentran en determinadas regiones del espacio de observaciones.
  
  ---
- ## [Variable aleatoria](<../conceptos/Variable aleatoria.md>) y [Distribución](<../conceptos/Distribución.md>)
- Una métrica observada puede modelarse como una **variable aleatoria**.
- La distribución describe qué valores son frecuentes y cuáles son raros.
- Como primera aproximación suele utilizarse una [Distribución normal](<../conceptos/Distribución normal.md>).
- ### [Distribución normal](<../conceptos/Distribución normal.md>)
- La **media** representa el comportamiento promedio esperado.
- El **desvío estándar** representa la variabilidad natural del sistema.
- Cuanto mayor sea el desvío estándar, mayor será la fluctuación esperada.
- ### [Z-Score](<../conceptos/Z-Score.md>)
- Mide cuántos desvíos estándar separan una observación de la media.
- Permite comparar observaciones considerando la variabilidad de la métrica.
- Cuanto mayor sea el valor absoluto del Z-Score, menos frecuente resulta la observación.
- Regla práctica: valores por encima de ±3 desvíos estándar suelen considerarse candidatos a anomalía.
  
  ---
- ## Contexto operacional
  
  Una rareza estadística **no implica necesariamente un incidente**.
  
  Puede deberse a:
- despliegues;
- tráfico nocturno;
- eventos especiales;
- tareas batch.
  
  Por ello, la detección de anomalías requiere además:
- contexto temporal;
- conocimiento operacional;
- reducción de falsos positivos.
  
  ---
- ## [Modelos paramétricos](<../conceptos/Modelos paramétricos.md>)
  
  No todas las métricas siguen la misma distribución.
  
  Ejemplos:
- Latencia agregada → [Distribución normal](<../conceptos/Distribución normal.md>) o Log-normal.
- Errores por minuto → [Poisson](<../conceptos/Poisson.md>).
- Tiempo entre fallos → [Distribución exponencial](<../conceptos/Distribución exponencial.md>).
- Uso de CPU → Aproximadamente normal.
- Requests por ventana → [Poisson](<../conceptos/Poisson.md>).
- ### [Poisson](<../conceptos/Poisson.md>)
- Se utiliza para modelar variables de conteo.
- El parámetro λ representa la cantidad promedio esperada de eventos.
  
  ---
- ## [Likelihood](<../conceptos/Likelihood.md>)
  
  La likelihood mide **qué tan compatible es una observación con el modelo aprendido**.
- Likelihood alta → comportamiento esperado.
- Likelihood baja → posible anomalía.
  
  En variables continuas interesa la **densidad** alrededor de una observación, no la probabilidad de un valor exacto.
- ### [Soporte local](<../conceptos/Soporte local.md>)
- Regiones densas → muchas observaciones cercanas.
- Regiones con poco soporte → pocas observaciones cercanas.
  
  **Idea clave:** las anomalías aparecen en regiones de baja densidad o bajo soporte local.
  
  ---
- ## [Gaussian Mixture Model](<../conceptos/Gaussian Mixture Model.md>)
- ### Problema
  
  Una única distribución normal puede representar mal sistemas con distintos modos normales de funcionamiento (por ejemplo, tráfico diurno y nocturno).
- ### Idea
  
  Combinar varias distribuciones normales.
- Cada componente representa un modo de operación distinto.
- Cada componente posee un peso (π) que indica su importancia relativa.
- Permite modelar distribuciones multimodales.
  
  Las anomalías corresponden a observaciones alejadas de todas las componentes o ubicadas entre ellas, donde la densidad es baja.
  
  ---
- ## [Modelo generativo](<../conceptos/Modelo generativo.md>)
  
  En lugar de definir manualmente un modelo probabilístico, un modelo generativo aprende el comportamiento normal directamente a partir de los datos.
  
  Objetivos:
- aprender regiones densas;
- aprender relaciones entre variables;
- estimar likelihood;
- generar nuevas observaciones normales.
  
  Los parámetros del modelo son desconocidos y deben estimarse utilizando los datos de entrenamiento.
  
  ---
- ## [PCA](<../conceptos/PCA.md>)
- ### Objetivo
  
  Reducir la dimensionalidad de los datos.
- ### Idea
- Identifica variables correlacionadas.
- Las resume mediante un conjunto mucho menor de variables.
- La representación reducida se denomina [Espacio latente](<../conceptos/Espacio latente.md>).
- ### [Espacio latente](<../conceptos/Espacio latente.md>)
- Está representado por **z**.
- **z** es una versión comprimida de la observación original que conserva la mayor parte de la información.
- ### Reconstrucción
  
  A partir de **z** puede reconstruirse una aproximación de la observación original.
- Cuanto menor sea el error de reconstrucción, mejor representa **z** a los datos originales.
- ### Limitación
- PCA no es un modelo generativo.
- No permite calcular likelihood ni generar nuevas observaciones.
  
  ---
- ## [Probabilistic PCA](<../conceptos/Probabilistic PCA.md>)
  
  PPCA combina PCA con un modelo probabilístico.
- ### Idea
- Generar un factor latente.
- Agregar ruido gaussiano.
- Generar una observación.
- ### Ventajas
- Permite generar nuevas observaciones normales.
- Permite estimar likelihood.
- Modela explícitamente el ruido.
- ### Diferencia con PCA
- PCA reduce dimensionalidad.
- PPCA además modela cómo se generan los datos.
  
  ---
- # Resumen
- Una anomalía es una observación poco compatible con el comportamiento habitual.
- La rareza estadística no implica necesariamente un incidente.
- Las anomalías aparecen en regiones de baja densidad o bajo soporte local.
- Una única Gaussiana puede no representar correctamente varios modos normales de funcionamiento.
- Los modelos generativos aprenden el comportamiento normal y permiten estimar likelihood.
- PCA reduce dimensionalidad; PPCA convierte esa idea en un modelo probabilístico capaz de generar datos y calcular likelihood.
