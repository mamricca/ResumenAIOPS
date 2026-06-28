## Objetivo

Asignar a cada observación un puntaje que indique qué tan probable es que sea una anomalía.
- ## Idea
  
  Isolation Forest construye múltiples árboles independientes.
  
  Para cada observación:
- Se calcula la profundidad a la que queda aislada en cada árbol.
- Se promedian esas profundidades.
- El promedio se compara con la profundidad esperada de un árbol construido con una submuestra de tamaño **ψ**.
- ## Interpretación
- La profundidad promedio es **mucho menor** que la esperada → la observación se aisló rápidamente → score alto → posible anomalía.
- La profundidad promedio es **similar** a la esperada → comportamiento habitual → score cercano a 0,5.
- ## Valores típicos
- Score cercano a **1** → anomalía muy probable.
- Score cercano a **0,5** → comportamiento normal.
- Score mucho menor que **0,5** → observación muy difícil de aislar (región muy densa).
- ## Relación con la profundidad
- Menor profundidad → mayor score.
- Mayor profundidad → menor score.
  
  La profundidad se normaliza utilizando **c(ψ)** para poder comparar árboles construidos con el mismo tamaño de submuestra.
- ## Relación con [[Contamination]]
  
  El score **no decide por sí solo** si una observación es una anomalía.
  
  Primero se calcula el score de todas las observaciones y luego **Contamination** determina el umbral de corte, clasificando como anomalías el porcentaje de observaciones con score más alto.
- ## Idea clave
  
  El Score de Liu transforma la profundidad promedio de aislamiento en un valor normalizado que permite ordenar las observaciones desde las más normales hasta las más anómalas.