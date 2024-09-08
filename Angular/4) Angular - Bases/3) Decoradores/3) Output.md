Es un decorador que convierte un campo de clase en una **propiedad de salida** y brinda configuraciones de metadatos.

La finalidad del decorador es poder emitir eventos desde un componente hijo hacia un componente padre. Esto permite que el componente hijo se comunique con el padre, enviandole datos o notificando que se debe realizar una acción.

Ejemplo:
#### Componente hijo

```Typescript
export class AddCharacterComponent {

	@Output()
	public onNewCharacter: EventEmitter<Character> = new EventEmitter();
	
	public character: Character = {
		name: '',
		power: 0
	}

	emitCharater(): void {
		if ( this.character.name.length === 0 ) return;
		
		this.onNewCharacter.emit(this.character);
		
		this.character = { name: '', power: 0}
	}
}
```

Se debe importar la clase _EventEmitter_ para poder emitir un evento. En este caso se indica que en la emisión del evento se enviará un dato de tipo _Character_  y luego se realizá una instancia. Para  emitir el evento solo hay que usar el método emit, este recibe opcionalmente un valor que se requiera emitir.
#### Componente padre

```HTML
<dbz-add-character (onNewCharacter)="onNewCharacter( $event )" ></dbz-add-character>
```

Se usan los paréntesis para indicar un _enlace de evento_, es decir, cuando se dispare un evento en DOM te permitirá ejecutar un método de tu componente, en este caso **onNewCharacter()**.

A mencionar, que la variable "$event" tiene el valor dado al emitir el evento.