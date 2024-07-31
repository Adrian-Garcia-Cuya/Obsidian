# Introducción
Buenas tardes profesor y compañeros.

En esta ocasión nos tocó exponer sobre el árbol de decisión.

``Breve resumen del arbol``
Este tiene como fin poder ver la estructura jerarquica de decisiones para poder predecir las variables dependientes a partir de las pariables independientes.

Este algoritmo pertenece a la rama de lenguaje supervisado, el cual, a su vez pertenece al tipo clasificación, en este caso.

Este modelo tiene como objetivo predecir a que clase pertenece una planta. En este caso de tiene una "una clasificación multiclase" debio a que se tienen más de 2 posibles valores; son 3 (iris-setosa, iris-versicolor, iris-virginica).

# Explicación del algoritmo
Ahora, explicare como se ha se desarrollado este modelo. 

Lo primero que se hizo fue importar la libreria pandas y se le dio el alias "pd". Luego, utilizamos la funcion "read" para leer el dataset "iris" y asi poder mostrar, de manera rapida, las 5 primeras filas de este conjunto de datos.

Después, se va a separar las columnas (VI) de las clases (VD) y se almacenarán en sus respectivas variables, "x" y "y".

Como se puede ver, estoy tomando las 4 columnas con la funcion "iloc". 

Luego, estoy importanto una función de la libreria sklearn llamada "LabelEncoder" la cual nos permitirá transformar una variable no númerica a numérica. Esto se hace porque los algoritmos de ML trabajan mejor con variables númericas. 

Con la función "fit" se hará un entrenamiento para que identifique los valores únicos (i-s,iv,iv) de las características y los valores por los que se van a reemplazar(0,1,2). Con la función "transform" reemplazamos los valores.

# Explicación del modelo
Ahora, se esta importando la funcion "train_test_split" de la libreria sklearn. Esto nos va a permitir separar en 2 bloques la data, uno para el entramiento del modelo y otro para la prueba.

Como se puede ver, esta función recibe algunos argumentos, como las variables independientes y las variables dependientes. luego se debe especificar el tamaño de la separación, normalmente se escoge el 30% de los datos para la prueba y el 70% restante para entrenar el modelo, y este es el caso.

En x_train irá el 70% de los datos para entrenar, en x_test el 30% restante. Los mismos para las etiquetas o VD. 

Luego, se utiliza StandarScaler de la libreria sklearn para realizar el escalado. Esto con la finalidad de que las caracteristicas se encuentren en la misma escala y asi poder generar un modelo más precisio en sus predicciones.

Lo que se está haciendo es instanciar un objeto "sc" y luego realizar el escalado con fit_transform, se le pasa los datos de entrenamiento, y tambien va a remplezar los valores con la escala generada.

ahora, vamos a crear el modelo. Importamos "DecisionTreeClassifier" el cual no va a permitir crear un modelo "clasificador de arbol de decision "

Como se puede ver aqui se crea el modelo y se le esta dando como argumento que tome como "criterio" lo que es la entriopia. Esto nos permite saber la impureza de un conjunto de datos.







