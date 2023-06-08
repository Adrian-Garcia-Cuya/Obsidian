# ¿Qué es una imagen?
Una imagen es un archivo construido por capas. El cual, tiene todas las dependencias necesarias para ejecutar la aplicación.

El contenedor utiliza el filesystem personalizado que contiene la imagen para ejecutar la aplicación, entre otras tareas. Es por ello, que este filesystem debe tener todas las dependencias, scripts, configuraciones, etc, necesarias. Además, las imagenes tienes otras configuraciones para las variables de entorno.