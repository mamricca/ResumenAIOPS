# Clase 10 - Isolation Forest
- ## Idea principal
  
  Cada observación se representa mediante un vector de features. Durante el funcionamiento normal del sistema, las observaciones se concentran en determinadas regiones del espacio.
- Regiones de alta densidad → muchas observaciones similares.
- Regiones de baja densidad → pocos vecinos.
  
  Las regiones de baja densidad corresponden a combinaciones poco frecuentes de KPI y representan posibles anomalías.
  
  ---
- ## Aproximación local
  
  En lugar de estudiar un punto exacto, se analiza una pequeña región alrededor de la observación.
- Muchas observaciones cercanas → alto soporte local.
- Pocas observaciones cercanas → bajo soporte local.
  
  La relación entre los conceptos es:
  
  | Concepto | Interpretación |
  | ---- | ---- |
  | p(x) baja | combinación de KPI poco frecuente |
  | Poco soporte local | pocos vecinos cercanos |
  | Volumen | tamaño de la región donde buscamos vecinos |
  | Aislamiento rápido | consecuencia esperada al particionar recursivamente el espacio |
  
  **Idea clave:** baja densidad ⇒ poco soporte local ⇒ aislamiento rápido.
  
  ---
- ## Idea de Isolation Forest
  
  Si particionamos el espacio repetidas veces hasta separar completamente las observaciones, podemos medir qué tan fácil resulta aislar cada punto.
  
  Cada nodo del árbol:
- elige una variable al azar;
- selecciona un umbral uniforme dentro del rango de esa variable;
- divide las observaciones en dos subconjuntos.
  
  Cuando un punto posee pocos vecinos cercanos, existe una mayor probabilidad de que un corte aleatorio lo separe rápidamente del resto.
  
  Isolation Forest no estima explícitamente la densidad; utiliza la facilidad de aislamiento como una aproximación a la rareza estadística.
  
  ---
- ## Profundidad esperada
  
  Se define (c(n)) como la profundidad promedio esperada de un árbol construido con (n) observaciones.
  
  Como cada árbol de Isolation Forest se construye utilizando una submuestra de tamaño [ψ (Subsampling)](<ψ (Subsampling).md>) , la normalización utiliza **c(ψ)**.
- Profundidad mucho menor que c(ψ)→ posible anomalía.
- Profundidad cercana a (c(\psi)) → comportamiento habitual.
  
  La recursión termina cuando:
- el nodo contiene una única observación;
- existen observaciones duplicadas que impiden seguir dividiendo;
- se alcanza la profundidad máxima definida por la implementación.
  
  ---
- ## [Score de Liu](<Score de Liu.md>)
  
  Se entrenan **m** árboles independientes utilizando submuestras de tamaño **ψ**.
  
  La profundidad de una observación se promedia entre todos los árboles.
- Profundidad muy inferior a (c(\psi)) → score cercano a 1 → anomalía.
- Profundidad cercana a (c(\psi)) → score cercano a 0,5 → comportamiento normal.
  
  ---
- ## Hiperparámetros
- ### [ψ (Subsampling)](<ψ (Subsampling).md>) 
  
  Tamaño de la submuestra utilizada para construir cada árbol.
- Reduce el costo computacional.
- Hace que cada árbol vea una parte distinta del dataset.
- Valores iniciales habituales: (2^8) a (2^{10}).
- ### m
  
  Cantidad de árboles del bosque.
- Más árboles → score más estable.
- Habitualmente entre 100 y 200 árboles.
- ### [Contamination](<Contamination.md>)
  
  Define qué porcentaje de observaciones con mayor score se clasificará como anomalía.
  
  Por ejemplo, contamination = 0.02 clasifica aproximadamente el 2 % de observaciones con score más alto como outliers.
  
  ---
- ## Riesgos
  
  Isolation Forest es poco interpretable.
  
  Una forma de interpretar sus resultados consiste en analizar qué variables aparecen con mayor frecuencia en los cortes cercanos a la raíz, ya que suelen ser las que más contribuyen al aislamiento de las anomalías.
  
  <!--EndFragment-->