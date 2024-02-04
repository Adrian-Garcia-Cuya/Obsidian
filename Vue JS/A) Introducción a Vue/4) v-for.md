La directiva ==v-for== permite realizar iteraciones. Ese bucle realizará sus iteraciones dependiendo de la cantidad de elementos en el array. Es como un bucle "foreach".

# Uso de v-for
Se ingresa como primer valor la variable que va a tomar cada elemento del array, y como segundo valor el array.

En el ejemplo a continuación se esta iterando un array de objetos.

```HTML
<ul>
	<li v-for="pais in paises">
		{{pais.name}}
	</li>
</ul>
```

Para mostrar un dato, usas la interpolación e ingresas el primer valor (pais) y usas la nomenclatura del punto para acceder a la propiedad del objeto (name).

## Acceder al número de iteración
Para realizar esto es necesario que ingreses como valor un paréntesis al comienzo y dentro de esto agregues el valor que va recorrer los elementos y como segundo valor el ==index==.

Veamos un ejemplo:

```HTML
<ul>
	<li v-for="(pais, index) in paises">
			{{index + 1}} - {{pais.name}} - {{pais.capital}}
	</li>
</ul>
```

## LLave
Para que Vue realice un correcto seguimiento de los elementos, al realizar CRUD, recomienda agregar una llave al bucle. Este debe ser agregado solo en campos únicos. Como por ejemplo un id, correo, etc.
```HTML
<ul>
	<li v-for="(pais, index) in paises"  :key="pais.name">
			{{index + 1}} - {{pais.name}} - {{pais.capital}}
	</li>
</ul>
```
En este caso no hay un identificador unico pero podria ser un 'id'. La llave se podria decir que ayuda a especificar quien es el valor que identificara a los datos que se imprimen en el momento del bucle.

# Otra forma de usar el v-for
Esto se logra simplemento agregado una etiqueta "template" la cual tendrá el bucle y dentro del el los elementos que quieres mostrar.

Veamos un ejemplo:
```HTML
<template v-for="(pais, index) in paises">
	<li :key="pais.name">
			{{index + 1}} - {{pais.name}} - {{pais.capital}}
	</li>
</template>
```
El resultado sería el mismo. Esto es similar al uso del foreach en otros lenguajes.