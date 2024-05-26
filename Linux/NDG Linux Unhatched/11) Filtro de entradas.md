El comando `grep` es un filtro de texto que busca líneas en una entrada y devolverá aquellas que coincidan con el patrón determinado.
```
grep [OPCIONES] PATRÓN [ARCHIVO]
```

```
sysadmin@localhost:~/Documents$ grep sysadmin passwd    
sysadmin:x:1001:1001:System Administrator:/home/sysadmin:/bin/bash
```
En este caso se utilizo el comando *grep* para buscar la palabra "sysadmin" dentro de "passwd".

El ejemplo anterior utiliza un término de búsqueda simple como patrón; sin embargo *grep* es capaz de interpretar patrones de búsqueda mucho más complejos.
## Nota
Un patron es una secuencia específica de caracteres que el comando busca dentro de un archivo o una entrada de texto. Este patrón puede ser una cadena de texto simple o puede contener caracteres especiales que permiten realizar búsquedas más complejas y flexibles.