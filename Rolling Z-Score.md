## Definición

El Rolling Z-Score compara una observación con la media y el desvío estándar de una ventana móvil reciente.
- ## Objetivo
  
  Detectar valores inusuales considerando únicamente el contexto reciente de la serie.
- ## Interpretación
- |z| pequeño → comportamiento esperado.
- |z| > 3 → posible anomalía.
- ## Ventaja
  
  Se adapta a cambios graduales del comportamiento normal al utilizar estadísticas calculadas sobre una ventana móvil.
- ## Idea clave
  
  El Rolling Z-Score mide cuántos desvíos estándar se encuentra una observación respecto de su contexto reciente.
- ## Relacionado
- [[Moving Average (MA)]]
- [[Serie Temporal]]