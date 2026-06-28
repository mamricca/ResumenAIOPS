## Definición

γ (gamma) es un hiperparámetro del [Kernel RBF](<Kernel RBF.md>) que controla el alcance de la influencia de cada observación.
- ## Funcionamiento
- **γ pequeño**
	- Cada observación influye sobre una región amplia.
	- La frontera de decisión es más suave.
	- Mayor capacidad de generalización.
	- Riesgo de subajuste.
- **γ grande**
	- Cada observación influye solo sobre su vecindad.
	- La frontera de decisión es más compleja.
	- Mayor capacidad para ajustarse a los datos.
	- Riesgo de sobreajuste.
- ## Interpretación
  
  γ controla qué tan "local" es la noción de similitud del [Kernel RBF](<Kernel RBF.md>).
- γ bajo → los puntos lejanos siguen siendo relativamente similares.
- γ alto → la similitud disminuye rápidamente con la distancia.
- ## Idea clave
  
  γ controla la complejidad de la frontera de decisión aprendida por [One-Class SVM](<One-Class SVM.md>).
- ## Relacionado
- [Kernel RBF](<Kernel RBF.md>)
- [One-Class SVM](<One-Class SVM.md>)