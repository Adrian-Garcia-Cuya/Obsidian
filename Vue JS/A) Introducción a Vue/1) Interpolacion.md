Es una forma de insertar expresiones js en una plantilla.

la expresion de js es cualquier operación con js que puedas hacer en una sola línea. Ejm: operación matemática o mostrar un valor.
# Area de trabajo
Se define en que elemento html va a construir el componente (componente padre) de la aplicación.

Para definir un área de trabajo se debe crear un "div" y darle la propiedad id con el nombre ==app==.

# Especificar el área de trabajo 
Para usar el área de trabajo se debe montar (especificar con que div debe interactuar).
```HTML
<script>
	//se crea la aplicacion
	Vue.createApp( //definimos nuestras propiedades y metodos
		data() {
			return{ //retornamos un objeto json
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

"creaApp" retorna un objeto que ya tiene nuestra aplicación.