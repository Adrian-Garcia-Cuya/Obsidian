# ¿Qué es un contenedor?
Un contenedor es un entorno/espacio aislado en la maquina que está aislado de todos los demás procesos del host.

**Características:**
- Es una instancia ejecutable de una imagen. Se puede crear, iniciar, detener, mover o eliminar contenedores usando el CLI.
- Se puede ejecutar en máquinas virtuales, locales o implementarse en la nube.
- Es portátil (se puede ejecutar en cualquier sistema operativo).
- Está aislado de otros contenedores y ejecuta su propio software, binarios y configuraciones.
###### Nota
El contenedor es una instancia de una imagen porque se crear a partir de una imagen base. ***Cuando se crea un contenedor se toma esa imagen como punto de partida y se crea una instancia en ejecución de esa imagen***.

Cada contenedor creado a partir de una imagen es una instancia independiente, con su propio entorno aislado y recursos específicos.