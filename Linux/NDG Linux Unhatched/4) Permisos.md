Los permisos permiten determinar como los usuarios podran interactuar con un archivo o directorio.

Los permisos se dividen en 3 grupos de 3 caracteres:

![[permisos-repaso.png]]
### Nota
Como se menciona, los permisos estan separados por grupos, es decir cada grupo tiene permisos especificos. Cuando un usuario pertenece a uno de los grupos tomara los permisos respectivos e ignorara los demas permisos. 
### Propietario
El primer grupo se refiere al propietario del archivo. Si su cuenta actual es propietario del archivo, se usara el primer grupo de permisos y los demas permisos no tendran efecto.

El nombre del propietario se encuentra en la posicion de 'sysadmin'.

![[permiso-propietario.png]]

### Grupo
Este segundo conjunto se refiere al **grupo** que posee el archivo. Si la cuenta actual no es propietaria del archivo pero pertenece al grupo que posee el archivo, se aplicaran los permisos del grupo y los demas permisos no tendran efecto.

El nombre del grupo se puede visualizar al lado del nombre del propietario.

![[permiso-grupo.png]]

### Otros
El último grupo es para todos los demás, cualquiera a quien los dos primeros conjuntos de permisos no sean aplicables. Si no es el usuario que posee el archivo o un miembro del grupo que posee el archivo, se le aplicará el tercer conjunto de permisos.

![[permisos-otros.png]]

# Tipos de permisos
Un archivo o directorio pueden tener 3 tipos de permisos: *leer, escribir y ejecutar*. La forma en como se aplican estos permisos difiere entre un archivo y directorio.

![[tipos_permisos.png]]

#### Nota
El permiso "x" en un directorio te permite acceder a este. Obviamente si no tienes este permiso no podras hacer nada en el directorio.

El permiso "w" en un directorio permite crear, renombrar y eliminar subdirectorios.

#### Importante
Es relevante tomar en cuenta que permisos se aplican cuando se trabaja con linux.

```
-r--rw-rwx. 1 sysadmin staff 999 Apr  10  2013 /home/sysadmin/test
```
En este ejemplo, el usuario 'sysadmin' termina teniendo menos acceso a este archivo que los demas. No importa si 'sysadmin' es miembro del grupo `staff`; una vez establecida la propiedad del usuario, solo se aplican los permisos del usuario propietario.