1)  Al momento de querer ejecutar un comando y utilizar el id del elemento al que quieres que se aplique ese comando puedes utilizar solo los 3 primeros números.

Ejemplo: Se tiene el contenedor con id -> ==2d7h867768d98==. Al ejecutar el comando para eliminar el contenedor se puede realizar de esta forma abreviada:

```Docker
docker container rm 2d7
```

2) En ocasiones puede que tengas problemas al querer probar si el servidor de base de datos esta correcto. En este caso, en dbear, en los "driver properties", el  driver llamado "allowPublicKeyRetrieval" esta por defecto en *false*. Esto es por una medida de seguridad ante posibles ataques maliciosos. Por ende, es necesario cambiarlo a *true* para poder probar la conexión.

![[Docker-tips-test-conexion.png]]