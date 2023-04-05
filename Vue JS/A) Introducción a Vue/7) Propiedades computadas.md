Evita que haya gran cantidad de lógica de programación en las etiquedas.

La principal diferencia entre methods y computed es entonces:  
**Cuando necesitamos cambiar la data debemos usar `methods`, pero cuando necesitamos cambiar la presentación de los datos existentes usamos `computed`**
# Uso
Hay que agregar un elemento llamado ==computed==, todo lo que contenga serán llamadas propiedades computadas.

Veamos un ejemplo:

```HTML
<script>
	Vue.createApp({
		data() {
			return {
				color: "black",
				active: true
			}
        },
        computed: {
	        colorClassComputed() {
		        return this.active ? 'text-blue' : 'text-red'
	        }
        }
	}).mount('#app')
</script>
```
Se agrego un método llamado "colorClassComputed" y para invocarlo solo se debe agregar, este caso, el nombre a la clase.
```HTML
<p v-bind:class="colorClassComputed">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi accusamus autem blanditiis. Dicta quidem minima consectetur saepe modi eum corporis veniam, atque dolores dolore nisi qui voluptatem delectus ipsum ut.</p>
```
###### nota (Agregar mas de una clase)
Es posible agregar más de una clase como se muestra a continuación:
```HTML
<p v-bind:class="colorClassComputed" class="otra_clase">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi accusamus autem blanditi</p>
```
Vue se encargará de unir o fucionar estas dos clases.