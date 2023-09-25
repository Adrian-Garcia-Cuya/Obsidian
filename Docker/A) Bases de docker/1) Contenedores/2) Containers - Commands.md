Los comandos para realizar todo tipo de operaciones con el contenedor empiezan con **docker container**, luego sigue el comando para la tarea que se quiere realizar y finalmente el nombre o código del contenedor.

Veamos un ejemplo:
```Docker
docker container "comando" "nombre o id contenedor"
```
```Docker
docker container run testcontenedor
```

Veamos algunos de los comandos más utilizados:

1. Crear y ejecutar un nuevo contenedor:
```Docker
docker container run
```
2. Crear un nuevo contenedor:
```Docker
docker container create
```
3. Ejecutar un o más contenedores detenidos:
```Docker
docker container start
```
4. Detener uno más contenedores:
```Docker
docker container stop
```
5. Reiniciar uno o más contenedores:
```Docker
docker container restart
```
6. Eliminar todos los contenedores detenidos:
```Docker
docker container prune
```
7. Elimina uno o más contenedores:
```Docker
docker container rm
```
8. Actualizar las configuraciones de uno o más contenedores:
```Docker
docker container update
```
9. Renombrar un contenedor:
```Docker
docker container rename
```
10. Listar los contenedores en ejecución/levantados:
```Docker
docker container ls
```
Mostrar tanto los contenedores en ejecución y detenidos:
```Docker
docker container ls -a
```
11.  Visualizar las tareas que realiza un contenedor:
```Docker
docker container logs
```
12. Matar uno o más contenedores ejecutandose:
```Docker
docker container kill
```

###### N - difference between stop and kill
El uso de los comandos ==stop== y ==kill== puede ser similar. Su uso depende de la situación. Por lo general, se utiliza stop para detener adecuadamente un contenedor y que realice los procesos de limpieza o liberar recursos. Kill se suele usar en situaciones de emergencia en donde se requiera un detención rápida del contenedor sin que realice los procesos mencionados recientemente.