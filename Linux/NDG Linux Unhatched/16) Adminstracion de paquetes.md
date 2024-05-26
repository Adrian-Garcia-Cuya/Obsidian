La administracion de paquetes es un sistema que permite instalar, actualizar, consultar y eliminar un software de un sistema de archivos.

Existen muchos software para la gestion de archivos pero los mas utilizados son *debian* y *red hat*.

#### Nota - permisos de gestion
Varios de los comandos para gestionar los paquetes necesitan privilegios administrativos como el usuario *root* para poder ejecutarse.

# Consutar paquetes
Cuando se quiera revisar los paquetes disponibles se puede ejecutar el comando `apt-get search` para buscar los paquetes.

```
apt-get search "package_name"
```

No es necesario que el nombre sea exacto, este comando traera los posibles resultados.

# Instalar un paquete
Este caso, se usara el comando **apt-get** (para distribuciones deribadas de *debian*).

Se debe ejecutar el siguiente comando:
```
sudo apt-get install "package_name"
```

#### Nota - observacion al instalar un paquete
Se recomienda antes de instalar un paquete ejecutar el comando `apt-get update`. Esto debido a que se debe actualizar el listado de paquetes disponibles que se encuentra localmente. De esta manera se obtienen las ultimas actualizaciones (mejoras, agregaciones, etc.) del servidor y asi poder descargar las versiones mas actuales.

# Actualizar un paquete
Para actualizar un solo paquete puede utilizarce el mismo comando `apt-get install`. Si el paquete no se encuentra lo instala, caso contrario lo actualiza.

Tambien, se puede actualizar todos los paquetes del sistema con el comando `apt-get upgrade`. Al igual que al instalar, se recomienda ejecutar el comado `apt-get update`.

```
sudo apt-get upgrade
```

# Eliminacion de paquetes
Existen 2 maneras de eliminar los paquetes. La primera `(apt-get purge)` elimina todos los archivos del paquete y la segunda forma `(apt-get remove)`, tambien borra los archivos del paquete exceptuando los archivos de configuracion.

Veamos unos ejemplos:

```
sudo apt-get remove 'package_name'
sudo apt-get purge 'package_name'
```

