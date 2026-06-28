## Definición

El Moving Average (MA) es una técnica de suavizado que reemplaza cada observación por el promedio de una ventana de valores recientes.
- ## Objetivo
  
  Reducir el ruido de una [Serie Temporal](<Serie Temporal.md>) para hacer más visibles las tendencias y los patrones.
- ## Funcionamiento
  
  Se selecciona una ventana de tamaño fijo y se calcula el promedio de las observaciones contenidas en ella.
  
  A medida que avanza la serie, la ventana se desplaza y el promedio se recalcula.
- ## Ventajas
- Reduce el ruido.
- Hace más visibles las tendencias.
- Es simple de implementar.
- ## Desventajas
- Introduce un retraso temporal.
- Responde lentamente a cambios bruscos.
- ## Uso
  
  El Moving Average puede utilizarse para:
- suavizar series temporales;
- realizar [Forecasting](<Forecasting.md>) simple;
- calcular estadísticas móviles como el [Rolling Z-Score](<Rolling Z-Score.md>).
- ## Idea clave
  
  El Moving Average reduce las fluctuaciones de corto plazo promediando las observaciones recientes.
- ## Relacionado
- [Serie Temporal](<Serie Temporal.md>)
- [Rolling Z-Score](<Rolling Z-Score.md>)
- [Exponentially Weighted Moving Average (EWMA)](<Exponentially Weighted Moving Average (EWMA).md>)
- [Forecasting](<Forecasting.md>)