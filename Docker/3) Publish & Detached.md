Tanto publish como Detached son banderas. Estas se utilizan para agregar configuraciones adicionales a los comandos.

# Publish
Publish mapea el puerto del host con el del contenedor. Esta forma estable una conexión en donde se permite que haya una comunicación de datos bidireccional entre el host y el contenedor.

Veamos un ejemplo de su uso:
```Docker 
docker container run --publish 80:8080
```

Para usar la bandera se debe anteponer 2 guiones, seguido de su nombre y finalmente el puerto del host que se va a mapear con el contenedor. Recuerda, primero siempre es el puerto de host y luego el del contenedor.

Una forma abreviada de hacerlo es simplemente colocando ==-p==.

# Detached
Detached permite que el contenedor se ejecute en segundo plano. De esta forma, se puede seguir utilizando la consola sin que este enlazado al proceso del contenedor en ejecución.

Veamos un ejemplo de su uso:
```Docker
docker container --detached
```

Una forma abreviada de hacerlo es simplemente colocando ==-d==.

###### N -  Publish and Detach - short form
Una forma de utilizar estas 2 banderas es que puedes usarlas juntas. Esto es porque suelen utilizarse muchas veces y por ello decidieron hacerle una forma corta.

Veamos un ejemplo:
```Docker
docker container -dp 90:8080
```