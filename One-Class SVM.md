## Objetivo

Detectar anomalías aprendiendo una frontera que encierra el comportamiento normal del sistema.

En lugar de separar dos clases, One-Class SVM se entrena únicamente con observaciones normales y considera anomalías a las observaciones que quedan fuera de la frontera aprendida.
- ## Ver
- [[Clase 11]]
- ## Conceptos relacionados
- [[Kernel Trick]]
- [[Kernel RBF]]
- [[γ (Gamma)]]
- [[ν (Nu)]]
- [[Support Vectors]]
- [[Soft Margin]]
- [[C]]
- [[Multiplicadores de Lagrange]]
- ## Idea clave
  
  One-Class SVM aprende una frontera alrededor del comportamiento normal. Las observaciones que quedan fuera de esa frontera se consideran anomalías.