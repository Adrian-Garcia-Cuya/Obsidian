Analizaremos a detalle la informacion que nos muestra la terminal al momento de listarnos los archivos.

Para obtener información detallada sobre los archivos, como el tipo de archivo, los permisos, las propiedades o el sello horario, se debe ejecutar una lista larga utilizando la opción `-l` con el comando `ls`.

![[comando_ls-l.png]]

Cada linea corresponde a un archivo dentro del directorio. La informacion de cada archivo esta dividida por campos separados por espacios.

## Listado de campos
**Tipo de archivo :** este primer campo contiene 10 caracteres. El primer caracter indica el tipo de archivo y los siguientes 9 los permisos.

![[senalizacion_tipo_archivo.png]]

Los tipos de archivos son:
![[tipo_archivos.png]]

**Permisos :** los permisos indican como determinados usuarios pueden acceder a un archivo.

![[permisos.png]]

**Número de enlaces directos :** el numero indica cuantos enlaces directos apuntan a este archivo.

![[enlaces_directos.png]]

**Propietario del archivo :** cada que se crea un archivo se le asigna automaticamente el usuario que lo creo.

![[propietario_archivo.png]]

**Grupo propietario del archivo :** Indica qué grupo posee este archivo.

![[grupo_archivo.png]]

**Tamaño del archivo :** 

![[tamano_archivo.png]]

Nota: Los directorios y archivos más grandes pueden mostrarse en kilobytes ya que mostrar su tamaño en bytes resultaría en un número demasiado grande.

**Sello horario o de tiempo :** Indica la fecha y hora en que el contenido del archivo se modificó por última vez.

![[sello_horario.png]]

**Nombre del archivo :** El campo final contiene el nombre del archivo o directorio.

![[nombre_archivo.png]]

#### Importante
En el caso de enlaces simbólicos, **un archivo que apunta a otro archivo** (acceso directo), el nombre del enlace se mostrará junto a una flecha y el nombre de la ruta del archivo original.

![[enlace_simbolico.png]]

## Opciones extra para el comando ls

- **-t** (timestamp) -> ordena los archivos por su sello de tiempo.
- **-s** (size) -> ordena los archivos por su tamaño.
- **-r**  (reverse) -> invierte el orden de cualquier tipo de ordenacion.