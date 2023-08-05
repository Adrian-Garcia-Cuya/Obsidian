Es un archivo que se utiliza para ejecutar rápidamente todo un grupo de contenedores que ejecuta o permita desarrollar una nueva aplicación.



# Servicios
Los servicios son un parte o componentes de una aplicación. Dentro de estos servicios están las configuraciones necesarias para que ese componente cumpla su papel en el funcionamiento de la aplicación. Como por ejemplo, las imágenes que se van a instanciar al momento de levantar los contenedores de los servicios.

Veamos un ejemplo de un archivo docker compose:
![[docker_compose.png]]

Como se puede observar, dentro de "services" se encontraran todos los servicios que requerirá la aplicación. En este caso se tiene un servicio llamado *db*, el cual tiene un contenedor, su imagen, el bind volume y una variable de entorno de la imagen.

###### Note - depends
Si requieres que un servicio se ejecute antes que otro para el correcto funcionamiento de tu aplicación se puede utilizar el **depends_on**.

Veamos un ejemplo:

![[docker_compose_depends.png]]

Luego de crear el servicio "db", se creo el "pgAdmin", aquí se indica que pgAdmin depende de que el servicio "db" se cree o monte primero. No importa si en las instrucciones esta debajo del servicio de "pgAdmin", se creara primero "db".

# Crear y designar volumenes
Para crear un volumen en docker compose se debe colocar "volumes" al mismo nivel que de "services". Luego, dar una tabulación e ingresar el nombre del volumen que deseas crear. En este caso, la imagen superior se tiene que se esta usando el volumen nombrado "postgres-db", por tal motivo ese nombre se usará.

Veamos un ejemplo:

![[docker_compose-volumen.png]]

De esta forma, docker creara el volumen y utiliza cierta nomenclatura para nombrarlo.
Primero le da el nombre del proyecto, luego el nombre del volumen y ultimo el nombre de replica, si es que hay.

Veamos un ejemplo:

![[docker_compose-volumen-nomenclatura.png]]

En esta imagen se aprecia la nomenclatura en el ultimo volumen.
Nombre del proyecto -> **postgres-pgadmin**
Nombre del volumen -> **postgres-db**
(en este caso no hay replicas)

# Utilizar un volumen creado
Para usar un volumen x que ya se tiene creado solo hay que agregar la siguiente linea a continuación:

![[docker-volumen-asignar.png]]

**IMPORTANTE**: Una vez montado los contenedores con docker compose, si se modifica el archivo, es necesario dar de baja lo montado(borrar contenedores, redes, etc). 

El comando es el siguiente:
```Docker
docker compose down
```

# Bind Volume
Para crear un bind volume en docker compose se realizá de la siguiente forma:

![[docker-compose-bind-volume.png]]

Como se puede observar, se indica la ruta actual "./", seguido del nombre de la carpeta de debe crear y es la cual se vinculará con el filesystem del contenedor.

# Variables de entorno
Para evitar que otros puedan ver las credenciales privadas al enviarles el archivo compose es recomendable tener configurado las variables de entorno.

![[docker-compose-variables_entorno.png]]

Como se puede observar, en el archivo ".env" se definen las variables de entorno y en el compose se utilizan mediante el simbolo del dolar y el uso de llaves.

**IMPORTANTE**: Lo que hace **restar: always** es reiniciar o volver a ejecutar el servicio en caso de que se detenga de forma inesperada u ocurra un error en el servicio.

# Comandos
Para ejecutar los comando se agrega el elemento "command" y luego se envia el comando entre corchetes.

Veamos:
![[docker-compose_comando.png]]

En este caso se indica que se ejecute el comando "auth" cuando se monte la imagen, es decir, se cree un contenedor a partir de una imagen.
