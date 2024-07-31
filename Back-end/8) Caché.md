Guarda procesos para acceder a ellos posteriormente sin la necesidad de procesarlo de nuevo. Esto permite obtener una respuesta rápida a diferencia de la primera vez.

![[Captura desde 2023-09-24 22-04-11.png]]

Toda la información que se guarde en caché tiene un tiempo de expiración.

# Donde podemos aplicar la caché
Se puede aplicar en los 3 primeros casos. Esto debido a que en este tipo de páginas se suele reenviar la misma solicitud por lo que al tenerla guardada en caché la respuesta simplemente se la proporciona al usuario de forma instantánea.

![[Captura desde 2023-09-24 22-07-26.png]]

Una dato interesante, es que, utilizar la caché puede evitar ataques "DDOS", ya que, este tipo de ataques envían varias solicitudes al mismo endpoint con la finalidad de saturar el servidor pero como la respuesta se guarda en caché el servidor respondera la solicitud de forma rápida por lo que no se saturaria.j
###### Nota
La cache se puede guardar en el servidor.
