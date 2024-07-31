El editor de texto principal de Linux y UNIX es `vi`. Algo que destacar es que de este editor esta disponible en todas las distribuciones de linux y se puede ejecutar tanto en el CLI como en una GUI.

Veamos un ejemplo de uso:

![[Pasted image 20240525164203.png]]

# Modos de vi
`vi` cuenta con 3 tipos de modos:

## Modo comando
El modo comando es el que empieza con el programa. En este punto se pueden escribir comandos para desplazar y manipular texto o acceder a otros modos. Si se encuentra en otro modo, para regresar al *modo comando* solo se debe presionar la tecla **Esc**.

Este modo cuenta con 2 caracteristicas: el movimiento a realizar y el contador, este ultimo indica cuantas veces debe realizarce dicho movimiento.

Tiene el siguiente formato:
```
[numero] movimiento
```

Esta tabla contiene todos los movimientos disponibles:
![[Pasted image 20240525165323.png]]

Siguiendo el formato, veamos un ejemplo:

![[Pasted image 20240525165717.png]]

En el siguiente listado, se tiene el cursor en la primera palabra. Como indica en la tabla podemos desplazarnos habia abajo con la techa **j**, pero si es necesario desplazarse mas de una linea, se puede indicar la cantidad. Por ejemplo, si es requerido moverse 5 filas abajo se deben presionar la siguientes teclas **5 + j**.

El puntero se moveria a lo siguiente:

![[Pasted image 20240525170041.png]]

Esto se puede realizar con cualquier movimiento.

### Modo de acciones
El editor `vi` cuenta con los siguientes 3 comandos:

![[Pasted image 20240525170231.png]]

Los comando de movimiento ayudan ubicar un punto especifico del texto para luego poder aplicarle ciertas *acciones*. Tomar en cuenta que esta acciones tienen efecto apartir de la ubicacion del puntero.

Tienen el siguiente formato:

```
accion [numero] movimiento
```

o

```
[numero] accion movimiento
```

- **Eliminar** -> suprime el texto indicado en el archivo y lo guarda en el *bufer* (portapapeles).

![[Pasted image 20240525170650.png]]

- **Cambiar** -> al igual que en eliminar, esta accion elimina el texto y lo guarda en el *bufer* pero con la diferencia que el programa cambia a **modo insercion**, esto permite poder cambiar el texto desde donde este ubicado el cursor.

![[Pasted image 20240525171039.png]]

- **Sacar** -> guarda el texto o contenido en el *bufer* sin eliminarlo.

![[Pasted image 20240525171228.png]]

- **Poner** -> coloca la informacion guardada en el *bufer* antes o despues de la posicion del cursor.

![[Pasted image 20240525171436.png]]

#### Nota - acciones
Algo importante a mencionar, es que todas las acciones que cuenten con numeros para repetir la accion, esta puede ser cambiada por cualquier otro numero, segun lo que se necesite.

## Modo insertar
El modo insertar permite poder ingresar texto a un documento.

La siguiente tabla muestra las formas en como se puede acceder al modo insertar:

![[Pasted image 20240525173352.png]]



## Buscar en vi
El programa `vi` permite realizar busquedas complejas o avanzadas debido a que admite expresiones regulares.

Para realizar una busqueda se debe presionar la tecla `/`, luego, esto esperara el texto o la expresion a buscar.

Veamos un ejemplo:

```
/[ae]
```

En este caso se agrego una expresion regular para buscar las coincidencias entre 2 caracteres unicos "a" y "e". 

Posterior a ello, se debe presionar la tecla **Enter** para realizar la busqueda. Para desplazarse a los siguientes resultados se presiona la tecla *n* y si se desea regresar, se presiona la tecla *N*.

Por defecto, muestra los resultados apatir de la primera coincidencia. Para invertir esto, es decir, que empiece mostrando la ultima coincidencia solo de debe reemplaza el `/` por `?`

```
?[ae]
```

## Modo ex
El modo "ex" en `vim` tiene sus raíces en el editor original llamado `ex`. El nombre `vi` proviene de un comando dentro de `ex` que permitía cambiar al modo "visual". Inicialmente, `ex` solo permitía a los usuarios ver y editar una línea a la vez. Con el comando "visual" (`vi`), los usuarios podían ver y editar múltiples líneas a la vez, lo que resultaba más conveniente.

Finalmente, `vi` se convirtió en el nombre principal del programa. En el modo `ex` de `vim`, se pueden ver o cambiar configuraciones y ejecutar comandos de archivo como abrir, guardar o cancelar cambios en un documento. Para acceder al modo `ex`, simplemente escribe `:` en el *modo comando* de `vim`.

Algunas de las acciones mas usadas en el *modo ex*:

![[Pasted image 20240525174938.png]]

Con *escritura* hace referencia a **guardar**.

Un análisis rápido de la tabla anterior revela que cuando un signo de exclamación, `!` , se agrega a un comando, se intentará forzar la operación.

#### Nota - editor vi mejorado
Un punto a mencionar es que el editor `vi` orginal no se encuentra en los sistemas Linux, en cambio, cuenta con la version mejorada llamada `vim (vi improved)`. Ambos funcionan igual, la diferencia es que `vim` cuenta con funciones adicionales.