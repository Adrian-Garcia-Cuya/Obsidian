# Que son los getters?
Los getters son similares a las propiedades computadas. Estas se definen en la 'tienda'. De esta manera, cualquiera de los componentes podrá utilizar todos los getters definidos y de esta forma se evita que en cada componente se reescriba codigo en caso de que varios componentes requieran realizar algo en una propiedad computada (ademas, también, de obtener la información).

Veamos como definir un getter:

![[vuex-getters.png]]
Como se puede observar, se definió el metodo 'sizeApellido' y este retorna el conteo de caracteres que esta almacenado en el estado 'apellido'. Mencionar que estos métodos reciben como parámetro el objeto 'state'.

Ahora, para poder usarlo, en un principio es similar a como se vio en el uso de los estado.

Veamos:
```js
$store.getters.sizeApellido
```

Teniendo eso en mente, tendremos el mismo problema que habíamos mencionado. Por ellos realizaremos el mismo procedimiento que se sugirió para evitarlo.

![[vuex-gettersUse.png]]
En este caso, estaríamos importando la función 'mapGetters' (la cual hara lo mismo que la otra). Y luego  definimos los getters dentro del array.
