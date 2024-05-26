Linux tiene una funcion de linea de comandos llamada *redireccion de entrada/salida (E/S) (input/output; IO)*. La redireccion permite enviar la informacion de la linea de comandos a otros archivos, dispositivos y otros comandos.

La entrada y salida de comando se compone de 3 rutas o vias. Estas se denominan *descriptores de archivos*, los cuales tienen el siguiente nombre:

- **Entrada estandar (standard input (STDIN))** : esto hace referencia a la informacion que el comando recibe(como archivos por ejemplo) y procesa cuando se ejecuta.

![[Pasted image 20240524155520.png]]

- **Salida estandar (STDOUT)**: esto es la informacion que muestra el comando, es decir, la informacion resultante.

![[Pasted image 20240524155545.png]]

- **Error estandar (STDERR)** : son los mensajes de error generados por los comandos que no se ejecutaron correctamente. 

![[Pasted image 20240524155610.png]]

#### Nota - mensaje
En este apunte solo estara cubriendo el descriptor *STDOUT*.

# Redirigiendo la salida estandar
Se tomara como ejemplo el siguiente archivo.

![[Pasted image 20240524155820.png]]

Para redirigir la informacion que muestra el comando se debe utilizar el simbolo ">":

![[Pasted image 20240524155939.png]]

Esto indica que la salida del comando *cat*, de la entrada *food.txt*, se copiara en un nuevo archivo llamado *newfile1.txt*

Tambien se puede redirigir lo que imprime en consola en comando *echo*:

![[Pasted image 20240524160216.png]]

#### Importante 
Cuando se utiliza la redireccion a un archivo existente se debe tomar encuenta que se reemplazara el contenido del archivo con la salida del comando que se redirige. Una forma de evitar esto es agregando otro simbolo mas *>>*.

![[Pasted image 20240524160421.png]]