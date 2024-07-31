En componente puede emitir eventos personalizados directamente en una plantilla. 

Se suele emitir eventos para comunicarse con el componente padre.

# Emitir
En este caso, se está emitiendo el evento desde un template.
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
        <button @click="$emit('crecerTexto', 0.2)">Incrementar tamaño</button>
    `
})
```
Lo que se está haciendo es escuchar el evento "click" para luego emitir el evento ==crecerTexto== y como segundo argumento se envia un dato.

# Escuchar evento
Para que el componente padre escuche el evento se utiliza la directiva "v-on".
```HTML
<div id="app">
    <template v-for="course in courses" :key="course.id">
        <div :style="{ fontSize: textSize + 'em'}">
            <detail-course @crecer-texto="textSize +=$event" :curso="course"></detail-course>
        </div>
    </template>
            
</div>
```
Al momento de escuchar el evento emitido sigue la siguiente sintaxis: "crecer==-==texto" y luego recibe la acción a realizar. En este caso es incrementar dinámicamente el tamaño de la fuente.

###### nota ($event)
Si al emitir un evento se envía un valor, para poder usarlo en el html se debe escribir la variable ==$event==. Internamente Vue asigna el valor que envías a esa variable.

# Crear método que permita realizar la acción del evento a ejecutar
Se agrega "methods" al componente padre y nombras a tu método.
En este caso este va a recibir un parametro el cual será el que se está enviando al momento de emitir el evento.
```Javascript
methods: {
	crecer(size) {
		this.textSize += size
	}

},
```
Para usarlo solo se debe escribir su nombre.
```HTML
<div id="app">
    <template v-for="course in courses" :key="course.id">
        <div :style="{ fontSize: textSize + 'em'}">
            <detail-course @crecer-texto="crecer" :curso="course"></detail-course>
        </div>
    </template>   
</div>
```