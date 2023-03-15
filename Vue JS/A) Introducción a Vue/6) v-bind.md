Permite modificar los atributos de las etiquetas dinámicamente.

# Uso
Colocas ==v-bind==, dos puntos ":" y luego el nombre del atributo, en este caso será una clase. 

Dentro de la clase se colocará sintaxis básica de js. Lo que se quiere lograr es que se cambie el nombre de la clase dinámicamente.

Veamos un ejemplo:

Primero, agregamos las propiedades que usaremos.
```HTML
<script>
	Vue.createApp({
		data() {
			return {
				color: "black",
				active: true
			}
        }
	}).mount('#app')
</script>
```
Luego, colocamos la directiva v-bind en las etiquetas que modificaremos.
```HTML
<div id="app">
    <button @click="color = 'red'">
        Rojo
    </button>
    <button @click="color = 'green'">
        Verde
    </button>
    <button @click="color = 'blue'">
         Azul
    </button>

	//se modificará la clase de esta etiqueta
    <p v-bind:class="`text-${color}`" >Lorem ipsum dolor sit amet consectetur adipisicing elit. Excepturi, deserunt nemo </p>

    <button @click="active = !active"> //se auto asigna la negación del valor de la variable cada vez que se hace clic.
    
        <span v-if="active">Desactivar</span>
        <span v-else>Activar</span>
    </button>
	
	//se modificará la clase de esta etiqueta
	<p v-bind:class="active ? 'text-blue' : 'text-red'">Lorem ipsum dolor sit amet con</p>
</div>
```

## Formas de user v-bind
La primera es como acabas de ver:
```HTML
//la sintaxis de js es la que está dentro del atributo class
//se esta usando un operador ternario.
<p v-bind:class="active ? 'text-blue' : 'text-red'">Lorem ipsum dolor sit amet con</p>
```
La segunda forma solo es mas resumido:
```HTML
//solo se coloca ":"
<p :class="active ? 'text-blue' : 'text-red'">Lorem ipsum dolor sit amet con</p>
```