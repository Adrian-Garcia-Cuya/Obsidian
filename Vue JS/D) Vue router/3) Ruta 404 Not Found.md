Es necesario poder mostrar un mensaje de error al colocar una ruta incorrecta o inexistente. Por ese motivo, para hacer esto se creará un componente que lo muestre.

Se crear el componente "NotFound" y se agrega sus datos al array de rutas. Se usara una expresion regular en el **path** para especificar que cualquier cosa que se escriba que no se identifique, mostrar el "NotFound".

Veamos un ejemplo:

```Javascript
import NotFound from "@/views/NotFound.vue";
const routes = [
  {
    path: '/:pathMatch(.*)',
    name: "NotFound",
    component: NotFound
  }
];
```

Resultado:
![[not_found.png]]