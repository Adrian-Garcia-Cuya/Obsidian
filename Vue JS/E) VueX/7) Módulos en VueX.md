Modularizar nuestra tienda nos va a permitir tener nuestro código separado y de esta manera, esto permitirá que nuestro código sea mas legible.

Para realizar esto podemos separar nuestros conceptos de la siguiente manera:

![[vuex-modules.png]]

Como se puede observar, en el archivo 'index.js' estamos creando dos constantes una es 'moduleUser' y el otro 'moduleCounter'. Cada uno tendrá sus propios estados, mutations, etc.

Para hacer uso de cada modulo se debe agregar un objeto y darle una propiedad al modulo que creaste en 'createStore'.

Ahora, acceder a los estados desde un componente es de la siguiente manera:
```js
$store.state.user.nombre
```
Es igual a como hemos visto anteriormente y de la misma forma tenemos una manera de evitar estar colocando todo esto.

![[vuex-modulesUsed.png]]
Lo unico que se debe realizar es, ahora, dar un objeto a la funciona 'mapState', darle las propiedades correspondientes (las cuales luego usaremos para mostrar los datos), y cada propiedad recibirá una función flecha. Esta como parámetro debe recibir el 'state' y retornar el valor del modulo que uno quiera obtener, en este caso 'user'.

# Alcances de módulos
De forma predeterminada, uno puede acceder a todas las funciones de los módulos sin ningún problema, ya que, a pesar de estar en diferentes módulos, estos tienen un alcance global.

Si se desea que estos tengan un alcance local es necesario agregar una propiedad:
```js
namespaced: true,
```
En la primera imagen se puede observar esto.

De esta manera, los componentes ya no podrán usar las funciones como lo estaban haciendo antes. Lo que hay que hacer ahora es especificar de que modulo se esta queriendo llamar a la función.

![[vuex-modulesNamespaced.png]]

En cada función, antes de enviar las funciones que usaremos, debemos indicar a que modulo le pertenece.

# Usando un helper

La función `createNamespacedHelpers` acepta un nombre de espacio como argumento (el modulo) y devuelve un conjunto de funciones (helpers) que están vinculadas a ese espacio de nombres en particular. Estas funciones facilitan la conexión de tus componentes Vue al estado, getters, mutaciones y acciones de ese espacio de nombres específico.

![[vuex-helper.png]]

Para usarlo, se debe importar. Luego, se destructura debido a que este ayudante retorna un objeto con todas la funciones que nos van a permitir acceder a nuestras funciones de cada modulo.

De esta manera ya no especificamos el modulo en cada función como se mostró anteriormente.

# Separando módulos
Podemos tener nuestros módulos en diferentes archivos para tener un código mas legible.

Creamos una carpeta 'modules' en nuestra 'tienda' y dentro de esta estarán los archivos js de cada modulo.

![[vuex-separetedModules.png]]
Luego, solo es exportar la constante como se ve al final de la imagen.

Finalmente, en nuestro archivo 'index.js' importamos nuestros módulos.
![[vuex-importModules.png]]

