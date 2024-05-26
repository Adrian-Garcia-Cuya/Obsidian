La especificacion JSON:API, es como un cliente debe solicitar que se busquen o modifiquen los recursos, y como un servidor debe responder a esas solicitudes.

![[Ejemplo-JSON-API.png]]

![[Razones-para-usarlo.png]]

# Estructura de un documento
Se le conoce como documento al cuerpo de una peticion o respuesta. Es un objeto JSON que solo debe tener estas propiedades:

![[Pasted image 20240413213654.png]]
No necesariamente deben existir todos en un documento. Al menos uno.

## Partes del documento
- Data : Es el miembro mas importante y contiene la informacion principal del documento.
Puede ser objeto, un array de objetos, null o array vacio.
Cada uno de los objetos dentro de "Data" se les conoce como "Resource Identifier Object" y debe contener como minimo un tipo y un identificador, ambos deben ser string.
![[Pasted image 20240413214247.png]]
Opcionalmente, puede tener la siguientes propiedades:

![[Pasted image 20240413214336.png]]

Esta propiedad debe contener todas las propiedades del recurso.
![[Pasted image 20240413214403.png]]

Contiene las relaciones
![[Pasted image 20240413214430.png]]

![[Pasted image 20240413214457.png]]
En data tenemos los objetos indentificadores de recursos.
![[Pasted image 20240413214511.png]]
![[Pasted image 20240413214549.png]]

En meta se puede agregar cualquier informacion adicional.
![[Pasted image 20240413215025.png]]

En la propiedad link se tiene un link que apunta a si mismo (endpoint).
![[Pasted image 20240413215152.png]]

- Meta
![[Pasted image 20240413215349.png]]

- Jsonapi : Contiene la version de la api. Si no se especifica por defecto se asume que es la 1.0.
![[Pasted image 20240413215412.png]]

- Links : Contiene los links de paginacion. Es comun complementar los links con la propiedad meta para enviar mas informacion importante sobre la paginacion.
![[Pasted image 20240413215522.png]]

- included : Contiene todos los objetos de los recursos que estan relacionados con los datos primarios o relacionados entre si.
![[Pasted image 20240413220101.png]]

- errors : Contiene todos los objetos de error.
![[Pasted image 20240413215753.png]]
