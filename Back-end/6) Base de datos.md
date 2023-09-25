Partimos desde el servidor:

![[Captura desde 2023-09-24 18-50-05.png]]

Le hacemos un zoom:

![[Captura desde 2023-09-24 18-51-06.png]]

Dentro del servidor, puede uno o varios servicios de backend corriendo, al igual que base de datos.

# ¿Cómo se conectan estos servicios entre si?
Se conectan a través de drivers. Cada base de datos tiene su propio driver y estan adaptados para diferentes lenguajes.

![[Captura desde 2023-09-24 18-55-44.png]]}
Las base de datos relacionales tienen un lenguaje en común "SQL"
Los frameworks aprovechan estas características	mediante el uso de los ORM. Esto debido a que abstraen la conexión a la base de datos y  permiten realizar peticiones/consultas, mediante la programación orientada a objetos, a la base de datos.

Importante:
Si utilizamos el ORM, nos da la posibilidad de realizar un cambio entre esas bases de datos de la imagen, debido a que manejan el mismo lenguaje SQL.