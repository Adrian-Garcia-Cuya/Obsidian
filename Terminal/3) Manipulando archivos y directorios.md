- **Crear una carpeta** => comando "mkdir"
Ejemplo: "mkdir 'nombre_carpeta'"
- **Crear una archivo** => comando "touch"
Ejemplo: "touch 'nombre_archivo'"

Nota: el comando touch crea un archivo que por defecto linux lo considera texto pero se puede definir la extension.

Se puede crear varios directorios y archivos a la vez:
Ejemplo: "mkdir 'name1' 'name2' 'name3'"
Ejemplo: "touch 'file1' 'file2' 'file3'"

- **Copiar un archivo** => comando "cp"
Ejemplo: "cp file1 'nombre_archivo_copia'" -> 'cp file1 file_bk'

Importante: como no se indica la ruta, el so entendera que estas copiando ese archivo en la misma ruta donde se encuentra. Practicamente, es como si se agregara un "./" invisible.

- **Mover un archivo** => comando "mv"
Ejemplo: "mv file_bk 'ruta_destino'" -> 'mv file_bk ..'

Nota: el comando "mv" te permite cambiar de nombre el archivo.
Ejemplo: "mv file_bk 'nuevo_nombre'" -> "mv file_bk fileCopy"

- **Eliminar un archivo** => comando "rm"
Ejemplo: "rm 'nombre_archivo'"

 **Eliminar un archivo de forma interactiva** => comando "rm -i"
Ejemplo: "rm -i 'nombre_archivo'"

Nota: te consulta si deseas eliminar el archivo "x". Escribir solo "y" para aceptar.

- **Eliminar un directorio** => comando "rm -r"
Ejemplo: "rm  -r 'nombre_carpeta'"

 **Eliminar un directorio de forma interactiva** => comando "rm -ri"
Ejemplo: "rm -ri 'nombre_carpeta'"

Nota: te consulta si deseas eliminar la carpeta "x" y hace la misma consulta, uno por uno con cada archivo dentro de la carpeta. Escribir solo "y" para aceptar.