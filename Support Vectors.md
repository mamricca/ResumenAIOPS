## Definición

Los Support Vectors son las observaciones más cercanas al hiperplano de decisión.

En un SVM son los puntos que se encuentran sobre los hiperplanos que delimitan el margen.
- ## ¿Por qué son importantes?
  
  Los Support Vectors son las únicas observaciones que determinan la posición del hiperplano óptimo.
  
  Mover un Support Vector modifica el hiperplano, mientras que mover una observación alejada del margen generalmente no cambia la solución.
- ## Relación con el margen
  
  Los Support Vectors se encuentran sobre los hiperplanos:
- wᵀx + b = 1
- wᵀx + b = -1
  
  La distancia entre estos dos hiperplanos constituye el margen.
- ## En la optimización
  
  Al resolver el problema mediante [Multiplicadores de Lagrange](<Multiplicadores de Lagrange.md>), únicamente los Support Vectors tienen multiplicadores distintos de cero.
  
  Por eso la solución final depende únicamente de ellos.
- ## Idea clave
  
  Los Support Vectors "sostienen" el margen del SVM: son los puntos críticos que determinan la frontera de decisión.
- ## Relacionado
- [Soft Margin](<Soft Margin.md>)
- [C](<C.md>)
- [Multiplicadores de Lagrange](<Multiplicadores de Lagrange.md>)
- [Kernel Trick](<Kernel Trick.md>)
- [One-Class SVM](<One-Class SVM.md>)