## Definición

ν (nu) es un hiperparámetro de [One-Class SVM](<One-Class SVM.md>) que controla la cantidad esperada de anomalías y la complejidad de la frontera.
- ## Funcionamiento
- **ν pequeño**
	- Frontera más amplia.
	- Menos observaciones clasificadas como anomalías.
- **ν grande**
	- Frontera más ajustada.
	- Más observaciones clasificadas como anomalías.
- ## Interpretación
  
  ν puede interpretarse como:
- una **cota superior** de la fracción de anomalías esperadas durante el entrenamiento;
- una **cota inferior** de la fracción de support vectors.
- ## Efecto práctico
  
  A medida que ν aumenta, el modelo se vuelve más sensible y detecta una mayor cantidad de anomalías.
- ## Idea clave
  
  ν controla el compromiso entre una frontera conservadora y una frontera más estricta alrededor del comportamiento normal.
- ## Relacionado
- [One-Class SVM](<One-Class SVM.md>)