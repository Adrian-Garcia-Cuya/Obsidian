# Event Loop

Tarea signada para mover del Task Queue al Stack, solo si el Stack está vacío.

**CONCEPTOS**

### Memory Heap

Los objetos, variables, funciones son asignados a un montículo (espacio grande en memoria no organizado) en la espera de ser utilizados.

### Call Stack (pila)

Apila de forma organizada las instrucciones de nuestro programa.

### Task queue

Cola de tareas, se maneja la concurrencia, se agregan las tareas que ya están listas para pasar al Stack (pila). El Stack debe de estar vacío.

### MicroTask Queue

Las promesas tienen otra forma de ejecutarse y una prioridad superior.

### Web APIs

JavaScript del lado del cliente: setTimeout, XMLHttpRequest, File Reader, DOM.

**Nota:** Javascript nació dentro del navegador con la finalidad de generar interacciones con el usuario.

![[Curso de Asincronismo con JavaScript/Imagenes/asincronismo.png]]
