Es un conjunto de funcionabilidades centradas en una necesidad específica de la aplicación.

## ngModule
Es un decorador que convierte una clase en un NgModule(módulo) y brinda metadatos de configuración, que permitirá definir el comportamiento de un módulo.

*Opciones:*
- providers ->  El conjunto de objetos inyectables que están disponibles en este módulo.
- declarations -> El conjunto de componentes, directivas y pipes que pertenecen al módulo.
- imports -> El conjunto de NgModules cuyas "declarables" exportadas están disponibles para las plantillas del módulo actual. En otras palabras, los componentes declarados y exportados de otros modulos estarán disponibles en las plantillas del módulo que las importe.
- exports -> El conjunto de componentes, directivas y pipes declarados en un NgModule, pueden utilizarse en la plantilla de cualquier componente que forme parte de un NgModule que importe el otro NgModule que exporta estos elementos.

Ejemplo:

```Typescript
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule } from '@angular/forms';
import { MainPageComponent } from './pages/main-page.component';
import { ListComponent } from './components/list/list.component';
import { AddCharacterComponent } from './components/add-character/add-character.component';

@NgModule({
	declarations: [
		MainPageComponent,
		ListComponent,
		AddCharacterComponent
	],
	
	imports: [
		CommonModule,
		FormsModule
	],
	
	exports: [
		MainPageComponent
	]
})

export class DbzModule { }
```