**Sesiones:**

1. La información de la sesión se almacena en el servidor, generalmente en una base de datos o una memoria caché.
    
2. Cada vez que se realiza una solicitud, el servidor debe consultar y validar la información de la sesión en su almacenamiento.
    
3. Los servidores de aplicaciones mantienen un estado de sesión para cada usuario autenticado.
    
4. Las sesiones pueden ser eficaces para aplicaciones monolíticas y menos distribuidas, pero pueden presentar desafíos de escalabilidad y mantenimiento.
    

**JWT (JSON Web Tokens):**

1. La información del usuario y otros datos relacionados con la sesión se almacenan en el propio token (payload del JWT). Esto incluye información como el ID de usuario, roles, permisos y otros detalles relevantes.
    
2. La firma del JWT se utiliza para verificar la autenticidad e integridad del token, pero no se necesita una consulta adicional al servidor para validar la sesión. El servidor simplemente verifica la firma y confía en los datos del JWT.
    
3. Los servidores no mantienen un estado de sesión para usuarios autenticados, lo que los hace "stateless". Cuando se dice que los servidores son "stateless" en el contexto de JWT (JSON Web Tokens), significa que los servidores no guardan ni recuerdan información sobre la sesión de un usuario autenticado entre diferentes solicitudes.
    
4. Los JWT son útiles en arquitecturas distribuidas, microservicios y aplicaciones altamente escalables, ya que simplifican la autenticación y autorización en sistemas distribuidos.
    

Por lo tanto, la diferencia fundamental radica en dónde se almacena la información de la sesión y cómo se verifica la autenticación y la autorización. Las sesiones requieren almacenamiento en el servidor y validación adicional, mientras que los JWT contienen toda la información necesaria y se verifican mediante su firma.

![[Flujo_sesion.png]]

![[flujo_token.png]]

![[Captura desde 2023-10-15 10-23-34.png]]


