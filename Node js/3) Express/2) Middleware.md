Las funciones de _middleware_ son funciones que tienen acceso al objeto de solicitud (`req`), al objeto de respuesta (`res`) y a la siguiente función de middleware en el ciclo de solicitud/respuestas de la aplicación.

Las funciones *middleware* pueden realizar las siguientes tareas:
- Ejecutar cualquier código.
- Realizar cambios en la solicitud y objetos de respuesta.
- Finalizar el ciclo de una solicitud/respuesta.
- Invocar la siguiente función *middleware* que se encuentre en la pila.