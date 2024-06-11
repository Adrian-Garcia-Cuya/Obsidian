## Que es?
Es un sistema operativo el cual se ejecuta en sistemas informaticos o hardware.
## Que es el CLI de linux? 
Es la *Interface de linea de comandos*, la cual, esta basada en texto y es donde podemos escribir los comandos.

## Que es prompt?
Es una señal que muestra el *CLI* para indicar que esta esperando la "entrada" del usuario.

## Que es un comando?
Es un grupo de tareas o una tarea que el ordenador debe realizar. Cuando se escribe un comando, el sistema operativo ejecuta un proceso para recibir la entrada (comando) y luego, internamente manipula datos o ejecuta otros procesos para posteriormente dar un resultado como respuesta.

## Nota
La mayoria de los comandos siguen un patron de sintaxis:

```
comando [opciones...] [argumentos...]
```
- comando: tarea a ejecutar.
- opciones: alteran el comportamiento del comando.
- argumentos: es o son los argumentos donde se require que el comando actue.

## Argumentos
Un ejemplo claro puede ser al usar el comando **ls** y seguido brindarle el nombre de un directorio.
```
ls Documents
```
En este caso el argumento seria el nombre del directorio y, como se interpretaria esto segun lo mencionado anteriormente?

El comando **ls** muestra un listado de contenidos del directorio actual pero si le brindas el nombre de un directorio (que vendria a ser un argumento), el comando ls ya no hara efecto al directorio actual sino al argumento (directorio proporcionado) y mostrara su contenido.

## Opciones
Un ejemplo puede ser el comando **ls** y seguido brindarle la opcion **-l**. Esto hara que el comando se comporte de una forma diferente. En ves mostrar el contenido del directorio verticalmente los listara horizontalmente y ademas mostrar informacion adicional al respecto.

Estas opciones pueden ser mas de una y a su vez puede ir juntas. Hay varias formas de combinarlas y usarlas.
```
ls -l -r
ls -rl
ls -lr
```
En este caso todo esto producira el mismo resultado. Como se menciono, las opciones pueden ir separadas, juntas o los mismo pero con el orden invertido.
### Nota
En su mayoria el caracter elegido para el comando es memotecnico de su proposito en ingles. Por ejemplo: **l** se refiere a largo (long) y **r** invertir (reverse).

## Rutas absolutas
Una ruta absoluta le permite especificar la ubicación exacta de un directorio. Siempre comienza en el directorio root, por lo tanto siempre comienza con el carácter `/`. La ruta al directorio de inicio (home) `/home/sysadmin` es una ruta absoluta.

## Rutas relativas
Una ruta relativa ubica un archivo en relación con la ubicación actual del usuario en el sistema de archivos. Las rutas relativas no comienzan con el carácter `/`, comienzan con el nombre de un directorio.
```
sysadmin@localhost:~/Documents$ cd School/Art
sysadmin@localhost:~/Documents/School/Art
```