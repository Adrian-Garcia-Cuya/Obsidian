El comando **chmod** se utiliza para cambiar los permisos de un archivo o directorio. Tomar en cuenta que solo el propietario  o usuario raiz (root) puede cambiar los permisos de un archivo.

Existen 2 metodos para cambiar los permisos usando **chmod**: el metodo simbolico y el metodo octal. El metodo simbolico es util cuando se require cambiar un conjunto de permisos a la misma vez. El método octal o numérico requiere conocer el valor octal de cada uno de los permisos y requiere que los tres conjuntos de permisos (usuario, grupo, otros) se especifiquen cada vez. 

# Metodo simbolico
```
chmod [<COJUNTO DE PERMISOS><ACCIÓN><PERMISOS>]... ARCHIVO
```
Para usar el método simbólico de `chmod` primero debe indicar qué conjunto de permisos (grupo de permiso) se está cambiando:

![[chmod-conjunto-permisos.png]]
![[simbolos-conjunto-permisos.png]]

A continuación, especifique un símbolo para la acción:

![[chmod-accion.png]]

![[chmond-simbolos-acciones.png]]

Después del símbolo de acción, especifique uno o más permisos.

![[chmod-simbolos-permisos.png]]

Finalmente, añada un espacio y los nombres de ruta para los archivos a los que quiere asignar los permisos.

Por ejemplo, se quiere ejecutar el script del archivo pero solo cuenta con los permisos siguientes:
```
sysadmin@localhost:~/Documents$ ls -l hello.sh                                  
-rw-r--r-- 1 sysadmin sysadmin 647 Dec 20  2017 hello.sh
```
Este archivo tiene como propietario a 'sysadmin' el cual es la cuenta actual. Entonces al ser el usuario el propietario puede agregar el simbolo **u**. Luego, se especifica la accion que se quiere realizar, en este caso ejectuar el archivo, por ende, se le dara el permiso con el simbolo **x**. Finalmente, solo queda especificar el archivo al que se le modificaran los permisos.

```
sysadmin@localhost:~/Documents chmod u+x hello.sh
```
Una ves hecho esto se puede ver que el archivo cambio de color, demostrando que ha sido modificado sus permisos.

Para hacer la modificacion de permisos en conjunto es realizar el mismo proceso pero tanto el simbolo del grupo de permiso como el de la accion debe estar separado por comas.

```
chmod u=rw,g=r,o=r archivo.txt
```
### Nota
¿Por qué el comando se llama `chmod` en lugar de `chperm`? Los permisos solían denominarse modos de acceso, por lo que el comando `chmod` realmente significa cambiar los modos de acceso (**ch**ange access **mod**e).

