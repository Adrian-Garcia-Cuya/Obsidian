# ¿Qué es una imagen?
Una imagen es un archivo construido por capas. El cual, tiene todas las dependencias necesarias para ejecutar la aplicación.

El [[1) Contenedores - Containers#¿Qué es un contenedor?|contenedor]] utiliza el filesystem personalizado que contiene la imagen para ejecutar la aplicación, entre otras tareas. Es por ello, que este filesystem debe tener todas las dependencias, scripts, configuraciones, etc, necesarias. Además, las imagenes tienes otras configuraciones para las variables de entorno.

# Commands
Los comandos de las imágenes son similares al de los contenedores debido a que se sigue la misma estructura. No todos los comandos mencionados en el contenedor funcionan para las imagenes.

Veamos su estructura:
```Docker
docker image "comando"
```

###### N - images commads equals containers commads
Tanto para listar (ls) y eliminar (rm) son los mismos comandos. Recuerda también que debes pasar el nombre de la imagen o el "id".