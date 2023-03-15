Se puede utilizar cuando se quiere mostrar un sub-menu con información del usuario o de cursos a los que está inscrito, por ejemplo.

# Uso de rutas anidadas
Para este ejemplo se copiará la estructura del "div" que se tiene en el componente padre en el componente/vista "UsersView".

```HTML
<div id="app">
        <router-link :to="'/users/'+$route.params.userId">Index</router-link> |
        <router-link :to="'/users/'+$route.params.userId+'/profile'">Perfil</router-link> |
        <router-link :to="'/users/'+$route.params.userId+'/courses'">Cursos</router-link>  
</div>
```

Para usar la rutas anidadas, en el objeto de la ruta, se debe usar la propiedad **children**. Este recibirá un array de objetos, con las rutas y nombres de los componentes.

Veamos:
```Javascript
{
    path: "/users/:userId?",
    name: "Users",
    component: Users,
    children: [
      {
        path: '',
        component: Index
      },
      {
        path: 'profile',
        component: Profile
      },
      {
        path: 'courses',
        component: Courses
      },
    ]
  },
```

## LLamado de rutas hijas
Las rutas hijas toman la ruta principal y se acoplan a esta. Es decir, solo se agregan al final de la ruta principal.

Veamos un ejemplo:

Se tiene la ruta ``/users/:userId?`` y se quiere acceder a la ruta ``profile``. Al momento de dar la ruta al enlace se debe dar la siguiente: ``/users/'valorId'/profile``. De esta forma indicar que quieres entrar a la ruta hija de la ruta principal.

###### Nota
si se quiere mostrar un contenido base, no se agrega alguna ruta al path hijo, solo el componente.

```Javascript
{
    path: '',
	component: Index
}
```

# Mostrar los componentes/vistas
Luego de ingresar el enlace de la ruta del componente/vista correctamente, podemos especificar donde se quiere mostrar.

Al igual que en el menú, en el sub-menu se especificará utilizando el componente "router-view", fuera del "div".

```HTML
<template >
    <div v-if="$route.params.userId">
        <h1>Aquí podras ver el detalle de un usuario</h1>
    </div>
    <div v-else>
        <h1>Aquí podrás ver la lista de usuarios</h1>
    </div>

    <div id="app">
        <!-- <HelloWorld msg="Bienvenido al curso de Vue de Javascript"/> -->
        <router-link :to="'/users/'+$route.params.userId">Index</router-link> |
        <router-link :to="'/users/'+$route.params.userId+'/profile'">Perfil</router-link> |
        <router-link :to="'/users/'+$route.params.userId+'/courses'">Cursos</router-link>  
  </div>


  <router-view />
</template>
```