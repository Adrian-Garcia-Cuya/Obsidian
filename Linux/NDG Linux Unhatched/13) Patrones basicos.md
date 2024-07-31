Las [[12) Expresiones regulares#^940a74|expresiones regulares]] son patrones que solo algunos comandos pueden interpretar. Estos patrones pueden ser utilizados para buscar o identificar cadenas de texto específicas que sigan ciertas reglas o formatos.

# Caracteres de anclaje
Los caracteres de anclaje es una de las formas con las que se puede utilizar expresiones regulares para limitar los resultados de una busqueda.

Por ejemplo, busquemos *root* que se repite reiteradamente:
```
sysadmin@localhost:~/Documents$ grep 'root' passwd
root:x:0:0:root:/root:/bin/bash                                                 
operator:x:1000:37::/root:
```

El primer carácter de anclaje `^` se utiliza para indicar que el patrón debe aparecer al principio de la línea.

El segundo carácter de anclaje `$` se puede utilizar para indicar que el patrón debe aparecer al final de la línea.
```
sysadmin@localhost:~/Documents grep 'r$' alpha-first.txt
B is for Bea**r**
F is for Flowe**r**
```

#### Nota
Para evitar que la [[3) Acceso administrativo#^7ae08d|shell]] malinterprete los caracteres especiales (en este caso *root*), estos patrones pueden escribirse 'protegidos' por comillas simples.

# Encontrar caracteres coincidentes usando `.`
El caracter `.` puede representar cualquier caracter de nueva linea.

```
sysadmin@localhost:~/Documents$ grep 'r..f' red.txt
reef
roof
```

En esta busqueda el patron indica que debe empezar con "r", luego, los siguientes 2 caracteres puede ser cualquier caracter debido al ".", finalmente, el patron debe terminar en el caracter "f".

Este caracter puede usarse las veces que se requiera. Para encontrar todas las palabras de al menos cuatro caracteres se puede utilizar el siguiente patrón:

```
sysadmin@localhost:~/Documents$ grep '....' red.txt                          
reef
reeed
roof                                                                           
reed
root
reel
read
```

# Encontrar un carácter único usando `[]`
Los corchetes se utilizan para indicar caracteres unicos o un rango de caracteres a buscar en una entrada de texto.

Para buscar caracteres unicos que se deseen busca se puede realizar de la siguiente manera:

![[grep-corchete.png]]

Como se puede observar, se especificaron en este caso 2 caracteres a buscar y como resultado nos muestra las lineas donde encontro esos caracteres presente.

Para encontrar todas las líneas en el archivo `profile.txt` que contienen un número, utilice el patrón `[0123456789]` o `[0-9]`:

![[grep-corchete2.png]]

Por otro lado, para encontrar todas las líneas que contienen caracteres no numéricos, inserte un `^` como primer carácter dentro de los corchetes. Este carácter niega los caracteres que lo siguen:

![[grep-corchete3.png]]

Como se puede observar, el resultado muestra en rojo los caracteres que no pertenen al rango de caracteres no numericos y en blanco los que si. Mientra haya aunque sea un caracter no numerico en la linea lo mostrara.

Cuando otros caracteres de expresión regular se colocan dentro de corchetes, se tratan como caracteres literales. Es decir, por su significado real. Por ejemplo, el `.` permite representar cualquier caracter pero si se coloca dentro de los corchetes `[]` se tomara como un caracter de "."

![[grep-corchete4.png]]

# Indicar un carácter o patrón repetido utilizando el `*`
Este caracter indicar la ausencia o la presencia una o más veces del carácter o patron que lo precede (que esta antes del `*`).

![[Pasted image 20240517160810.png]]

Se puede observar que el caracter "e" puede estar presente o mas de una vez presente. Siempre y cuando se cumpa la primera letra "r" y la final "d".

Es posible utilizarlo tambien al querer buscar caracteres unicos. Por ejemplo:

![[Pasted image 20240517161046.png]]

Esto obtiene todas las coincidencia de "r" como primera letra, tanto la letra "o" como "e" pueden estar ausentes o presentes mas de una vez y finalmente la ultima letra debe ser "d".

# Entrada estándar
Cuando no se brinda el nombre de un archivo `grep` actuadra sobre la entrada estandar, es decir, tomara la informacion a partir de lo que se escriba en el teclado. En cada linea que se escriba `grep` hara una busqueda del patron dado.

![[Pasted image 20240517161448.png]]

Para salir, solo se debe presionar **Ctrl+d**.