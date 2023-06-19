Para que laravel sepa que archivo mostrar al momento de colocar una URL se utilizan lo que son las rutas.

Estas rutas seran incluidas en el archivo "web.php".

![[rutas.png]]

### Crear una nueva ruta

Para ello vamos a requerir lo siguiente:
```PHP
Route::get('nombre_de_la_ruta', function(){
	return "retorno de texto :D");
});
```
### Agregar variables a las rutas

Para agregar una variable a la ruta se debe de utilizar las llaves y luego pasar esa variable como parámetro a la función anónima.
```PHP
Route::get('cursos/{curso}', function($curso) {
	return "El nombre del curso es: $curso";
});
```
También es posible pasar más de una variable:
```PHP
Route::get('cursos/{curso}/{programacion}', function($curso, $programacion)) {
	return "Estas en el curso de $curso que pertenece a la categoría $programacion";
});
```
### Agregar una variable opcional a la ruta

Puedes indicar que el valor por ingresar sea opcional, solo debes agregar un signo de pregunta de cierre al final del nombre de la variable.

Después, debes inicializar la variable al momento de pasarla como parámetro en la función anónima. Esta debe ser nula, ya que, no tendrá ningún valor.

Veamos un ejemplo:
```PHP
Route::get('cursos/{curso}/{programacion?}', function($curso, $programacion = null))
```
### Especificar ruta de controladores
Para especificar los controladores que se usaran en la aplicación se utiliza la palabra reservada "use" y luego indicamos la ruta en donde se encuentra el archivo.

Veamos un ejemplo:
```PHP
use App\Http\Controllers\homeController;
```
### Utilizar controladores en las rutas
Se puede utilizar los controladores agregando el nombre de la clase y especificando el método que utilizarán para esa ruta.

Veamos un ejemplo:
```PHP
Route::get('nombre_ruta', [nombre_de_la_clase::class, 'nombre_del_método']);
```
```PHP
Route::get('cursos', [cursoController::class, 'index']);
Route::get('cursos/{curso}', [cursoController::class, 'index']);
```
#### Nota (controlador en las rutas - envio de variable)
En caso de que se esté pasando una variable por la ruta, ahora el método que está en el controlador es el que recibirá la variable.

ver [[Controlador#Ejemplo de parámetro recibido]]

#### Nota (controlador en las rutas - método por defecto)
Por defecto, la ruta busca al método [[Controlador#invoke]], por lo tanto no sería necesario agregar los corchetes y el metodo, para éste caso. Solo agregamos el nombre de la clase.

Veamos un ejemplo:
```PHP
Route::get('/', homeController::class);
```
### Grupo de rutas
Si las rutas utilizan un controlador en común, éstas se pueden agrupar. Esto ayudará a evitar que se reescriba líneas de código.

Para utilizar el grupo de rutas se debe usar el método ==controller== y ==group==. 

En el método ==controller== especificaremos el nombre del controlador que usaran todas las rutas.

En el método ==group== agruparemos todas las rutas.

Veamos un ejemplo:

```PHP
Route::controller(nombre_del_controlador) -> group(function {
	Route::get('nombre_de_la_ruta', 'nombre_del_método');
	Route::get('nombre_de_la_ruta', 'nombre_del_método');
	Route::get('nombre_de_la_ruta', 'nombre_del_método');
});
```
```PHP
Route::controller(cursoController) -> group(function {
	Route::get('cursos', 'index');
	Route::get('cursos/crear', 'create');
	Route::get('cursos/{curso}', 'show');
});
```
### Nombrar las rutas
Se puede asignar un nombre a las rutas. Esto debido a que al tener muchas vistas con los mismos enlaces cambiar cada enlace seria tedioso.

Para nombrar a una ruta usamos en método ==name== y como argumento le damos el nombre que tendrá la ruta.

Veamos un ejemplo:
```PHP
Route::get('cursos', [cursoController::class, 'index']) -> name('cursos.index');
```
### Usar nombre de rutas en la vista
Para poder usar los nombres asignados a cada ruta se debe usar en método ==route== y como argumento dar el nombre de la ruta.

Veamos un ejemplo:
```HTML
<a href="{{route('cursos.create')}}">Crear curso</a>
```
###### nota(nombre rutas vista - envio de variable)
Para enviar la variable cuando se utilizó el método ==route==, sencillamente en el segundo argumento se debe colocar la variable.
```HTML
<a href="{{route('cursos.show', $objeto->id)}}">{{$objeto->name}}</a>
```
En este caso se está pasando el id.