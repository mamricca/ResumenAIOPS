## Definición

Los multiplicadores de Lagrange son una herramienta matemática utilizada para resolver problemas de optimización con restricciones.
- ## En SVM
  
  Permiten incorporar las restricciones de clasificación dentro de la función objetivo, resolviendo simultáneamente:
- maximizar el margen;
- respetar las restricciones de clasificación.
  
  Como resultado, la solución queda determinada únicamente por los [Support Vectors](<Support Vectors.md>).
- ## ¿Por qué son importantes?
  
  Gracias a la formulación de Lagrange se obtiene la formulación dual del problema, sobre la cual puede aplicarse el [Kernel Trick](<Kernel Trick.md>).
- ## Idea clave
  
  Los multiplicadores de Lagrange permiten resolver el problema de optimización de SVM con restricciones y son la base matemática que posibilita el uso de kernels.
- ## Relacionado
- [Kernel Trick](<Kernel Trick.md>)
- [Support Vectors](<Support Vectors.md>)