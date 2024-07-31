# Modificar el valor de un estado
Para realizar esto se creo un método en la 'tienda', el cual recibirá un parámetro, el cual, actualizara el valor del estado.

Veamos:
![[vuex-mutationsUpdate.png]]

Como se puede observar, se estará actualizando el valor del estado.

Para utilizarlo en los componentes se debe realizar lo siguiente:
![[vuex-mutationsUpdateUse.png]]

Se agrego la función nueva en el mapeo de los 'mutadores' para poder utilizarlo. Luego se creo una función la cual llamara al mutador y le enviara el argumento necesario.

###### Nota
Mencionar que en las mutaciones solo se pueden realizar operaciones sincrónicas.