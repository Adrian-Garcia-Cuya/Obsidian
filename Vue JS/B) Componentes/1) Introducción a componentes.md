Los componentes permiten dividir las interfaz en piezas ==independientes y reutilizables==.

Se pueden agregar estilos y funcionalidades js a los componentes.

Es normal que una aplicación se organice en un árbol de componentes anidados.
![[Árbol_de_componentes.png]]
# Crear un componente
Para crear un componente se pasa un método llamado "component".

Ccomo primer argumento se pasa el nombre del componente (button-counter) y como segundo parametro un objeto, donde se definirá las propiedades, algún método que pueda tener y el "template"(código html que se quiere mostrar).

```Javascript
const app = Vue.createApp({
    data() {
        return {
            message: 'hola Vue',
            count: 5
        }
    }
});
app.component('button-counter', {
    data() {
        return {
            count: 0
        }
    },
    template: //código html que se mostrará cada vez que se llame a este componente
    `   <button @click="count++">
            Haz echo click {{count}} veces
        </button>`
});
```
###### Nota (componente)
Cada componente es diferente, son independientes, y manejan sus propios datos.

# Usar componente
Para usarlo simplemente ingresas su nombre, como si fuera una etiqueta.
```HTML
<div id="app">
	<button-counter></button-counter>
	<button-counter></button-counter>
	<button-counter></button-counter>
</div>
```
