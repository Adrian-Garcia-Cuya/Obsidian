- **Escalamiento vertical** => consiste en aumentar los recursos de la maquina.

![[Captura desde 2023-09-24 21-38-59.png]]

- **Escalamiento horizontal** => creamos varios servidores "al lado" con las mismas características de recursos.

![[Captura desde 2023-09-24 21-42-09.png]]

# Ejemplo

![[Captura desde 2023-09-24 21-46-10.png]]
# Load Balancer
Distribuye las peticiones en paralelo a cada uno de los servidores. En caso de que falle uno deja de enviar peticiones a ese servidor y lo distribuye a los otros.

![[Captura desde 2023-09-24 21-45-32.png]]

# Problema con Load Balancer
Uno de los problemas principales problemas de usar el "Load Balancer" es si tenemos la base de datos en el mismo servidor del backend. Esto es porque si un usuario hace un request el cual llega al load balancer y lo envía a un servidor "x", se guarda la información, pero si recarga la página y hace otro request, el load balancer, si detecta que el sever "x" no esta disponible enviará el request a otro servidor con otra base de datos donde no encontrará la información en principio.

![[Captura desde 2023-09-24 21-48-11.png]]

# Replicación
Es el proceso de sincronizar varias bases de datos. Esto con la finalidad de no repetir el mismo problema que con los servidores como se puede observar en la imagen.

![[Captura desde 2023-09-24 21-57-10.png]]

