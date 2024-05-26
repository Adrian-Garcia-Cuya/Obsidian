El comando `mv` se utiliza para mover un archivo de una ubicación en el sistema de archivos a otra.
```
mv ORIGEN DESTINO
```

Generalmente, los archivos que se van a mover se denominan origen, y el lugar donde se van a colocar se denomina destino.

Para mover el archivo `people.csv` al directorio `Work`, utilice el nombre del archivo como origen y el nombre del directorio como destino:
```
sysadmin@localhost:~/Documents$ mv people.csv Work
```

Puede cambiar el nombre del archivo al momento de moverlo a otro directorio.
```
sysadmin@localhost:~/Documents$ mv 'file_name' 'directory/new_file_name'
sysadmin@localhost:~/Documents$ mv people.csv Work/changepeople.csv
```

Mover un archivo dentro del mismo directorio es una forma eficaz de cambiarlo de nombre. Por ejemplo, en el ejemplo siguiente, el archivo `animals.txt` recibe un nuevo nombre `zoo.txt`:
```
mv animals.txt zoo.txt
```

El comando `mv` puede utilizarse para mover varios archivos, siempre y cuando el argumento final proporcionado al comando sea el destino. Por ejemplo, para mover tres archivos al directorio `School`:
```
sysadmin@localhost:~/Documents$ mv numbers.txt letters.txt alpha.txt School        
sysadmin@localhost:~/Documents$ ls School                                       
Art  Engineering  Math  alpha.txt  letters.txt  numbers.txt
```

### Nota
Los permisos pueden afectar comandos de administración de archivos, incluyendo el comando `mv`. Mover un archivo requiere tener permisos de escritura y ejecución tanto en los directorios de origen como de destino.
