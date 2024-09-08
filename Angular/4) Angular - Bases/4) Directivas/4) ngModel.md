Es una directiva que conecta un **elemento de entrada de la vista** con una variable del componente. Esto permite que los cambios fluyan entre el modelo (componente) y la vista. 

Cuando se usa en modo bidireccional, si la variable del componente cambia, el valor mostrado en el elemento de entrada de la vista también se actualiza automáticamente para reflejar el nuevo valor de la variable, y viceversa. También puede usarse en modo unidireccional para reflejar datos del componente en la vista sin permitir modificaciones desde la vista.

Ejemplo:

```Typescript
export class AddCharacterComponent {

	public character: Character = {
		name: '',
		power: 0
	}
}
```

```HTML
<input
	type="text"
	name="name"
	[(ngModel)]="character.name"
	class="form-control mb-2"
	placeholder="Nombre">
```

En este ejemplo se define un atributo "character" de tipo **Character**. Ahora, en la plantilla, en el elemento de entrada ( input ) se utiliza la directiva "ngModel", la cual, está utilizando el enlace de doble vía, ya que, como se puede ver, se especifíca mediante el uso de "[()]".

Las llaves permite el enlace de una sola vía, es decir, mostrar el valor del atributo en el elemento de entrada, y los parentesís, permite que el valor que recibe el input se envíe al atributo del componente.

