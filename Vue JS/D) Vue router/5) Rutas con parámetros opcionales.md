En caso no sea necesario enviar una variable por la URL se puede indicar que el valor será opcional.

Veamos un ejemplo:

```Javascript
const routes = [
  {
    path: "/users/:userId?",
    name: "Users",
    component: Users
  }
];
```

El signo de interrogación de cierre indica que la variable será opcional.