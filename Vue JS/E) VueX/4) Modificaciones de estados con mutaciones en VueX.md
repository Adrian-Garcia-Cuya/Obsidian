# Que es?
Los 'mutations' son métodos dentro de la tienda que van a permitir que podamos modificar los valores de los estados.

Vamos como definirlos:
![[vuex-mutations.png]]
En esta ocasión, se han creado dos métodos, 'decrement' e 'increment', los cuales incrementaran o disminuirán el valor del estado 'count'.

Al igual, como se vio anteriormente, para usar estos métodos hay que realizar un llamado un poco extenso como el siguiente:

```js
$store.commit('increment');
```

Para evitar escribir tanto, como ya se vio, se pueden mapear también los 'mutadores'.

Veamos:
![[vuex-mutationsUse.png]]

Se importo la función, 'mapMutations', esta creara la funciones por nosotros y crearan las funciones que llamen a los 'mutadores'. Recibira como parámetro un array con el nombre de los mutadores que se requieran.