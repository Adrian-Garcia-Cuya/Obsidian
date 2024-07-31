Estas directivas permiten tener estructuras de control en el html y mostrar contenido dependiento del resultado de la condición.

Al usarlas puedes pasar como valor una operacion o una propiedad, que es lo recomentable y es como se realizará en los ejemplos.

# v-if
```HTML
<p v-if="active">Hola, esto se motrará en caso sea verdad</p>
```
# v-else
```HTML
<p v-else>Hola, esto se motrará en caso sea falso</p>
```
# v-if-else
Esta directiva se ejecuta en caso no se cumpla una condición y se quiera comprobar otra.
```HTML
<p v-else-if="active">Hola, esto se motrará en caso sea verdad</p>
```
# v-show
```HTML
<p v-show="active">Hola, esto se motrará en caso sea verdad</p>
```

###### nota (directivas de control)
Al usar estas directivas, cuando la condición no es verdadera, las etiquetas se eliminan del DOM, pero la directiva **show**, a diferencia de estas, no se elimina del DOM simplemente se oculta. Puedes verificarlo al inspeccionar la página.