## Definición

**ψ (psi)** representa el tamaño de la submuestra utilizada para construir cada árbol de Isolation Forest.

En lugar de utilizar todo el conjunto de datos, cada árbol se entrena con una muestra aleatoria de ψ observaciones.
- ## Objetivos
- Reducir el costo computacional.
- Hacer que cada árbol vea una parte distinta del dataset.
- Aumentar la diversidad entre árboles.
- Reducir el efecto del **masking**, donde varias anomalías cercanas pueden ocultarse entre sí.
- ## Relación con la profundidad esperada
  
  La profundidad promedio esperada depende del tamaño del árbol.
  
  Como cada árbol contiene **ψ** observaciones, la normalización del [Score de Liu](<Score de Liu.md>) utiliza **c(ψ)** en lugar de **c(n)**.
- Profundidad mucho menor que **c(ψ)** → posible anomalía.
- Profundidad cercana a **c(ψ)** → comportamiento habitual.
- ## Valores habituales
  
  Como punto de partida suelen utilizarse valores entre:
- 2⁸ = 256 observaciones.
- 2¹⁰ = 1024 observaciones.
- ## Consideraciones
- ψ pequeño
	- árboles más rápidos;
	- menor costo computacional;
	- suele ser suficiente para detectar anomalías.
- ψ grande
	- árboles más profundos;
	- mayor costo computacional;
	- pocas mejoras adicionales una vez alcanzado un tamaño razonable.
- ## Idea clave
  
  Isolation Forest no necesita construir árboles utilizando todo el dataset. Las anomalías suelen poder detectarse utilizando submuestras relativamente pequeñas.
- ## Relacionado
- [Semana 10 - Isolation Forest](<../clases/Semana 10 - Isolation Forest.md>)
- [Score de Liu](<Score de Liu.md>)