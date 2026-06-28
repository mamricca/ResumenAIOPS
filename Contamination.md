## Definición

**Contamination** es un hiperparámetro que indica la proporción esperada de anomalías en el conjunto de datos.

Se utiliza para determinar el umbral a partir del cual una observación será clasificada como anómala.
- ## Funcionamiento
  
  Una vez calculado el [[Score de Liu]] para todas las observaciones:
- Se ordenan los scores de mayor a menor.
- Se selecciona el porcentaje indicado por **Contamination**.
- Esas observaciones se clasifican como anomalías.
- ## Ejemplo
  
  Si:
- Contamination = **0.02**
- Dataset = **10.000** observaciones
  
  Entonces se clasifican aproximadamente las **200 observaciones con mayor score** como anomalías.
- ## Efecto del parámetro
- Contamination alto
	- Detecta más anomalías.
	- Aumenta el riesgo de falsos positivos.
- Contamination bajo
	- Detecta menos anomalías.
	- Disminuye los falsos positivos, pero puede aumentar los falsos negativos.
- ## Importante
  
  Contamination **no modifica cómo se construyen los árboles ni cómo se calcula el Score de Liu**.
  
  Únicamente determina el punto de corte utilizado para convertir el score en una clasificación (normal o anomalía).
- ## Relacionado
- [[Isolation Forest]]
- [[Score de Liu]]
- [[Anomalía]]