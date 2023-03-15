# ¿Qué es el asincronismo?

Los lenguajes por defecto son sincrónicos. Es decir, se ejecutan tarea por tarea.

## CONCEPTOS

### <ins>JavaScript es single-threaded</ins>

Aún con múltiples procesadores, solo se puede ejecutar tareas en un solo hilo, llamado el hilo principal.

### <ins>Bloqueante</ins>

Una tarea no devuelve el control hasta que se ha completado. Por ejemplo, un "alert" el programa se detiene y no continua hasta que le des click y se cierre el alert.

### <ins>No bloqueante</ins>

Una tarea se devuelve inmediatamente con independencia del resultado. Si se completó, devuelve los datos. Si no, un error.

### <ins>Síncrono</ins>

Las tareas se ejecutan de forma secuencial, se debe esperar a que se complete para continuar con la siguiente tarea.

### <ins>Asíncrono</ins>

Las tareas pueden ser realizadas más tarde, lo que hace posible que una respuesta sea procesada en diferido(después o luego).

### <ins>Concurrencia en JavaScript</ins>

Utiliza un modelo de concurrencia basado en un "loop de eventos".

### <ins>EventLoop</ins>

El bucle de eventos es un patrón de diseño que espera y distribuye eventos o  mensajes en un programa.

Dentro del lenguaje de programación tenemos:

### <ins>Callbacks</ins>

Una función que se pasa como argumento de otra función y que será invocada.

En el transcurso de los años el lenguaje fue mejorando y de ello surgió:

### <ins>Promesas</ins>

Función no-bloqueante y asíncrona la cual puede ==retornar un valor ahora, en el futuro o nunca.==

### <ins>Async/Await</ins>

Permite estructurar una función asincrónica sin bloqueo de una manera similar a una función sincrónica ordinaria.

JavaScript es: asíncrono y no bloqueante, con un bucle de eventos (concurrencia) implementado con un único hilo para sus interfaces de I/O (entrada/salida).