En la mayoría de los casos se comienza a crear una imagen basados en otra imagen.

Instrucciones:

***Herencia:*** Este paso basa nuestra imagen a crear, a
partir de otra en particular.

```Docker
FROM node:19.2-alpine3.16 //punto de partida
```

***Working directory:*** Establece que partir de este punto, estamos en el directorio especificado, es como cambiarse de directorio vía comando.

En esta versión "alpine" que se instala, viene con una carpeta llamada "app". Lo que se va a realizar a continuación es movernos o cambiar de directorio a la carpeta "app".

Al realizar esto, todas las rutas o directorios se ejecutaran dentro de la carpeta "app". 
```Docker
WORKDIR /app 
```

***Copia todos los archivos y directorios:*** de mi proyecto (source) hacia el working directory del contenedor (dest, en este caso seria "app" como se especifico en el WORKDIR), excluyendo lo especificado en el archivo .dockerignore

```Docker
COPY "source" "dest"
```
```Docker
COPY "app.js package.json" "./"
```

***Inicialización:*** Se indica que se deben de descargar e instalar los módulos de node.
Se utiliza para ejecutar comandos.
```Docker
RUN npm install
```

***Comando:*** especifica la instrucción que se __ejecutará cuando se inicie un contenedor__ de Docker.
```Docker
CMD ["node", "app.js"]
```

## Construir una imagen
Construir y asignar un tag a la imagen: El objetivo del tag es que sea fácil de identificar y leer por humanos.

```Docker
docker build --tag cron-ticker .
```

***-t /--tag) :*** Este primer tag asigna el name de la imagen
***. :*** El punto indica a dónde buscar el archivo DockerFile en el directorio actual.

###### Nota - image name
Si no se ingresa ningún tag, por defecto, se ingresa el tag "latest".

##### IMPORTANTE
Si se realizan cambios en el dockerfile o en el codigo fuente, docker lo revisara al construir o reconstruir la imagen. 
Se recomienda mantener un orden en los layers/capas debido a que si se hace un cambio, los posteriores layers se volveran a ejecutar/crear. Esto ayudara a que los layers se mantenga en cache y la construcción de una imagen sea mas rápida.

## Renombrar una imagen
Esto permitira crear imagenes que apunten al mismo ID.
```Docker
docker image tag SOURCE[:TAG] TARGET_IMAGE[:TAG]
```

```Docker
docker image tag isaias0328/cron-ticker:pantera isaias0328/cron-ticker
```
## Subir la imagen creada a DockerHub
Al momento de querer subir la imagen a docker te pedira que inicies sesion. Para ello, debes hacerlo mediante el siguiente comando:
```Docker
docker login
```

Luego de  eso, pedirá las credenciales.

Para cerrar sesión solo se debe realizar el siguiente comando:

```Docker
docker logout
```


Para subir la imagen creada solo se debe realizar el siguiente comando:
```Docker
docker push "nombreUsuario"/"nombreImagen":"version"
```

Por ejemplo:
```Docker
docker push isaias0328/cron-ticker:castor
```