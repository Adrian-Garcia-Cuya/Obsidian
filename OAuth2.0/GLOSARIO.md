#### Autenticar
Es la acción de verificar la identidad de un usuario.
#### Autorizar
Es la acción de dar permisos a un usuario con acceso limitado a nuestros recursos.

#### Tipos de autorización:
- Basic -> autorización mediante credenciales.
- Bearer -> es una autorización por medio del token.
###### Nota
1. Las credenciales se envian cifradas siempre y cuando la pagina cuente con el protocolo https. Si no es el caso, las credenciales quedan expuestas en la red.
2. En primera instancia se realiza una autenticación "basic" cuando el usuario ingresa sus credenciales. Luego de ser validadas, el servidor retorna un token y el usuario pasa a tener una autorización "Bearer", es decir, que ahora esta autenticado mediante el token y con eso puede realizar acciones.