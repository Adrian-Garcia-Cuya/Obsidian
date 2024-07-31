# Eliminación de cache
Cuando se modifica un archivo de configuración en laravel, por ejemplo, el archivo ".env", se debe actualizar la configuración de cache. Esto es por que laravel almacena las configuraciones en cache con el fin de evitar cargar los archivos de configuración en cada solicitud que se realice.
Importante aclarar que si se modifica y no se actualiza la caché, laravel seguirá usando la configuración anterior y los cambios no tendrán efecto.

Comando para actualizar la caché:
```PHP
php artisan config:cache
```

# Funcionamiento del Resource
Cuando quieres modificar como se va a presentar los datos en tu respuesta se puede utilizar los resource personalizados. Normalmente el metodo *first* retorna una instancia del modelo con los datos pero el metod *get* retorna una coleccion de instancias. Para estos casos se usa el metodo estatico "collection", el cual tomara la coleccion y creara una nueva pero adicionalmenete creara instancias del recurso personalizado el cual tendra como atributo los nombres de las propiedades de las instancias de los modelos, asi tambien, sus datos.

Al final, retorna una coleccion de instancias de tu recurso personalizado con los datos de las instancias de tu modelo.

```PHP
return ShoppingCartResource::collection($userCart);
```
### Formatear la respuesta
Una vez que se tiene la coleccion de instancias del recurso personalizado. Dentro de tu recurso personalizado puedes sobreescribir el metodo toArray y definir como quieres presentar los datos.

```PHP
    public function toArray($request)
    {
        return [
            'productId' => $this->product['id'],
            'name' => $this->product['name'],
            'brand' => $this->product['brand'],
            'userId' => $this->user_id
        ];
    }
```
Esto solo se puede hacer porque por cada instancia creada, se llama al metodo "toArray" (laravel internamente se encarga de hacer el llamado al metodo), el cual sobreescribimos, y por ende podemos acceder a las propiedades de la instancia del recurso personalizado.

Finalmente, retornara un array con nuestra estructura personalizada. Laravel internamente manejara estos datos retornados, los unira y generara la estructura de la respuesta en formato JSON.
```JSON
```
# Parametros por referencia

Pasar los parametros por referencia a una funcion, permite modificarla dentro de esta.

Normalmente cuando se envia un argumento a una funcion, en realidad, se crea una copia de la variable y esta es la que se recibe dentro de la funcion. Esto con la finalidad de evitar que se modifique accidentalmente o que se presenten errores debido a modificaciones inesperadas.

Veamos un ejemplo:

El siguiente codigo no afectara directamente a la variable *number*, esto debido a que se incremente a la copia de la variable que se recibe en la funcion.
```PHP
<?php

function increment($value) {
    $value += 1;
}

$number = 5;
increment($number);
echo $number; // Salida: 5
?>
```
Aqui se indica que el parametro *number* se envia por referencia, lo que permitira que cambie su valor.
```PHP
<?php

function increment(&$value) {
    $value += 1;
}

$number = 5;
increment($number);
echo $number; // Salida: 6
?>
```