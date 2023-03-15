Es buena practica llamar a las rutas por sus nombres debido a que si en algún momento se decide cambiar las rutas los nombres apuntaran a esa ruta a si la cambies.

# Uso de nombres de las rutas
Al momento de querer usar lo nombres de las rutas se necesita usar la directiva "v-bind" y luego agregar la propiedad name, que es donde irá el nombre de la ruta.

Veamos un ejemplo:
```HTML
<div id="app">
    <img alt="Vue logo" src="./assets/logo.png">

    <router-link :to="{name: 'Home'}">Home</router-link> |
    <router-link :to="{name: 'About'}">About</router-link> |
    <router-link :to="{name: 'Blog'}">Blog</router-link>
    <CounterNumber></CounterNumber>
    
  </div>
```

# Usar los nombres de rutas con parámetros

En este caso veremos un ejemplo con rutas anidadas pero funciona de la misma forma si fuera una ruta normal.

Primero se definen los nombres para las rutas hijas. Luego, al igual que hace un momento, es necesario agregar la directiva "v-bind" pero aqui se pasarán 2 propiedades: **name** y **params**. Este último recibirá los parametros que se envíen en la url.

**Params** es una propiedad que se le asigna un objeto y aqui estarán las propiedades con los valores de los parámetros.

Veamos: 
```HTML
<div id="app">
        <router-link :to="{name: 'UserIndex', params: {userId:$route.params.userId}}">Index</router-link> |
        <router-link :to="{name: 'UserProfile', params: {userId:$route.params.userId}}">Perfil</router-link> |
        <router-link :to="{name: 'UserCourses', params: {userId:$route.params.userId}}">Cursos</router-link>  
  </div>
```
