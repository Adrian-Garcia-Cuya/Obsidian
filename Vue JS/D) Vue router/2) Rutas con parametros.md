Pasar parametros en la url te permite recuperar los datos de una BD, por ejemplo, y asi poder mostrar cierto contenido.

# Definir parametro
Para enviar una variable por la ruta simplemente se coloca unos 2 puntos antes del nombre de la variable. Esto se realiza al definir la ruta para un componente.

Veamos un ejemplo:
```Javascript
import Post from "@/views/MyPost.vue";
const routes = [
	}
	    path: "/blog/:post",
	    name: "Post",
	    component: Post
	}
];
```

Como se puede observar se tiene la ruta "blog" y luego tenemos la variable "post", lo identificamos por los ":".

# Recibir una variable en un componente
En el componente, en la sección "template" se mostrará el valor enviado por la URL. Se abrirán 2 llaves y se usarán el diccionario "$route.params", el cual contiene todos los parámetros, y seguido, el nombre de la variable definida en el **path**.

Veamos un ejemplo:
```HTML
<template>
    <h1>Bienvenido al post: {{ $route.params.post }}</h1>
</template>
```

Luego de params se indica el nombre de la variable.

# Pasar más de un parámetro
Solo se debe agregar una variable más a la ruta como ya se vio.
```Javascript
const routes = [
  {
	   path: "/user/:user/post/:post",
	   name: "UserPost",
	   component: UserPost
	}

];
```

Se está enviando el nombre de usuario y el post/id.

# Ver los parametros almacenados
Como se mencionó anteriormente los parametros se almacenan en "params". Si se desea mostrar los valores solo hay que mostrar el "params" el cual contine en un objeto los valores de los parametros.

```Javascript
export default {
    mounted(){//este método se verá más adelante
        console.log(this.$route.params);
    }
}
```
