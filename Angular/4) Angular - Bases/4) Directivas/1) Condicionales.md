## ngIf
La directiva estructural _*ngIf_  permite renderizar condicionalmente una plantilla dependiendo del valor de la expresión (==true or false==).

Ejemplo:

```HTML
<button
	*ngIf="name === 'iron man'"
	(click)="changeHero('Spiderman')"
	class="btn btn-primary mx2">
	Cambiar nombre
</button>
```

Si la expresión es verdadera, es decir, name es igual a 'iron man', Angular renderizará el botón, caso contrario, no lo mostrará.

Luego de validar la expresión, es normal querer mostrar una u otra plantilla en caso no se cumpla la condición. Para ello, existe  el 'else'. 

Ejemplo:
```HTML
<div *ngIf="deletedHero; else nothingWasDeleted">
	<h3>Héroe borrado <small class="text-danger">{{ deletedHero }}</small> </h3>
</div>

<ng-template #nothingWasDeleted>
	<h3>No ha borrado nada</h3>
</ng-template>
```

Después de especificar la condición, se agrega *";"*  y el *else*, donde se puede observar un nombre. Este es hace referencia al contenido que se requiere renderizar en caso de que la condición sea falsa.

En el [[Templates#ng-template|ng-template]] se agrega la referencia simplemente dandole el mismo nombre con un *#*.