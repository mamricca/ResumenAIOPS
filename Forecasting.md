## Definición

El forecasting consiste en estimar valores futuros de una [[Serie Temporal]] utilizando las observaciones del pasado.
- ## Objetivo
  
  Dada una serie:
  
  x₁, x₂, ..., xₜ
  
  predecir:
  
  xₜ₊₁, xₜ₊₂, ...
- ## Métodos básicos
- ### Naive
  
  Predice que el próximo valor será igual al último observado.
- Muy simple.
- Funciona como baseline.
- No reacciona a cambios importantes.
- ### [[Moving Average (MA)]]
  
  Predice utilizando el promedio de las últimas observaciones.
- Reduce el ruido.
- Responde lentamente a cambios bruscos.
- ## Modelos más avanzados
  
  Existen modelos que además consideran:
- [[Tendencia]]
- [[Estacionalidad]]
- [[Autocorrelación (ACF)]]
  
  para mejorar las predicciones.
- ## Idea clave
  
  El forecasting utiliza el comportamiento pasado de una serie temporal para estimar sus valores futuros.
- ## Relacionado
- [[Serie Temporal]]
- [[Moving Average (MA)]]
- [[Estacionalidad]]
- [[Autocorrelación (ACF)]]