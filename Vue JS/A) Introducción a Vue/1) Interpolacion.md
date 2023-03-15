Es una forma de insertar valores en una plantilla.
# Area de trabajo
Para definir un área de trabajo se debe crear un "div" y darle la propiedad id con el nombre ==app==.

# Especificar el área de trabajo 
Para usar el área de trabajo se debe montar (especificar con que div debe interactuar).
```HTML
<script>
	//se crea la aplicacion
	Vue.createApp( //definimos nuestras propiedades y metodos
		data() {
			return{ //retornamos un objeto
				message: "hola mundo",
			}
		}
	).mount('#app');//En el método "mount" se da como argumento el nombre del espacio de trabajo.
</script>
```

Ahora, para mostrar esa propiedad se debe ir al espacio de trabajo y usar dos llaves de apertura y cierre.
```HTML
<div id="app">
	{{ message }} //esto es la interpolación
</div>
```