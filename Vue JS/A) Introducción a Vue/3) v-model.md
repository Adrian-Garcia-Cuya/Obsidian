# Sincronizar un campo con una propiedad
El directiva ==v-model== permite actualizar, en tiempo real, lo que se escribe en un campo. Es decir, si se escribe "juan" la propiedad tendra ese valor, si luego se borrar ese valor, también se borrará en la propiedad.
```HTML
<div id="app">
	<form action="" v-on:submit.prevent="addPais"> //se asigna el método creado
		<input type="text" v-model="name" > //Aquí se indica el nombre de la propiedad con la que estará enlazada.
		<button>Agregar</button>
    </form>
	{{paises}}
 </div>
```
Luego, se crea el método que agregará los países:
```HTML
<script>
	Vue.createApp({
		data() {
			return {
				name: "",
				paises: ['Peru', 'Bolivia']
			}
		},
		methods: {
			addPais() {
			this.paises.push(this.name); //se agrega el valor introducio en el campo al array "paises"
			this.name = "" //se limpia el campo
		}
	}).mount('#app')
</script>
```

###### nota (método prevent)
En el formulario se está dando el evento submit y se le está pasando el método ==prevent==, el cual evitará que se refresque la página






