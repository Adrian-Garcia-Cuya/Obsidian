El comando **chown** permite cambiar el propietario del los archivos y directorios. Realizar esto requiere acceso administrativo. Un usuario ordinario no puede realizar este comando; incluso si es el propietario del archivo tampoco podria.

Ademas, el comando **chown** permite cambiar el grupo propietario, es decir, que el archivo le pertenezca a otro grupo, lo cual puede ser realizado por el usuario root o el propietario del archivo.

Para cambiar el usuario propietario de un archivo, se puede utilizar la siguiente sintaxis. El argumento, `[PROPIETARIO]`, especifica qué usuario debe ser el nuevo propietario. El argumento, `ARCHIVO`, especifica el archivo al cual se está cambiando el propietario.

```
chown [OPCIONES] [PROPIETARIO] ARCHIVO
```

Recordar que para realizar esta accion se debe tener los privilegios administrativos.
```
sysadmin@localhost:~/Documents$ sudo chown root hello.sh
```