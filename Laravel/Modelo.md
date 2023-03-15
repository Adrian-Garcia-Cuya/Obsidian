Los ==modelos== son uno de los componentes más importantes que  interactúa con nuestra base de datos para realizar cualquier consulta SQL (CRUD). Se llamarán desde el controlador para poder realizar esas acciones.

Si no deseas seguir la convención mostrada en [[Comandos#Crear un modelo]] puedes agregar una variable protegia y darle el nombre de la tabla a la que quieres que administre eloquen.

Veamos un ejemplo:
```PHP
class Curso extends Models {
	use HasFactory;
	protected $table = "users";
}
```
#### Importante
Todos métodos que verás a continuación se usan en el controlador pero al ser métodos pertenecientes a las clases modelo, es la razón por la que los coloco aquí.
## Traer información de la BD
Los datos se obtienen utilizando el método ==all==. 
```PHP
$cursos = Curso::all();
```
El retorno es estos datos es mediante una colección(array) de objetos.

## Creación de consultas
Al momento de generar tus consultas puedes dar restricciones a estas y luego invocar al método ==get== para recuperar todas tus consultas (en colección de objetos).

Veamos un ejemplo:
```PHP
$cursos = Curso::where('category', 'Diseño web') -> get();
```
## Generador de consultas
El generado de consultas de BD de laravel proporciona una interfaz donde puedes crear y ejecutar consultas de BD.

### where()
El método ==where== permite filtrar los datos según la condición dada. Este va a recibir dos argumentos: el campo donde se encuentra el valor que buscas y el valor con el cual deseas hacer el filtro.

Por ejemplo, Si deseas que tu consulta solo te devuelva todos los cursos que tengan la categoría "Diseño web" debes realizar lo siguiente:
```PHP
$cursos = Curso::where('nombre_del_campo', 'valor_deseado_por_filtrar') -> get();
```
###### nota (where - operadores de comparación)
Con where puedes utilizar estos operadores para filtrar tus consultas.

Por ejemplo, quieres mostrar los registros con id mayores a 34.
```PHP
$cursos = Curso::where('id', '>', 34) -> get();
```
###### nota (where - like)
Esta propiedad buscará similitudes del valor que pases en todos los registros.

Veamos un ejemplo:
```PHP
$cursos = Curso::where('name', 'like', '% garcia %') -> get();
```
Esto devolvera todos los registros que tengan en el campo name "garcia". Otra punto, es que al colocar al inicio y al final los simbolos "%", ignora lo que haya antes o despues de la palabra buscada.
### orderBy()
Este método ordenará las consultas. Este recibe dos argumentos: el campo a ordenar y aquí eliges si lo ordenas de forma ascendente('asc') o descendente ('desc').

Veamos un ejemplo:
```PHP
$cursos = Curso::orderBy('id', 'desc') -> get();
```
###### nota (orderBy - por defecto)
Si el campo tiene el nombre ==id== el método ==orderBy== ordenará, por defecto, el campo de forma ascendente.
### first()
Este método retorna solo el primer objeto de la colección.
```PHP
$cursos = Curso::first();
```
### select()
Este método permite seleccionar que campos retornar. Este recibe como argumento los campos que quieras mostrar.

Veamos un ejemplo:
```PHP
$cursos = Curso::select('name','description') -> get();
```
###### nota (select - propiedad "as")
Esta propiedad ==as== permite asignarle un apodo o alias a un campo.

Veamos un ejemplo:
```PHP
$cursos = Curso::select('name as Nombre','description') -> get();
```
El retorno del campo "name" será con el alias "Nombre".
### take()
Este método permite elegir la cantidad de registros a retornar. Recibe como argumento el número de registros.
```PHP
$cursos = Curso::take(4) -> get();
```
### find()
Este método permite realizar una busqueda por id y retorna un objeto que esté relacionado al id.
```PHP
$cursos = Curso::find(4); //retorna el registro con id 4
```
### paginate()
Este método trae y muestra los datos pero paginado. Por defector, asignara 15 registros por página pero puedes indicar la cantidad de registros dando como argumento el valor deseado.
```PHP
$cursos = Curso::paginate(); //trae 15 registros
```
```PHP
$cursos = Curso::paginate(20); //trae 20 registros
```
###### nota (paginate - mostrar páginas)
Cuando se usas este método no se generan los botones para pasar de una página a otra por lo que hay que usar el método ==link== a la vista para poder ir de una página a otra.
```PHP
{{$curso -> link();}}
```
