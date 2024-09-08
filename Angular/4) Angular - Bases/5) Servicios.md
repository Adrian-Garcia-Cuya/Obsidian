### Concepto 1
Los servicios son clases que encapsulan cierta funcionabilidad específica, y son reusables en diferentes partes de la aplicación.

### Concepto 2
Brindan una forma de separar los datos y funciones en una aplicación de Angular, que pueden ser utilizados por multiples componentes de la aplicación.

## Dependencia
Los servicios puedes ser usados en múltiples componentes, y para que esto sea posible, los servicios deben ser inyectables. Los servicos que son inyectables y usados en un componente, se convertirán en la dependencia de ese componente. Por lo tanto, los componentes dependerán de esos servicios y no funcionarán sin ellos.

## Inyección de dependencia
La inyección de dependencias es un mecanísmo que maneja las dependencias de un componente de la aplicación y los servicios que otros componentes pueden usar.

Ejemplo:

```Typescript
import { Injectable } from '@angular/core';
import { v4 as uuid } from 'uuid';
import { Character } from '../interfaces/characer.interface';

@Injectable({
	providedIn: 'root'
})

export class DbzService {

	public characters: Character[] = [
	
		{
			id: uuid(),
			name: 'Krilin',
			power: 1000
		},
		{
			id: uuid(),
			name: 'Goku',
			power: 9500
		
		},
		{
			id: uuid(),
			name: 'Vegueta',
			power: 7500
		}
	];

	addCharacter( character: Character): void {
		character.id = uuid();
		this.characters.push( character );
	}

  

	deleteCharacterById( id: string ): void {
		this.characters = this.characters.filter( character => character.id !== id );
	}
}
```

Para tener un servicio, se debe utilizar el decorador **@Injectable**, el cuál, convertirá la clase en un servicio.

Para usarlo, solo se debe importar el servicio y agregarlo al constructor. Angular inyectará el servicio al componente.

```Typescript
import { DbzService } from './../services/dbz.service';
import { Component } from '@angular/core';

@Component({
	selector: 'app-dbz-main-page',
	templateUrl: './main-page.component.html'
})
export class MainPageComponent {
	constructor( private dbzService: DbzService ) {}
}
```