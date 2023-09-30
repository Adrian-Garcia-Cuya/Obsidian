Un comando pueden ser basicamente 4 cosas: 

![[Pasted image 20230928141114.png]]

1. Se compilo en un lenguaje de programacion y se pueden ejecutar.
2. Comando que viene por defecto dentro de la shell.
3. Son funciones externas de la shell.
4. Es una forma de crear atajos para ejecutar comandos.

- **comando type** -> nos permite ver la naturaleza de un comando.
Ejemplo: "type 'nombre_comando'"

- **comando alias** -> permite crear atajos para ejecutar ciertos comandos.
Ejemplo: "alias l='ls -lh'"

Nota: los alias no son permanentes, duran el tiempo que se mantiene abierta la ventana de la terminal. Hay una forma de guardarlos. Se ve en el tema de 'variable de entorno'.

- **comando help** -> nos muestra informacion de un comando.
Ejemplo: "help 'nombre_comando'"

IMPORTANTE -> si se escribe '--' obligatoriamente, va una palabra al lado.

- **comando man** -> nos muestra el manual de usuario de un comando.
Ejemplo: "man 'nombre_comando'"

- **comando info** -> nos muestra la descripcion de un comando.
Ejemplo: "info 'nombre_comando'"

- **comando whatis** -> nos muestra informacion breve de como funciona un comando.
Ejemplo: "whatis 'nombre_comando'"