# Qué es Vue router
Esta biblioteca es un enrutador oficial de Vue js. Permite crear y gestionar rutas en la página.

Esta herramienta permite crear aplicaciones de una sola página (**S**ingle **P**age **A**pplications **SPA**)

Lo que hace este ``SPA`` es no recargar la página, sino que renderiza la página actual y reemplaza un contenido con otro.

# Creación de carpetas luego de la installación
Una vez intalado la biblioteca se debe crear 2 carpetas en ``src``: router y views.

![[instalacion_router.png]]

Dentro de router estará un archivo "index.js", donde se indicará que información se quiere mostrar al presionar en un enlace.

![[index_js.png]]

En la carpeta View irán los componentes que funcionan como vista.
![[view.png]]

# Conceptos básicos de Vue Router
Dentro del archivo **index.js** se tiene un array de objetos llamado ``routes`` en donde cada objeto tendra como propiedad:
- path: aqui irá la ruta URL.
- name: un posible nombre de ruta.
- component: el componente que se quiere renderizar cuando se va a una determinada ruta.

Veamos un ejemplo:

```Javascript
const routes = [
  {
    path: "/",
    name: "Home",
    component: HomeView,
  },
  {
    path: "/about",
    name: "About",
    component: AboutView,
  },
];
```

# Renderizar componentes que funcionan como vista

## Router-view
Este componente sirve para indicar donde quieres que vaya tu componente/vista

## Router-link
Este componente se usa para crear los enlaces de las diferentes páginas de componentes.

Vemos un ejemplo:
```HTML
<template>
  <div id="app"></div>
  <img alt="Vue logo" src="./assets/logo.png">

  <router-link to="/">Home</router-link> | //los enlaces que mostraran determinados componentes.
  <router-link to="/about">About</router-link>

  <CounterNumber></CounterNumber>

  <router-view /> //especificamos donde se mostrarán los componentes.

</template>
```
