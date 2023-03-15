Una forma amigable de recibir parámetros de la URL es mediante el uso de props. Para ello, es necesario agregar la propiedad **props**, en el objeto rutas, y darle como valor "true". Ahora cualquier información que se pase por la ruta será enviada a la vista mediante un props.

Veamos:

```Javascript
{
	path: "/users/:userId?",
    name: "Users",
    component: Users,
    props: true,
}
```

En el componente/vista, en la sección scripts, se agregará la propiedad "props", este recibirá un array. Solo hay que agregar el nombre de la variable que va a recibir.

```Javascript
<script>
export default {
    props:['userId'],
}
</script>
```

Finalmente, para usarlo, solo es agregar las llaves de interpolación e ingresar el nombre de la variable.

```HTML
<div v-if="$route.params.userId">
        <h1>Aquí podras ver el detalle de usuario con id: {{userId }}</h1>
</div>
```
