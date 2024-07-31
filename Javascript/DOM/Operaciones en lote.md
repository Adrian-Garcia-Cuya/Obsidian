# Operaciones en lote

### ==**Importante**==

Reducir al máximo las operaciones con el DOM, con métodos que involucren escribir, modificar y eliminar, así tendremos un mejor rendimiento en nuestra aplicación.

Recomendación de como realizar operaciones en lote:

```Javascript
const nodos = [];
for(let i=0; i<100; i++){
    const node = document.createElement('input');
    nodos.push(node);
}

body.append(...nodos); //utilizamos sprend operator para agregar todos los nodos.
```