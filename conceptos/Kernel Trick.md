# Kernel RBF

- ## Definición
  
  El Kernel RBF (Radial Basis Function o Kernel Gaussiano) es una función kernel que mide la similitud entre dos observaciones según la distancia que existe entre ellas.
- ## Funcionamiento
- Observaciones cercanas → similitud alta.
- Observaciones lejanas → similitud baja.
  
  Gracias a esta medida de similitud, el modelo puede construir fronteras de decisión no lineales.
- ## Hiperparámetro [γ (Gamma)](<γ (Gamma).md>)
  
  γ controla el alcance de la influencia de cada observación.
- γ pequeño:
	- influencia amplia;
	- frontera más suave;
	- menor riesgo de sobreajuste.
- γ grande:
	- influencia local;
	- frontera más compleja;
	- mayor riesgo de sobreajuste.
- ## Uso
  
  Es el kernel utilizado habitualmente en [One-Class SVM](<One-Class SVM.md>) para modelar regiones de comportamiento normal con formas complejas.
- ## Idea clave
  
  El Kernel RBF no mide únicamente la distancia entre observaciones, sino su similitud. Cuanto más cerca se encuentran dos puntos, mayor es el valor del kernel y más similares se consideran.