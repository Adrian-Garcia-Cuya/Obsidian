```Git
git checkout -- . // obtiene la informacion antes de la modificacion siempre y cuando no este en el stage.
```

```Git
git config --global alias.'nombre del alias' 'comando'
Ejem:
git config --global alias.s "status --short"
```

```Git
git config --global -e // permite editar tus credenciales y alias
```

```Git
git commit --amend -m "Nuevo mensaje" //permite modificar el mensaje del ultimo commit
```

```Git
git mv 'nombre actual de archivo' 'nombre nuevo' //indica a git que estamos renombrando el archivo
```

```Git
git rm 'nombre del archivo' //indica a git que eliminamos el archivo
```

```Git
git rm -r 'nombre del directorio' //indica a git que eliminamos el directorio/carpeta
```

# tag
Normalmente se utiliza para manejar versiones de nuestra aplicación.

```Git
git tag //lista los tag creados
```

```Git
git tag 'nombre de tag' //permite agregar un mensaje al commit actual
```

```Git
git tag -a v1.0.0 -m "Version 1.0.0 lista" //'-a' permite agregar una etiqueta anotada al ultimo commit
```

```Git
git tag -a 'numero de version' 'numero de hash' //agregar el tag en el commit con el hash especificado
git tag -a v0.1.0 7587385
```

```Git
git tag 'nombre de tag' -m "mensaje del tag" //permite agregar un mensaje al tag
```

```Git
git tag -d "nombre del tag" //elimina un tag
```

```Git
git show 'nombre del tag' //muestra informacion adicional
git show v0.1.0
```

##### Importante (manejo de versiones)
Conozcamos el significado de cada '.' de la versión:
Ejemplo: **v1.0.0**
- **v1** -> se realiza el cambio de numero cada que haya un cambio importante en la aplicación (parche de errores que rompían la aplicación).
- **.0** -> se realiza el cambio cuando se realizan cambios pequeños como: la agregación de una librería, funcionalidad, etc.
- **.0** -> se realiza el cambio cuando se solucionaron errores.

###### Nota
- Usa `-a` para crear etiquetas anotadas con información adicional, apropiadas para versiones importantes.
- No uses `-a` para crear etiquetas ligeras si solo necesitas un marcador simple para un commit específico.

# reset

```Git
git reset 'nombre del archivo' // permite quitar un archivo del stage
```

- soft -> permite revertir un commit manteniendo los cambios actuales y los archivos en el stage
- mixed -> permite revertir un commit manteniendo los cambios actuales y los archivos estan fuera del stage
- hard -> permite revertir un commit borrando los cambios actuales.
```Git
git reset --soft HEAD^ //Revierte un commit
//HEAD a punta al ultimo commit
//Se puede reemplazar el HEAD por el hash de un commit
// ^ : indica tomar el commit anterior al especificado (HEAD en este caso)
// Se puede especificar la cantidad de commits anteriores que quieres tomar luego del '^'. Por ejemplo, puede ser 'HEAD^3' o 'HEAD^5' commits atras
```

```Git
git reset --reflog //permite ver el historial de comandos git utilizados
//cada accion realizada tiene un hash y podemos revertir las acciones realizadas usando 'reset --hard'
```

###### Nota
Todos los comandos 'soft', 'mixed' y 'hard' se les puede indicar el commit (HEAD^)

# stash
```Git
git stash //crea un stash de las modificaciones realizadas luego del commit.
```

```Git
git stash list //muestra el listado de stash creados
```

```Git
git stash list --stat //muestra informacion adicional del contanido de los stash
```

```Git
git stash pop //toma el ultimo stash y recupera los cambios almacenados en el stash. Ademas, elimina el stash y se reorganiza el posicionamiento de los demas stash (en caso se tenga).
```

```Git
git stash clear //elimina todos los stash
```

```Git
git stash apply 'nombre stash' //toma un stash en especifico y recupera las modificaciones del stash.
git stash apply stash@{2}
```

```Git
git stash drop 'nombre stash' //elimina el stash seleccionado
git stash drop stash@{2}
```

```Git
git stash show 'nombre stash' //muestra el contenido del stash
git stash show stash@{2}
```

```Git
git stash save 'Mensaje de referencia al contenido del stash' //guarda el stash con un mensaje
git stash save "Agregamos un villano"
```
###### Nota
- Se recomienda trabajar únicamente con un stash. Estos es porque al tener demasiados es probable olvidar lo que tiene almacenado cada stash.
- Los stash también generan conflictos. Se debe realizar lo mismo que se hace en la ramas.
# Rebase
El git rebase permite ordenar, unir, separar y corregir mensajes de los commits.

```Git
git rebase main //reposiciona el punto de separacion de la rama.
//contexto -> suponiendo que se tiene una rama y tienes 2 commit en ella. Ahora, en la rama main se realizaron 2 commits luego de separar la rama y ahora es necesario agregar esos commits del main a la rama.
Lo que hara este comando es mover el punto de separacion de la rama luego de los ultimos commits realizados en el main y a su vez obtener esos commits en la rama.
```

rebase interactivo:
```Git
git rebase -i HEAD~4 // abre una ventana interactiva el cual permite realizar diversas acciones.
```

![[rebase_interactivo.png]]

Nos aparecera los commits seleccionados y nos mostrara los comandos que se pueden utilizar.
- s / squash -> toma el commit y lo une con el commit anterior.
- r / reword -> toma el commit y edita el mensaje del commit.
- e/ edit -> toma el commit pero se realiza una pausa para realizar modificaciones.

Para usar los comandos se debe reemplazar la palabra **pick** por uno de los que se quieran usar.

Tanto en **squash y reword** aparece otra ventana interactiva donde una mostrar que mensaje del commit tomar o escribir uno nuevo y la otra permitira modificar el mensaje del commit.

Al usar el **edit** te retorna el a tu terminal pero puede realizar las correcciones correspondiendes, por ejemplo, separar las modificaciones en commits distintos. Una vez finalizado se debe ejecutar el comando:

```Git
git rebase --continue
```