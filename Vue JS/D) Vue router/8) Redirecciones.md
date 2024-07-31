Las redirecciones sirven para redirigir las rutas antiguas a las nuevas.
Un ejemplo sobre esto, un usuario guarda la ruta de cierta parte de la página pero esta se cambió por otra ruta y aqui es donde entra la redirección, puesto que hara que se redirija a la nueva ruta.

# Uso de redirecciones
Tenemos 2 formas de redireccionar. Una es especificando la ruta y otro es por su nombre, que es la más recomendable.

Veamos un ejemplo: 

```Javascript
 {
    path: '/blog',
    redirect: '/post',
  },
  {
    path: "/post",
    name: "Blog",
    component: Blog
  },
```

El segundo objeto te muestra el blog pero su ruta se cambió por "/post" es por ello que se agrego el primero objeto. Aquí, en el path, se indica la ruta anterior, que como se puede ver, fue "/blog". Luego, la propiedad **redirect** recibe como valor la ruta a la que va a redireccionar si se intenta ingresar a la ruta antigua, en este caso /blog.

La segunda forma de hacer esto es similar.

```Javascript
 {
    path: '/blog',
    redirect: {name: 'Blog'},
  },
  {
    path: "/post",
    name: "Blog",
    component: Blog
  },
```

Los unico que cambia es que ahora redirec recibe un objeto y este tiene como propiedad "name" y este recibe el nombre de la ruta a la que va a redireccionar.