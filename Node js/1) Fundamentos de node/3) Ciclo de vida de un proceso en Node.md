Los ciclos de vida de un proceso en *Node js*, a groso modo, se dividen en 3 partes.
Se tiene la **Pila de procesos (Call Stack)**, **Node Apis** y **Cola de callback**.

Todo parte desde la *Pila de procesos*, cuando se ejecuta una aplicacion, se crea el metodo *main*, el cual, ejecutara todas las lineas de codigo.

Veamos un ejemplo:

Se tiene el siguiente codigo a la derecha y en la pila de procesos ya se creo el metodo *main*.

![[ciclo-vida-main.png]]

Luego, toma la primera linea de codigo, la apila en el **Call Stack**, la ejecuta y la elimina.

![[ciclo-vida-ejecucion.png]]

Posteriormente toma la siguiente linea, que en este caso es un *setTimeout* y lo apila. Lo que hara es solo registrar la funcion pero no la eliminara de la pila porque todavia no se resuelve. Esto sucede porque *setTimeout* es una funcion asincrona y se especifica que se ejecutara pasado los 3 segundos.

![[Pasted image 20240514105355.png]]

Cuando se tiene operaciones asincronas (como esta), node la mueve al espacio de **Node Apis**. Aqui entraran todo las operacion asincronas y se esperara a que termine su proceso (o tiempo de espera).

![[ciclo-vida-node-apis.png]]

Continuando, se seguiran agregando al **Node Apis** los siguientes *setTimeout*, ya que, es el mismo proceso aunque con diferente tiempo de espera. Hasta que llegue a la ultima linea de codigo, la cual se agregara a la pila y se ejecutara.

Luego de ello, los *setTimeout* dentro del espacio de **Node Apis** ya habra terminado el tiempo de espera.

![[ciclo-vida-node-apis2.png]]

Por lo tanto, lo que hace node es moverlo no a la *pila de procesos* nuevamente, sino, lo que hace es moverlo a la **Cola de callback**, que es donde entraran todos los procesos asincronos una vez terminados.

![[ciclo-vida-cola-callback.png]]

Algo importante a mencionar es que la *cola de callbacks* mueve los procesos terminados a la *pila de procesos* pero esto lo hace unicamente cuando ya no haya ningun proceso ejecutandose en el.

Una vez que se compruebe que no hay ningun proceso ejecutandose en la pila, node mueve los procesos que estan listos para ejecutarse de la *cola de callbacks* a la *pila de procesos*.

Como se puede ver se ejecuta el *console.log* que estaba en el callback del *setTimeout* y lo elimina; y luego elimina el *main*.

![[ciclo-vida-en-espera.png]]

Este no quiere decir que aqui termino la aplicacion de node, como se puede ver todavia hay 2 *setTimeout*. 1 puede estar todavia en la espera y el otro probablemente ya este en la *cola de callbacks*. 

![[Pasted image 20240514111521.png]]

![[Pasted image 20240514111542.png]]

![[Pasted image 20240514111601.png]]

Una vez que no hay ningun proceso ejecutandose o en espera termina la aplicacion.

![[Pasted image 20240514111613.png]]




