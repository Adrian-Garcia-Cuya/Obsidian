El comando `rm` (remove) se utiliza para eliminar archivos y directorios. Cuando un archivo se elimina con el comando `rm`, generalmente siempre desaparece de manera permanente.

```
rm [OPCIONES] ARCHIVO
```

Sin ninguna opción, el comando `rm` normalmente se utiliza para eliminar archivos ordinarios:
```
sysadmin@localhost:~/Documents$ rm linux.txt
sysadmin@localhost:~/Documents$ ls linux.txt
ls: cannot access linux.txt: No such file or directory
```

El comando `rm` ignorará los directorios que se le pida eliminar. Para eliminar un directorio, utilice una opción recursiva, por ejemplo, las opciones `-r` o `-R`. Tenga cuidado ya que estas opciones son “recursivas” (se ejecuta en cada subdirectorio del directorio que se esta eliminando), y eliminarán todos los archivos y todos los subdirectorios:

```
sysadmin@localhost:~/Documents$ rm Work
rm: cannot remove 'Work': Is a directory
sysadmin@localhost:~/Documents$ rm -r Work
sysadmin@localhost:~/Documents$ ls Work                                         
ls: cannot access Work: No such file or directory
```

## Nota
Los permisos pueden afectar a los comandos de administración de archivos, como el comando `rm`.

Para eliminar un archivo dentro de un directorio, el usuario debe tener permiso de escritura y ejecución en ese directorio. Normalmente, los usuarios ordinarios solo tienen este tipo de permiso en su directorio principal y subdirectorios correspondientes.