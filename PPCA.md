## Definición

Probabilistic Principal Component Analysis (PPCA) es una versión probabilística de [PCA](<PCA.md>) que modela cómo se generan los datos a partir de un conjunto reducido de variables latentes.
- ## Idea
  
  En lugar de reducir la dimensionalidad únicamente desde un punto de vista geométrico, PPCA asume que cada observación se genera mediante:
- un vector latente **z** de baja dimensión;
- una transformación lineal;
- un término de ruido.
  
  De esta forma, una observación **x** puede reconstruirse a partir de **z**.
- ## ¿Para qué sirve?
  
  PPCA permite:
- reducir la dimensionalidad;
- reconstruir observaciones;
- estimar el error de reconstrucción;
- modelar la generación de datos;
- generar nuevas observaciones compatibles con el comportamiento normal.
- ## Detección de anomalías
  
  Si una observación no puede reconstruirse correctamente, el error de reconstrucción será alto, indicando que probablemente no siga el patrón aprendido por el modelo.
- ## Diferencia con [PCA](<PCA.md>)
- **PCA:** busca representar los datos con menos dimensiones.
- **PPCA:** además propone un modelo probabilístico sobre cómo se generan esos datos.
- ## Idea clave
  
  PPCA combina la reducción de dimensionalidad de [PCA](<PCA.md>) con un modelo generativo probabilístico, permitiendo representar, reconstruir y generar observaciones.
- ## Relacionado
- [PCA](<PCA.md>)
- [Likelihood](<Likelihood.md>)
- [Clase 9 - Modelos Generativos](<Clase 9 - Modelos Generativos.md>)