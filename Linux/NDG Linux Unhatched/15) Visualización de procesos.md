Al ejecutar un comando, da como resultar algo llamado *proceso*. En el sistema operativo linux,
los procesos se ejecutan en funcion de los privilegios/accesos, lo que permite limitarlos dependiendo del usuario.

El comando para ver los procesos es `ps`:
```
ps [OPCIONES]
```

![[Pasted image 20240520161058.png]]

De manera predeterminada, el comando `ps` muestra los procesos que se ejecutan en ese momento en la terminal actual.

La salida incluye las siguientes columnas de información:
- **PID** : representa al identificador de procesos.
- **TTY** : indica el nombre de la terminal donde se ejecuta un proceso. Es de utilidad para distinguir procesos con el mismo nombre.
- **TIME** : muestra el tiempo de ejecucion de un proceso.
- **CMD** : muestra el comando que inicio el proceso.

Ademas de poder ver los procesos que se ejecutan en la terminal actual, se puede visualizar todos los procesos que se estan ejecutando en el sistema con la opcion `-e`.

![[Pasted image 20240520161905.png]]

Tambien se puede utilizar la opcion `-f` para brindar informacion detallada que incluya las opciones y los argumentos de cada proceso.

![[Pasted image 20240520162041.png]]