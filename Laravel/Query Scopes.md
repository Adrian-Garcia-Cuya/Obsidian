Los query scopes son metodos en los modelos que nos permiten definir ambitos o restricciones en las consultas que deseamos hacer y poder utilizarlas en cualquier parte de la aplicacion.

# Ambitos
Los ambitos se refiere a los diferentes lugares de la aplicacion donde se requiera realizar un consulta, ya sean similares o identicas.

# Restricciones
Las restricciones son las clausulas (son filtros) que se utilizaran para realizar una consulta especifica.

# Tipos de ambitos

## Global scope
Los scopes globales son aquellos que se aplican a *todas las consultas del modelo en cuestión*. Es decir, cualquier consulta que hagas, tendrá la clausula que determines en tu scope global.

Veamos un ejemplo:

```PHP
class Post extends Model { 
	protected static function booted() 
	{ 
		static::addGlobalScope('published', function (Builder $builder) { $builder->where('published', true); 
		}); 
	} 
}
```
## Local scope
Los scopes locales son aquellos que se aplican solo en las consultas donde son invocados del modelo en cuestión.

Vemos un ejemplo:

```PHP
class Post extends Model { 

	public function scopePublished($query) 
	{ 
		return $query->where('published', true); 
	} 
}
```
Se esta creando el scope local llamado *scopePublished* que recibe como parámetro una inyección del objeto "QueryBuilder" que va a representar la consulta que se va a realizar y permitira utilizar sus métodos.

En este caso no es necesario especificar de que clase es el objeto que se está inyectando. Ver: [[Conceptos#Importante]].

## Construccion api

Se explicara lo que se esta realizando en este bloque de codigo

1.  Se esta creando el atributo '$allowIncluded' el cual tendra un array con los modelos relacionados al modelo category.
2.  Se crea el scope local y recibe como argumento una inyeccion de la clase Builder de eloquent.
3.  En la primera condicional se verifica que el atributo allowIncluded este inicicializado, es decir tenga algun valor o que el parametro que recibe request tenga algun valor (request representa la solicitud HTTP entrante y proporciona acceso a toda la información de la solicitud, incluidos los parámetros).
4. En caso los 2 casos se cumplan la funcion no retorna nada.
5. La variable '$relations' almacenara el array devuelto por explode. Lo que hace este ultimo es tomar una cadena, separarlos y cada elemento separado almacenarlo en un array.
6. Se crea una variable llamada igual que el atributo, el cual, almacenara un objeto collection que contiene los datos del atributo $allowIncluded. Esto con la finalidad de hacer uso de un metodo de esa clase.
7. Luego se realiza un foreach el cual va a recorrer el array proporcionado desde su indice y cada elemento del array.
8. Dentro del bucle hay un if con la siguiente condicion. El metodo contains de la clase collection y lo que permite es buscar si un dato se encuentra dentro de la coleccion, en este caso $allowIcluded. Lo que va a buscar es si el valor pasado por la url se encuentra en la coleccion. Si lo encuentra retorna 'true' sino 'false'.  En caso sea falso se hace una negacion para del valor y convertirlo en 'true' asi pueda entrar a la estructura de control
9. Al no estar en la coleccion se usa la funcion unset para eliminar ese valor del array $relations.
10.  Finalmente, se usa el metodo with para cargar anticipadamente el modelo relacionado al modelo category (en este caso). Es decir, se realizan instancias de los modelos especificados y laravel los guarda en la memoria de la aplicacion. De esta manera, cuando se accede a estas relaciones posteriormente, Laravel no tiene que hacer una nueva consulta a la base de datos, sino que simplemente puede devolver las instancias ya cargadas en memoria.
```PHP
protected $allowIncluded = ['posts', 'posts.user'];

public function scopeIncluded(Builder $query)
{

	if (empty($this->allowIncluded) || empty(request('included'))) {

		return;
	}

	$relations = explode(',', request('included')); //el metodo explode separara los valores ingresados en la variable por la "," indicada y los metera en un array como string.
	
	$allowIncluded = collect($this->allowIncluded);

  

	foreach ($relations as $key => $relationship) {

		if (!$allowIncluded->contains($relationship)) {

			unset($relations[$key]);

		}
	}

	$query->with($relations);

}
```
La finalidad de este scoped es verificar que las relaciones que se van a incluir esten relacionadas con el modelo(category) y cargar las instancias del modelo relacionado(posts, posts.user) anticipadamente
#### Importante
```PHP
$category = Category::included()->findOrFail($id);
```
En este caso particular, el método `included` es un "scope" definido en el modelo `Category` que agrega una cláusula `with` a la consulta que carga relaciones anticipadamente. Esto significa que, cuando se realiza una consulta a través de `Category::included()`, cualquier instancia de `Category` recuperada de la base de datos tendrá sus relaciones cargadas anticipadamente.

#### Importante - with
Cuando solo `post` esta dentro del metodo `with` solo se cargaran las relaciones que tiene el modelo post(o sea sus instancias). Para cargar tambien la relacion con user se tendria que utilizar la sintaxis `posts.user` dentro del método `with`.

Al utilizar `posts.user` dentro del método `with`, Laravel cargará anticipadamente tanto el modelo `Post` como el modelo `User` que esta relacionado a través de la relación definida en el modelo `Post`.

Por ejemplo, tambien hay otra relacion con post que seria el modelo tags y eso tambien se podrian cargar.






