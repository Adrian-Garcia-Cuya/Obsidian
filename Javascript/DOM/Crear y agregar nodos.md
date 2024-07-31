# Crear y agregar nodos

![[DOM/Imagenes/CrearAgregarNodos.png]]

![[DOM/Imagenes/CrearAgregarNodos2.png]]

==**IMPORTANTE**==

Crear un elemento no quiere decir que se agregue al DOM. Esta creación sucede en memoria y se asigna a una variable pero en ningun momento se agrega.

![[CrearTexto 1.png]]

Podemos agregar nodos de las formas siguientes:

![[DOM/Imagenes/agregarNodos.png]]

Recordar que con "appendChild" el nodo se agrega al final de la lista.

![[DOM/Imagenes/agregarNodoAppenchild.png]]

Nueva api para agregar nodos "append".
Utilizar "append" tiene algunas mas ventajas:

![[DOM/Imagenes/agregarNodoAppend.png]]

![[DOM/Imagenes/agregarNodoAppend2.png]]

"insertBefore" agrega el nodo antes del nodo de referencia.

![[DOM/Imagenes/agregarInserbefore.png]]

**Ejemplo:** document.insertBefore(node, referencia)

node -> nodo que queremos agregar.

referencia -> nodo al que hacemos referencia para que se agregue el nuevo nodo.

==**IMPORTANTE**==

![[DOM/Imagenes/agregarInserbeforeNota.png]]

Ultima forma de agregar un nodo.

![[DOM/Imagenes/agregarInsertAdjacentElement.png]]

![[DOM/Imagenes/agregarInserbefore3.png]]

```Javascript
referencia.insertAdjacentElement('beforebegin', nodo)

referencia.insertAdjacentElement('afterbegin', nodo)

referencia.insertAdjacentElement('beforeend', nodo)

referencia.insertAdjacentElement('afterend', nodo)
```