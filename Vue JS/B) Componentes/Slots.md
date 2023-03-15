Este elemento es un "slot outlet" que indica dónde se debe mostrar el "slot content" que ha sido proporcionado por las plantillas padres.

Un ejemplo claro es esta imagen. 
![[slot.png]]
La plantilla padre proporciona el slot content("click me" en este caso) y la etiqueta "slot", que está insertada dentro de la etiqueta button, indica que será reemplazado por el "slot content" ("click me").

Al final el DOM renderiza:
```HTML
<button class="fancy-btn">Click me!</button>
```

Veamos otro ejemplo:

Como se puede ver, en esta plantilla se está proporcionando la etiqueta "p" (slot content).
```HTML
<div id="app">
    <div :style="{ fontSize: textSize + 'em'}">
	    <detail-course @crecer-texto="crecer" :curso="course" >
	        <p>Este es el mejor curso que puedes encntrar en la web</p>
	    </detail-course>
    </div>
</div>
```

En la plantilla del componente se inserta donde debe ir esa etiqueta, por ello el slot (slot outlet) está arriba de la etiqueta "button".
```Javascript
app.component('detail-course', {
    data() {
        return {
            
        }
    },
    props: ['curso'],
    template: `
        <h1>{{curso.name}}</h1>
        <p>El precio del curso es: {{curso.price}}</p>
        <slot></slot>
        <button @click="$emit('crecerTexto', 0.2)">Incrementar tamaño</button>
    `
})
```

Al final se renderiza de la siguiente forma:

![[example_slot.png]]