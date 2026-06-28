## Definición

Sliding Windows es una técnica para convertir una [Serie Temporal](<Serie Temporal.md>) en un dataset tabular.

Consiste en tomar ventanas consecutivas de tamaño fijo, donde cada ventana se transforma en una fila del dataset.
- ## ¿Para qué sirve?
  
  Muchos algoritmos de Machine Learning esperan ejemplos independientes. Sliding Windows permite representar una serie temporal en ese formato.
- ## Ejemplo
  
  Serie:
  
  x₁ x₂ x₃ x₄ x₅
  
  Ventana de tamaño 3:
- (x₁,x₂,x₃) → x₄
- (x₂,x₃,x₄) → x₅
  
  Cada ventana constituye un ejemplo de entrenamiento.
- ## Idea clave
  
  Sliding Windows transforma una serie temporal en un conjunto de ejemplos apto para algoritmos tradicionales de Machine Learning.
- ## Relacionado
- [Serie Temporal](<Serie Temporal.md>)
- [Forecasting](<Forecasting.md>)
- [Lag](<Lag.md>)