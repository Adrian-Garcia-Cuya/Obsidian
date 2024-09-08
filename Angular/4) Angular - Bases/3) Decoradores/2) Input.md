## Input
Este decorador marca la propiedad de la clase como un campo de entrada y brinda configuraciones de metadatos. La propiedad de entrada esta vinculada/enlazada a una propiedad DOM en la plantilla. El ciclo de detección de Angular actualiza automaticamente la propiedad de entrada con el valor de la propiedad DOM

Permite enviar datos del componente padre al hijo.

*Options:*
- alias? ->  El nombre de la propiedad DOM, la cual, la propiedad de entrada está vinculada.

Ejemplo:
##### Componente padre
```Typescript
export class MainPageComponent {

	public characters: Character[] = [
		{
			name: 'Krilin',
			power: 1000
		},
		{
			name: 'Goku',
			
			power: 9500
		},
		{
			name: 'Vegueta',
			power: 7500
		}
	];
}
```

```HTML
<div class="row">
	<div class="col">
		<dbz-list [characterList]="characters" ></dbz-list>
	</div>
</div>
```

Aquí se envía los datos del atributo "characters" a la propiedad **characterList**, la cuál, está vinculada a la propiedad de entrada del componente hijo.
##### Componente hijo

```Typescript
export class ListComponent {

@Input()
public characterList: Character[] = [
		{
			name: 'Trunk',
			power: 10
		
		}
	];
}
```

En el componente hijo, se convierte la propiedad **characterList**, en una propiedad de entrada mediante el uso del decorador _@Input_.