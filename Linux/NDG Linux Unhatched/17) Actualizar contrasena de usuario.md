El comando `passwd` permite cambiar la contrasena de un usuario. Cada usuario puede cambiar su propia contrasena. El usuario *root* puede cambiar cualquier contrasena.

```
passwd [OPCIONES] [USUARIO]
```

Veamos un ejemplo cambiando la contrasena del usuario "sysadmin":

![[Pasted image 20240523153905.png]]

Ademas, tambien se puede ver informacion adicional de la contrasena con la opcion `-S`:

![[Pasted image 20240523153957.png]]

El significado de cada columna es el siguiente:

![[Pasted image 20240523154020.png]]

# Cambiar la contrasena desde el usuario "root"
Para cambiar la contrasena de un usuario desde el administrador, solo debe enviarse como argumento el nombre del usuario:

![[Pasted image 20240523154157.png]]
