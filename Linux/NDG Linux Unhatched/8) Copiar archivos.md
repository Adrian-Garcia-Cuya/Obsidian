Crear copias de archivos puede ser útil por numerosas razones:
- Si se ha creado una copia del archivo antes de que se hayan realizado cambios, siempre podremos revertir al archivo original.
- La copia de un archivo puede utilizarse para transferirlo a un dispositivo extraíble.
- La copia de un documento puede utilizarse como plantilla para un documento nuevo.

```
cp [OPCIONES] ORIGEN DESTINO
```

El comando **cp** se utiliza para copiar archivos. Similar al comando **mv**, requiere al menos dos argumentos: un origen y un destino.


```
sysadmin@localhost:~/Documents$ cp /etc/passwd .
//origen -> /etc/passwd
//destino -> .
//el punto significa el directorio actual.
```

### Nota
Los permisos pueden afectar a los comandos de administración de archivos, como el comando **cp**. Para copiar un archivo, es necesario tener permiso de ejecución para acceder al directorio donde se encuentra el archivo y permiso de lectura para el archivo que se está copiando.

También es necesario tener permiso de escritura y ejecución en el directorio al que se está copiando el archivo. 