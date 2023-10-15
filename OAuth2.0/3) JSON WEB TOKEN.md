### ¿Qué es un JSON Web Token?
No existe por si solo. Su existencia pueden ser de 2 tipos:

![[JSON_Web_Token.png]]

Comúnmente, en la web, es el más usado:
![[JSON_Web_Signature.png]]
El hecho que estén codificados quiere decir que se puede decodificar.

![[JSON_Web_Signature_decode.png]]

En el "Payload" tendremos algo llamado ==Claim names==, que son una forma de llamar también a las llaves.

Los claims son el estándar de como establecer información en el payload.
##### Hay 3 tipos de claim names:
1. Registered Claims -> Las especificaciones de JWT definen 7 claims registrados. No son obligatorios, pero se recomiendan para permitir interoperabilidad entre los sistemas (si se utilizan tokens entre aplicaciones terceras siempre se esperara la misma respuesta/solicitud).
Los primeros 4 son los mas utilizados:

![[Registered_claims.png]]

2. Public Claims -> se puede crear claims para el consumo publico que muestren información genérica como nombres o emails.
	Estos se deben registrar ante la IANA o usar nombres que no colisionen con otros registrados o public claims.
	LINK: https://www.iana.org/assignments/jwt/jwt.xhtml#claims
3. Private Claims -> se pueden crear claims privados para compartir información especifica de tu aplicación, como por ejemplo, la identificación del empleado, área al que pertenece dentro de la compañia, etc.

Veamos el ejemplo de un payload:

![[payload_ejemplo.png]]

Tanto el Encabezado y el Payload son objeto JSON codificados.
![[Captura desde 2023-10-14 22-26-03.png]]

La seguridad de los JWT radica en el "Firmado". Se tomada el encabezado codificado en base64, luego se concatena con un punto el payload, también codificado, y después se aplica el algoritmo de firmado (puede ser un secreto o una llave). Esta firma también queda codificada en base 64.

Es importante resaltar que la firma siempre esta compuesta por el "encabezado", el "payload" y una clave secreta .

![[Captura desde 2023-10-14 22-33-21.png]]

#### Flujo de generación del JWT
1. **Generación del JWT**: Después de que un usuario se autentica, el servidor de autenticación genera un JWT que consta de tres partes: el encabezado (header), la carga útil (payload) y la firma (signature). El encabezado y la carga útil son información legible por humanos y contienen datos sobre el usuario o la sesión. ==La firma se genera a partir del encabezado, la carga útil y una clave secreta o privada.==

2. **Entrega al Usuario**: El JWT se entrega al usuario, generalmente como una cadena codificada en base64 que puede ser almacenada en una cookie o en el almacenamiento local del navegador. El usuario lo incluirá en las solicitudes subsiguientes en el encabezado de autorización.

3. **Contenido del JWT**: La carga útil del JWT puede contener información diversa, como el ID de usuario, roles, permisos, fecha de expiración y otros datos relacionados con la sesión. La información que contiene depende de cómo esté diseñado el sistema y qué datos necesita transportar.

4. **Seguridad de la Firma**: La firma del JWT es esencial para garantizar que el token no se haya modificado durante la transmisión. La firma se calcula utilizando una clave secreta o privada que solo el servidor conoce. Cuando el servidor recibe un JWT en una solicitud, verifica la firma utilizando la misma clave y confirma que el contenido no ha sido alterado.

5. **Expiración del JWT**: Los JWT a menudo tienen una fecha de expiración (timestamp) en la carga útil que indica cuánto tiempo es válido el token. Después de la expiración, el token ya no es válido y el usuario debe autenticarse nuevamente.

6. **Uso en Solicitudes**: El cliente (por ejemplo, una aplicación web) incluye el JWT en el encabezado de autorización de las solicitudes a recursos protegidos. El servidor verifica la firma del JWT antes de procesar la solicitud. Si el JWT es válido y no ha expirado, se considera autenticado y autorizado para acceder a los recursos.

7. **Roles y Permisos**: Es común que los JWT incluyan esta información en la carga útil. Los servidores pueden usar esta información para tomar decisiones de autorización.

### Firmados mas populares

Asimétrico -> contiene una llave publica y privada.

![[Captura desde 2023-10-14 22-59-29.png]]
La llave privada solo lo debe conocer el "Authorization server" o entidades seguras.

Simetrico -> se usa una llave privada tanto para firmar como para verificar.
![[Captura desde 2023-10-14 23-02-39.png]]

### Generación de claves secretas
La clave secreta utilizada para firmar y verificar JWT ==generalmente se genera y se almacena en el servidor en un momento anterior a la generación de JWT.== La forma en que se obtiene y almacena la clave secreta depende de la implementación y de la arquitectura de seguridad de la aplicación.

Aquí hay algunas formas comunes de obtener y gestionar la clave secreta:

1. **Configuración del servidor:** La clave secreta se almacena en la configuración del servidor. ==Esto es común en aplicaciones web== o servicios que utilizan un archivo de configuración o una variable de entorno para almacenar la clave.
    
2. **Servicio de gestión de claves:** Algunas organizaciones utilizan servicios de gestión de claves (KMS, por sus siglas en inglés) para generar y almacenar claves seguras. Estos servicios proporcionan una capa adicional de seguridad y gestión de claves.
    
3. **Proceso de generación:** En el momento de la implementación o puesta en marcha, se genera una clave secreta y se almacena en un lugar seguro. Esta clave se utiliza para firmar y verificar JWT.
    
4. **Rotación de claves:** Para mantener la seguridad a largo plazo, es común realizar rotación de claves periódicamente. Esto implica generar una nueva clave y actualizar todas las partes de la aplicación que utilizan la clave para firmar y verificar JWT.
### Verificacion de una firma
La firma en un JWT se genera a partir del encabezado, el payload y la clave secreta. Luego, cuando el servidor recibe el JWT, realiza el mismo cálculo de la firma utilizando el encabezado, el payload y su propia clave secreta. Si la firma del JWT original y la firma que el servidor calcula no coinciden, es una señal de que el contenido del JWT ha sido modificado o que no se generó con la clave secreta adecuada. Esta verificación de la firma garantiza la integridad de los datos en el JWT y es una parte esencial de la seguridad en la autenticación y autorización basada en JWT.