Las acciones son similares a la mutaciones pero la principal diferencia es que con las acciones podremos realizar ==operaciones asíncronas==.

Para definir una acción, se realizar dentro de 'actions'. Cada función recibirá como primer parámetro el *context*, que vendría hacer el las demás propiedades de la tienda (o puede decir también 'el contexto de la tienda').

Veamos:
![[vuex-actions.png]]

Como se puede observar, se define la función 'changeNombre', recibe como parámetro el contexto de la tienda y luego se usa el 'setTimeout' para simular un proceso asíncrono.

Al igual como se llama a las mutaciones desde un componente, como se vio anteriormente, aquí se usa la misma función llamada 'commit'.

En el componente:
![[vuex-actionsUse.png]]
Esta es la forma extensa en como podríamos llamar a un 'actions', usando el 'dispatch'.

Veamos una forma más corta:
![[vuex-actionsShortUse.png]]
Como se vio anteriormente, una forma de no llamar constantemente desde 'store' es creando los propios métodos para cada 'acción' pero como ya se mencionó, estar creando un método para cada uno sería poco práctico y lo mejor sería mapearlo y que estos métodos se creen solos.

Veamos:
![[vuex-actionsShortUse2.png]]

Para mapear todas los 'actions', importaremos 'mapActions'. Luego, simplemente usaremos la función como se ve en la imagen y posteriormente usaremos las acciones que hemos mapeado.

# Usando Promesas
Para realizar un proceso mas similar a uno asíncrono, se usarán promesas:
![[vuex-actionsPromise.png]]

![[vuex-actionsPromise2.png]]

Como se puede observar, se crea una promesa y luego en el componente estaría obteniéndose una promesa como retorno, por ellos usamos 'then', que se ejecutará una vez resuelta la promesa.

En caso de que se quiera realizar una operación pero se requiera que se espere el resulta podemos usar funciones asíncronas.

Veamos:
![[vuex-actionsAsyncFunctions.png]]
Se creó una función asíncrona llamada 'confirmationChangeNombre', la cual recibirá 'dispatch' (para llamar/usar acciones definidas) y el nombre.
Lo re va a realizar es que cuando se llame a esa función, es llamar a 'changeNombre' pero esta acción no va a continuar hasta que 'changeNombre' retorne su valor, posterior a eso imprime un mensaje en la consola.

Aclarar que lo único que lo único que esperara para ejecutarse es todo lo que esté adentro de la función asíncrona (como el console.log). Fuera de eso la aplicación sigue ejecutándose.

![[vuex-actionsAsyncFunctions2.png]]
Ahora, llamaríamos a 'confirmationChangeNombre' desde el componente.
Aquí se puede ver lo que mencioné hace un momento. 'My component' se estaría ejecutando antes que el console.log dentro de la función mencionada.
###### Nota
Para llamar a las propiedades de la tienda con 'context' es de la siguiente forma:
```js
context.commit() //llama a los mutations
context.getters()
context.state
```

Tomando esto en cuenta, en las acciones que definamos, en vez de pasar el 'context', lo que haremiamos es destructurar ese objeto, vuex reconoce que context es el primer parámetro que reciben las acciones por lo que no es necesario especificar que queremos destructurar ese objeto, y quedaría de la siguiente manera:

![[vuex-actionsDestruction.png]]
En este caso, solo se está utilizando el 'commit'.