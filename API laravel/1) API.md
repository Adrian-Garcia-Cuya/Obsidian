# ¿Qué es?
Una API (Application Programming Interfaces) es una interfaz que se usa para comunicar distintos programas (cliente). Estas reciben peticiones y envian respuestas.

# Conceptos
Clientes -> programas que realizan peticiones.
API -> programa que reciben perticiones.
Recursos -> son la información que diferentes aplicaciones proporcionan a sus clientes.

**_La máquina encargada de entregar el recurso al cliente también recibe el nombre de servidor. Las organizaciones utilizan las API para compartir recursos y proporcionar servicios web, a la vez que mantienen la seguridad, el control y la autenticación._**

# Tipos de APIs
## Abiertas
Pueden acceder cualquier tipo de clientes.
## Privadas
Se crean para uso interno. Se utiliza para mejorar la comunicación dentro de una organización.

# REST (Representational State Transfer)
Rest (Transferencia de Estado Representacional) es una arquitectura de desarrollo web que te da una serie de reglas/guias sobre como debes crear una API.

1) **Cliente servidor**: Debe haber una separación de responsablilidad entre la API y los clientes. El cliente se encarga de la interacción con el usuario y el servidor de gestionar y procesar los datos.
2) **Es un protocolo sin estado**, es decir no se guarda información en el servidor, como: sesiones de usuario por ejemplo.
3) **Cacheable**: Las respuestas de la API deben poder ser almacenadas en cache por el cliente.
4) **Interfaz uniforme**: Indica que el servidor transfiere información en formato estándar. Por ejemplo, el servidor puede almacenar los datos como texto, pero enviarlos en formato de representación HTML.
5) **Sistema de capas**: el servidor puede disponer de varias capas para su implementación. Esto ayuda a mejorar la escalabilidad, el rendimiento y la seguridad.
6) **Codigo bajo demanda:** 

Se considera una API resful si el protocolo por el cual se comunica el cliente y la API es a través del protocolo "HTTP".

### Nota
La mayoria de peticiones que hace el cliente se realiza utilizando el formato "JSON" y la respuesta será en el mismo formato.

# Endpoint

Una "endpoint" son las URLs de la API. En este caso se va a definir como rutas en laravel.