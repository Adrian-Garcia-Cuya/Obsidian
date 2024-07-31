## Comando *su*
```
su OPCIONES NOMBRE-DE-USUARIO
```
El comando *su* permite actuar temporalmente como un usuario diferente. Lo hace creando un nuevo shell. De forma predeterminada, si no se especifica una cuenta de usuario, el comando *su* abrira el nuevo shell como usuario *root*, proporcionando privilegios administrativos.

- **shell :** es un programa que maneja la interpretación y ejecucíon de comandos, asi tambien, la ejecucion de programas y otros servicios. 
  Cuando se cambia de usuario, el sistema cargara el shell del nuevo usuario. Esto permite tener un entorno de trabajo separado y configurado para cada usuario.

### Nota 
La opción `-`, `-l`, o `--login` se utiliza para iniciar una nueva sesión de shell como el usuario especificado, y se recomienda usar esta opción para garantizar que el nuevo shell tenga todas las configuraciones adecuadas del nuevo usuario.

Estas 3 formas son validas y representan lo mismo:
```
su -
su -l
su --login
```
Después de ejecutar el comando **su**, se requiere una contraseña, la cual, no se muestra por seguridad.
```
sysadmin@localhost:~$ su  -
Password:
root@localhost:~#
```
Para cerrar la sesión y volver a la cuenta `sysadmin`, use el comando `exit`
```
root@localhost:~# exit
logout
sysadmin@localhost:~$
```
punto 6 -> falta el comando sudo

## Comando *sudo*                                                                                          

El comando sudo permite ejecutar comando como si fueras otro usuario sin la necesidad de cargar un nuevo shell. Para ejecutar un comando con privilegios administrativos se debe utilizar el comando como argumento para el comando **sudo**. Al igual que el comando *su*, el comando **sudo** asume  por defecto que la cuenta de usuario 'root' debe usarse para ejectuar comandos.

### Nota
El comando **sudo** también puede usarse para cambiar a otras cuentas de usuario. Para especificar una cuenta de usuario diferente, utilice la opción **-u**.

Ejecute el comando `sl` como usuario `root` poniendo `sudo` delante de él:
```
sysadmin@localhost:~$ sudo sl
[sudo] password for sysadmin:
```
La solicitud de contraseña no aparecerá de nuevo mientras el usuario continúe ejecutando comandos `sudo` a intervalos inferiores a cinco minutos.

