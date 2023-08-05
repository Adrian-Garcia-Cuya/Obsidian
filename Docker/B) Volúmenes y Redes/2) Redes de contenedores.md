Es un entorno virtualizado que da la capacidad a los contenedores para conectarse y comunicarse entre sí.

Al momento de crear una red en Docker se le asigna direcciones IP a cada contenedor que este dentro de esa red. Al mismo tiempo, se asigna un servidor DNS que mapea los nombres de los contenedores con sus respectivas direcciones IP. 

Esto facilita mucho las cosas debido a que ahora puedes referirte a un contenedor utilizando su propio nombre en lugar de su dirección IP.

Mostrar las redes:
```Docker
docker network ls
```

Inspeccionar redes:
```Docker
docker network inspect "nombre/codigo contenedor"
```

Conectar un contenedor a una red:
```Docker
docker network connect "nombre red" "nombre/codigo contenedor"
```

Agregar un red desde la inicialización de un contenedor:
Conectar un contenedor a una red:
```Docker
.
.
.
--network world-app
```

###### Note - networks and ports
La red facilita la transferencia de datos entre los dispositivos, mientras que los puertos facilitan la comunicación entre las aplicaciones o servicios dentro de cada dispositivo.

Para enviar datos a un puerto específico en un dispositivo, es necesario que el dispositivo esté presente en la red y tenga una dirección IP asignada dentro de esa red. Esto permite que los datos sean correctamente direccionados y entregados al dispositivo de destino.

Puedes ver la red como un edificio que conecta diferentes habitaciones (dispositivos) y los puertos como puertas dentro de esas habitaciones que permiten la comunicación entre las aplicaciones o servicios específicos.