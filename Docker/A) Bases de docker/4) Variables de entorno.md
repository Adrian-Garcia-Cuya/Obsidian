Las variables de entorno son valores dinámicos que se usan para configurar y controlar el entorno de ejecución, en este caso de los contenedores.

Las variables son útiles al cuando se quiere enviar cierta configuración al momento de levantar un contenedor.

Veamos un ejemplo:
```Docker
-e MYSQL_ROOT_PASSWORD=secret 
```

Aquí se está dando un valor a la variable de entorno que tiene la imagen. Esto es para configurar la contraseña de la base de datos "mysql".
