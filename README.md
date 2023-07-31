# Deep learning CNN para la detección de enfermedades de piel en perros
Para la construcción del modelo se utilizó la técnica conocida como *"Transfer learning"*. El modelo se basa en la red neuronal donominada `Xception` (https://arxiv.org/abs/1610.02357).

## Formato de entrada
El modelo únicamente realiza inferencias sobre imágenes que cumplan con los siguientes requisitos:
1. Los formatos aceptados: `jpeg`, `jpg` and `png`.
2. Las dimensiones (altura y ancho) de la imagen deben ser: `224x224`. 
3. Los píxeles de la imagen deben tener valores entre: `0 - 1`.
4. La imagen debe contar con `3` canales (RGB).

## Clases
Las clases en la que se clasifican los resultados del modelo son: `'Dermatitis piotraumatica'`, `'dermatofitosis'`, `'miasis'` and `'otra'`.

## Formato de salida
El resultado de este modelo es un vector que contiene el valor de las activaciones de la última capa del modelo. En otras palabras, el vector tendrá el valor de probabildad de que la imagen pertenezca a cada una de las clases que componen el modelo.
La posición del elemento en el vector se corresponde con la clase a la que pertenece, es decir, el elemento en la posición `0` se corresponde con la clase `dermatitis piotraumatica` y así con el resto de los elementos.
Dado que la activación de la última capa es `softmax` la suma de todos los valores del vector será aproximadamente `1`.