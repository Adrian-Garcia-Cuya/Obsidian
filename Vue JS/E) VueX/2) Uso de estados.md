Para guardar información o datos en la tienda se hace en el objeto **state**.

Veamos como es la estructura de la tienda:

![[vuex-states.png]]

Supongamos que se agregaran dos valores en state: 'nombre' y 'apellido'. Para acceder a ellos se debe realizar algo similar a como se accedian a los valores que se enviaban por los parametros.

Nos vamos al componente donde queremos mostrar los datos y agregamos lo siguiente:

```HTML
<template>
	<p>{{ $store.state.nombre }}</p>
	<p>{{ $store.state.apellido }}</p>
</template>
```

Como se puede observar, primero se indica que tomaremos la informacion de la 'tienda', luego accedemos a los 'states' y seguido el valor del cual queremos recuperar la información.

# Acceder a los datos desde la propiedades computadas
Una forma mas prolija de acceder a la informacion es desde las propiedades computadas. De la misma forma como se ha visto anteriormente. De esta forma, evitamos ingresar esas tres palabras para obtener los datos.

![[vuex-statesInComputedProperties.png]]
Como se puede ver, ahora solo seria necesario ingresar el nombre de la propiedad computada.

# Mapear a todos los datos del estado.
Consiste en acceder a todos los datos de la tienda desde el componente.

Para mapear el state, es necesario usar la funcion 'mapState', para ellos es necesario importarlo de la libreria 'vuex'.

```js
import {mapState} from 'vuex'
```

Lo siguiente es poder definir las propiedades computadas utilizando esta función, ya que, si bien es cierto se puede acceder a los datos de forma mas prolija como se vio antes, si hay una gran cantidad de datos que son requeridos se tendrían que crear demasiadas propiedades computadas.

Entonces, para evitar eso, lo definiremos de la siguiente forma:

![[vuex-mapState.png]]

De esta manera, al enviarle los datos que requerimos por medio de un array, la funcion se encarga de crear las propiedades computadas por nosotros por cada dato.

Ahora, aqui hay algo importante, si se requiere definir mas propiedades computas, no sera posible por la forma en como se ha realizado anteriormente en la imagen, debido a que es función crea un objeto y luego las propiedades computadas dentro.

Para evitar ello se puede crear el objeto y luego dentro de este, agregar 3 puntos antes de la funcion "mapState".

![[vuex-mapStateUse.png]]