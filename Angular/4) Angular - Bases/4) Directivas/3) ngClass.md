Agrega o remueve clases CSS en un elemento HTML.

Puede agregar o actualizar clases dependiento del tipo de evaluación de la expresión:
- `string` : agrega las clases específicas en la cada.
- `array` : agrega las clases declaradas en el arreglo.
- `object` : las clases son las "llaves" y son agregas cuando la expresión dada en el "valor" es `true`.

Ejemplo:
```HTML
<ul class="list-group">
	<li *ngFor="
		let character of characterList;
		let i = index;
		let isFirst = first;
		let isLast = last
		let isEven = even
		let isOdd = odd"
		class="list-group-item"
		[ngClass]="{
		'list-group-item-dark': isLast,
		'list-group-item-primary': isEven
		}">
```

Para esta ocasión la expresión js que se indica es la de un objeto. Lo que hará es agregar una clase si el número es par y agregar la otra clase si es impar.