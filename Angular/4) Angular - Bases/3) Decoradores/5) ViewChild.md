Este decorador declara que una propiedad será una referencia a un elemento del DOM, directiva o componente hijo en la plantilla.

Es de utilidad cuando es necesario interactuar con un componente del DOM o manipular un componente hijo luego de que angular renderice la vista.

Para poder hacer la referencia referencia se puede pasar el _tipo de clase_, _referencia local_ o su _selector CSS_.

``` Typescript
import { Component, ElementRef, ViewChild } from '@angular/core';

  

@Component({

selector: 'gifs-search-box',

template: `
	<h5>Buscar: </h5>
	<input
	type="text"
	placeholder="Buscar gifs..."
	class="block w-full rounded border-2 p-2 border-slate-700 focus:outline-none"
	(keyup.enter)="searchTag()"
	#txtTagInput >
`,

})

export class SearchBoxComponent {

	@ViewChild( 'txtTagInput' )
	public tagInput!: ElementRef<HTMLInputElement>;

	searchTag( ): void {
		const newTag = this.tagInput.nativeElement.value;
		console.log({ newTag });
	}
}
```

En primer lugar, para usar _@viewChild_ se debe importar del paquete '@angular/core'.

En este caso se utiliza para hacer referencia al "input" y poder mostrar el valor que se introduce en este elemento.

Antes que nada, se esta usando una _referencia local_ llamada **#txtTagInput**, la cual, va a representar al input en la plantilla.

En el componente se declara la propiedad _tagInput_ como referencia al elemento "input" con nombre _tagInput_ (que es su referencia local). Esto con la finalidad de mostrar por consola el valor introducido en el elemento, para ello, se usa **nativeElement.value**.