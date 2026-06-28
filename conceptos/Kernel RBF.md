## Definición

El Kernel Trick permite aplicar algoritmos lineales sobre datos que no son linealmente separables, sin calcular explícitamente una transformación a un espacio de mayor dimensión.
- ## Idea
  
  En lugar de transformar cada observación y luego calcular el producto interno, el kernel calcula directamente el resultado de ese producto en el espacio transformado.
  
  De esta forma se obtiene el mismo efecto con un costo computacional mucho menor.
- ## ¿Por qué se utiliza?
  
  Cuando un hiperplano lineal no alcanza para separar correctamente los datos, el Kernel Trick permite construir fronteras de decisión no lineales.
- ## En One-Class SVM
  
  One-Class SVM utiliza el Kernel Trick para aprender una frontera flexible que encierra el comportamiento normal del sistema.
- ## Idea clave
  
  El Kernel Trick permite trabajar implícitamente en un espacio de mayor dimensión reemplazando el producto interno por una función kernel, sin calcular la transformación de los datos.