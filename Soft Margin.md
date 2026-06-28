## Definición

El Soft Margin permite que algunas observaciones violen el margen o incluso sean clasificadas incorrectamente cuando las clases no son perfectamente separables.
- ## Objetivo
  
  Obtener un modelo más robusto frente a ruido y solapamiento entre clases.
- ## Relación con [C](<C.md>)
  
  El hiperparámetro C controla cuánto se penalizan esas violaciones:
- C grande → menos errores permitidos.
- C pequeño → más errores permitidos.
- ## Idea clave
  
  En datos reales suele ser preferible permitir algunos errores antes que forzar una separación perfecta que sobreajuste el modelo.