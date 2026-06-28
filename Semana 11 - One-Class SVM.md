- Clase 11
  
  para SVM la geometría (distancias, magnitudes) determina qué tan separables son las clases. Más adelante el [[Kernel RBF]] redefinirá esa noción de distancia en un espacio transformado.
  
  el producto interno mide la alineación entre vectores. Si <x,y> > 0 apuntan en una dirección similar, si es negativo apuntan en direcciones opuestas y si vale 0 son ortogonales. En un SVM decidimos según el signo de <w,x> + b; luego, con el [[Kernel Trick]], el producto interno se reemplaza por una función kernel.
  
  la función del hiperplano es:
  
  **wᵀx + b = 0**
- **w** determina la orientación del hiperplano y es perpendicular a él.
- **b** desplaza el hiperplano respecto del origen.
- El signo de **wᵀx + b** indica de qué lado del hiperplano se encuentra una observación.
  
  un hiperplano es una superficie de dimensión d−1 que divide el espacio en dos mitades. Un SVM busca el hiperplano que mejor separa dos clases.
  
  el objetivo del SVM no es solamente separar correctamente las clases, sino hacerlo dejando la mayor distancia posible entre ellas, es decir, maximizar el margen. Los puntos que tocan los hiperplanos que delimitan el margen,
- wᵀx + b = 1
- wᵀx + b = -1
  
  son los [[Support Vectors]], ya que son los únicos que determinan la posición final del hiperplano. El margen resulta ser **2/||w||**, por lo que maximizar el margen equivale a minimizar **||w||**.
  
  en datos reales las clases suelen solaparse o contener ruido, por lo que normalmente no existe un hiperplano que clasifique todas las observaciones sin errores. Para esto se utiliza el [[Soft Margin]] , que permite algunas violaciones del margen mediante variables de holgura (slack variables), penalizando esos errores en la función objetivo.
  
  la función objetivo busca un equilibrio entre maximizar el margen y minimizar las violaciones del margen. El hiperparámetro [[C]] controla ese compromiso:
- **C grande:** penaliza mucho los errores de clasificación, ajustando más el modelo a los datos de entrenamiento.
- **C pequeño:** permite más errores a cambio de un margen mayor y una mejor capacidad de generalización.
  
  para resolver este problema de optimización se utilizan los [[Multiplicadores de Lagrange]], que permiten incorporar las restricciones de clasificación dentro de la función objetivo. Como resultado, la solución depende únicamente de los [[Support Vectors]].
  
  cuando los datos no pueden separarse mediante un hiperplano lineal se utiliza el [[Kernel Trick]], que reemplaza el producto interno por una función kernel. Esto permite trabajar implícitamente en un espacio de mayor dimensión sin calcular explícitamente la transformación de los datos.
  
  el [[Kernel RBF]] mide la similitud entre dos observaciones según su distancia. Observaciones cercanas tienen una similitud alta, mientras que observaciones lejanas tienen una similitud baja. Gracias a esto pueden construirse fronteras de decisión no lineales.
- ## [[One-Class SVM]]
  
  en AIOps normalmente no existen ejemplos etiquetados de fallas, por lo que One-Class SVM se entrena únicamente con observaciones normales y aprende una frontera que encierra el comportamiento habitual del sistema.
  
  una vez entrenado:
- observaciones dentro de la frontera → comportamiento normal.
- observaciones fuera de la frontera → posibles anomalías.
  
  el modelo calcula una función de decisión:
- **f(x) ≥ 0:** la observación pertenece a la región normal.
- **f(x) < 0:** la observación se considera una anomalía.
  
  el hiperparámetro [[ν (Nu)]] controla la cantidad esperada de anomalías y la complejidad de la frontera.
- **ν pequeño:** frontera más amplia y menos anomalías detectadas.
- **ν grande:** frontera más ajustada y mayor sensibilidad.
  
  el hiperparámetro [[γ (Gamma)]] controla el alcance de la influencia de cada observación en el [[Kernel RBF]].
- **γ pequeño:** cada observación influye sobre una región amplia, obteniendo una frontera más suave.
- **γ grande:** la influencia es muy local, generando fronteras más complejas y con mayor riesgo de sobreajuste.
  
  antes de entrenar One-Class SVM es importante escalar las variables para que todas tengan una influencia comparable en el cálculo de similitudes.
  
  comparando ambos métodos:
- [[Semana 10 - Isolation Forest]]: detecta anomalías mediante aislamiento con cortes aleatorios. Escala muy bien a grandes volúmenes de datos y su principal hiperparámetro es [[Contamination]].
- [[One-Class SVM]]: aprende una frontera alrededor del comportamiento normal utilizando un [[Kernel RBF]]. Modela fronteras complejas y sus principales hiperparámetros son [[ν (Nu)]] y [[γ (Gamma)]].
  
  los tres enfoques vistos hasta ahora detectan observaciones poco habituales utilizando estrategias diferentes:
- [[Modelo generativo]]: estima la distribución o densidad de los datos.
- [[Semana 10 - Isolation Forest]]: mide qué tan rápido puede aislarse una observación.
- [[One-Class SVM]]: aprende una frontera que delimita la región de comportamiento normal.