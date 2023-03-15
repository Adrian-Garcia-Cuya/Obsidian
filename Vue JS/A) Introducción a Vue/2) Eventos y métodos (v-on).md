# Escuchar eventos
Para escuchar un evento se usa la directiva ==v-on:== mas el nombre del evento. Luego darle la acción que se debe realizar al hacer clic. En este caso se les dio 2 metodos.
```HTML
<div id="app">
	<button v-on:click="decrement()">
		-
	</button>
	{{ counter }}
	<button v-on:click="increment()">
		+
	</button>
</div>
```
## Otra forma de user v-on
Simplemente se reemplaza por un @.
```HTML
<div id="app">
	<button @click="decrement()">
		-
	</button>
	{{ counter }}
	<button @click="increment()">
		+
	</button>
</div>
```
# Crear métodos
Para definir métodos en Vue se agrega, luego de "data", ==methods==.
```HTML
<script>
	Vue.createApp({
		data() {
			return {
				counter: 0
			}
		},
		methods: {
			decrement() {
				this.counter--;//para hacer referencia a una de las propiedades se debe agregar la palabra "this".
			},
			increment() {
				this.counter++;
			}
		}
	}).mount('#app')
</script>
```
