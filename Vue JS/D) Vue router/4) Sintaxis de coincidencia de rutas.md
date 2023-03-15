Cuando se tiene 2 rutas similares y se quiere que se diferencien se usara algo llamado **expresiones regulares**.

En este caso veremos como se diferencia una ruta que recibe como parámetro números y otra strings.

Veamos:

```Javascript
Javascript
import NotFound from "@/views/NotFound.vue";
const routes = [
{
    path: "/compras/:orderId(\\d+)",
    name: "Order",
    component: Order
  },
  {
    path: "/compras/:producName",
    name: "Product",
    component: Product
  }
];
```

La expresión **(\\d+)** indica la coincidencia de un número y lo toma.
De esta manera se diferenciaría de la ruta similar que se tiene abajo, ya que, si se ingresa un string no lo tomará y se usará la ruta "/compras/:productName".

