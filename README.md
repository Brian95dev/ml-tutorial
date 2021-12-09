# MLTutorial

1. Del script de forest fires:

  a. ¿Se desea resolver el problema utilizando aprendizaje supervisado o no supervisado? ¿Es un problema de clasificación o de regresión?
  
  R/ En éste caso se busca resolver el problema haciendo uso de aprendizaje supervisado, específicamente basado en regresión lineal.
  
  b. ¿Qué interpretación le puede dar a los resultados obtenidos?
  
  R/ Tomando en cuenta los valores de error absoluto promedio, raiz del error cuadrático medio y en especial el coeficiente de determinación, que resultó ser negativo, se evidencia que las predicciones de nuestro modelo tienen altos valores de error, de hecho éstas predicciones se encuentran tan lejos de los valores correctos que una linea horiziontal a través de la media de se ajusta mejor a los datos, que la línea obtenida por la regresión lineal. Debido a ésto, es recomendable obtener más datos y/o cambiar el modelo de predicción utilizado.


2. Del script de recursos humanos (rrhh):

  a. ¿Cuál es la clase para la que el modelo más se equivoca? ¿Por qué?
  
  R/ Basándonos en la matriz de confusión obtenida apartir del modelo, se evidencia un porcentaje de acierto en el conjunto de valores predichos (se puede interpretar como verdaderos positivos y negativos, sólo que tenemos 3 opciones en vez de un caso binario) del 61% en la clase objetivo de salario alto, en el caso de salario bajo es del 50% y finalmente, en el caso de salario medio es del 62%. Por lo que la clase para la que el modelo más equivoca corresponde a aquella en la que la menor cantidad de valores predichos concuerdan con los valores reales, la cual es salario bajo.
  
  
  b. ¿Cuál cree que es el propósito del parámetro max_depth usado al momento de instanciar el modelo de árbol de decisión?
  
  R/ Definir la profunidad máxima del árbol, en éste caso equivale a la misma altura dado que ningún nodo podrá tener una profundidad mayor a la altura del árbol, al usar el plot tree para dibujar el árbol, se evidencia que se respeta la altura máxima de 5, dado que ningún nodo tiene una profunidad mayor a éste valor. En la práctica ésto limita el alcance del árbol de decisión, lo cual puede ser eficiente en tiempo de ejecución para casos dónde se obtengan resultados estables sin necesidad de tener un árbol de altura ilimitada.
  
  c. Para este caso particular, ¿por qué cree que es difícil obtener un buen clasificador?
  
  R/ Incluso al remover la limitación de altura se siguen presentando porcentajes de error considerables, ésto probablemente se debe al desbalanceo de clases dado por la predominancia de salarios medios y bajos, por sobre los salarios altos en el dataset, así que puede ser necesario un mayor preprocesamiento de los datos. Por otra parte, vale la pena revisar si de verdad es relevante la clase objetivo planteada, dado que podría tener más sentido predecir por ejemplo el atributo left, para predecir bajo que condiciones se están retirando los empleados, o tal vez rangos del atributo satisfaction level, para conocer las condiciones que pueden general malestar/bienestar en los empleados y tomar decisiones al respecto. Así mismo hay que revisar que tan relevantes para el caso son atributos como number_project o si debemos ignorarlo y agregar tal vez atributos más importantes en el contexto.
  
3. Identificación de géneros musicales: Tenga en cuenta que hay dos scripts: music.ipynb y music-multiclass.ipynb. En el primero se intenta crear un modelo clasificador solo para dos clases (caso binario) y en el segundo se entrena uno para todas las clases (géneros musicales) del dataset.

  a. Para el caso binario (jazz and blues vs. soul and reggae) ¿Es posible obtener mejores métricas entrenando un modelo basado en Random Forest?
  
  R/
   
  b. Escoja otro par de géneros, entrene un conjunto de modelos y documente los resultados del mejor que se haya obtenido.
  
  R/
  
  c. Para el caso multi-clase, ¿cuál es la clase para la que el modelo más se equivoca? ¿Por qué?
  
  R/
  
  d. Para el caso multi-clase, el modelo basado en red neuronal parece estar mayoritariamente sesgado hacia un género particular. ¿Cuál género cree que es?
  
  R/
  
4. Segmentación de cajas de compensación familiar (subsidio):

  a. ¿Qué cajas de compensación parecen ser mayoritariamente diferentes a las demás?
    
  R/  Las cajas de compensación presentes en los cluster 1 y 3 parecen ser mayoritariamente diferentes debido al tamaño reducido de sus siluetas en comparación a los clusters 0 y 2, adicionalmente, el cluster 3 tiene un coeficiente menor al promedio en el modelo original.
  
  b. ¿A partir de qué características utilizadas para el entrenamiento del modelo se podría explicar la razón por la que las cajas anteriores fueron agrupadas en clusters tan pequeños?
  
  R/ Este agrupamiento sucede puesto que las cajas de los cluster más pequeños se encuentran mas cerca del centroide de dichos clusters, es decir, los atributos de estas cajas son más similares entre sí, en comparación a las cajas que se en cuentran en el cluster más grandes.
  
  c. ¿Se pueden obtener resultados más homogéneos utilizando cantidades diferentes de clusters para el entrenamiento? Entienda homogeneidad como clusters con cantidades similares de instancias de datos.

  R/ No exactamente. Al aumentar el número de clusters uno por uno hasta 9 por ejemplo, se evidencia que es posible alcanzar un mayor nivel de homogeneidad entre la mayoría de los clusters existentes, sin embargo, varios clusters resultan completamente vacíos y por lo menos uno considerablemente más grande que el resto. Por otra parte, al disminuir el número de clusters uno por uno hasta llegar a 2, se incrementa la desigualdad entre clusters, dónde uno resulta mucho más poblado, mientras que 1 o 2 clusters aparte tienen a ser muy pequeños, aunque homogeneos entre ellos.
