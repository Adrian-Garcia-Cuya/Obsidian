## ngFor
Es una directiva estructural que renderiza una plantilla por cada elemento en una colección. Ésta directiva se agrega dentro de un elemento que se convertirá en el padre de las plantillas clonadas.

Ejemplo:
```HTML
<ul class="mt-2 list-group">
	<li *ngFor="let name of heroNames"
		class="list-group-item">
		{{ name }}
	</li>
</ul>
```

También, los siguientes valores exportados pueden asignarse a variables locales:
- `index: number`: El indice del actual elemento en la colección.
- `count: number`: La longitud de la colección.
- `first: boolean`: True cuando el elemento es el primero en la colección.
- `last: boolean`: True cual elemento es el último en la colección.
- `even: boolean`: True cuando el elemento tiene un índice par en la colección.
- `odd: boolean`: True cuando el elemento tiene un índice impar en la colección.

Ejemplo: 
```HTML
<h4>Listado</h4>
<ul class="list-group">
	<li *ngFor="
	let character of characterList;
	let i = index;
	let isFirst = first;
	let isLast = last
	let isEven = even
	let isOdd = odd"
	class="list-group-item">
	
	<span class="text-primary"> {{ i + 1 }}. </span>
	
	<span>{{ character.name }} - </span>
	
	<strong>power: </strong>
	
	<span>{{ character.power }}</span>
	
	</li>
</ul>

```
"Los valores exportados se asignan a las siguientes variables locales: `i`, `isFirst`, `isLast`, `isEven` e `isOdd`. Estas variables pueden ser usadas dentro de la plantilla."