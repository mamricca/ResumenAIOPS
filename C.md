## Definición

C es un hiperparámetro de SVM que controla el equilibrio entre maximizar el margen y minimizar los errores de clasificación.
- ## Funcionamiento
- **C grande**
	- Penaliza fuertemente las violaciones del margen.
	- El modelo intenta clasificar correctamente la mayor cantidad posible de observaciones.
	- Puede reducir el margen y aumentar el riesgo de sobreajuste.
- **C pequeño**
	- Permite más violaciones del margen.
	- Favorece un margen más amplio.
	- Generaliza mejor frente a nuevos datos.
- ## Idea clave
  
  C controla el compromiso entre ajustar el modelo a los datos de entrenamiento y obtener una buena capacidad de generalización.
- ## Relacionado
- [Soft Margin](<Soft Margin.md>)
- [One-Class SVM](<One-Class SVM.md>)