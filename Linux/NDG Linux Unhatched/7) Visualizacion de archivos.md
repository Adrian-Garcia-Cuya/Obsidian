Existen varios comandos en Linux disponibles para visualizar el contenido de los archivos. El comando `cat`, que significa “concatenar”, a menudo se usa para ver rápidamente el contenido de archivos pequeños debido a que muestra todo el contenido.

```
cat [OPCIONES] [ARCHIVO]
```

```
sysadmin@localhost:~/Documents$ cat animals.txt
```

Otra forma de ver el contenido de los archivos es utilizando los comandos **head** y **tail** .
- head -> se utiliza para ver un número seleccionado de líneas desde la parte superior del archivo.
```
sysadmin@localhost:~/Documents$ head alpha.txt
```
- tail -> se utiliza para ver un número seleccionado de líneas desde la parte inferior del archivo.
```
sysadmin@localhost:~/Documents$ tail alpha.txt
```
Por defecto, ambos comando muestran 10 lineas, ya sea superior o inferior. Si se desea especificar un numero de lineas a ver en concreto, se puede hacer agregando la bandera **-n**

```
sysadmin@localhost:~/Documents$ head -n 5 alpha.txt

sysadmin@localhost:~/Documents$ tail -n 5 alpha.txt
```



