# **NodeLists vs Array**

**NodeLists** es un objeto que devuelve un conjunto de nodos.

Un **Array** es una colección de elementos.

Un nodeList es devuelto al pedir nodos con "querySelectorAll".

Podemos convertir el nodeList a Array de la siguientes formas:

**1) Primera forma**

const nodeList = document.querySelectorAll('div'); //almacenamos la nodeList devuelta en una variable

const array = \[...nodeList\]; //se utiliza el sprint operator.

**2) Segunda forma** (esta forma es más recomendada)

const nodeList = document.querySelectorAll('div');

array = ==**Array.form**==(nodeList);

const nodeList = document.querySelectorAll('div');

array = ==**Array.form**==(nodeList);