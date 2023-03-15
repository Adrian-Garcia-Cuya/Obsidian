## invoke
Utilizamos este método cuando queremos que el controlador administre una única ruta.
Este es el primer método que busca la ruta en el controlador.
```PHP
public function __invoke() {
	return "Bienvenido a la página de inicio";
}
```
## index
Se utiliza este método para llamar a la página principal.
```PHP
public function index() {
	return "vista principal";
}
```
## create
Se utiliza este método para crear lo que quieras.
```PHP
public function create() {
	 return "vista para crear algo";
}
```
## show
Se utiliza este método para mostrar información.
```PHP
public function show() {
	return "vista para mostrar datos";
}
```
## Ejemplo de parámetro recibido
```PHP
public function show($curso) {
	return "Este es el curso de: $curso";
}
```
## Retorno de vistas
Para regresar una vista se utilizará el método ==view==. Se debe pasar como argumento el nombre del archivo que se desea mostrar y no es necesario agrega la extesión "php".

Tomar en cuenta que el método view nos úbica en la capeta view.

Veamos un ejemplo:
```PHP
public function ejemplo() {
	return view('nombre_del_archivo');
}
```
```PHP
public function ejemplo() {
	return view('home'); //Esto es equivalente a "home.php"
}
```
###### nota (retorno de vista - creación de carpeta en view)
Si se desea crear una carpeta en la ==carpeta view==, al dar su ubicación, se debe colocar un punto que separe la/s carpeta/s y el archivo.

Veamos un ejemplo:
```PHP
public function ejemplo() {
	return view('cursos.create');
}
```
###### nota (retorno de vista - envío de variable)
Una forma de enviar una variable a la vista es creando un array asociativo y lo que se enviará a la vista es la clave.

Veamos un ejemplo:
```PHP
public function ejemplo($curso) {
	return view('cursos.show', ['course' => $curso]);
}
```
Otra forma de enviar las variable es usando el método compact. Este método crea un array asociativo, donde el nombre de la variable será la clave y el contenido será su valor.

Veamos un ejemplo: 
```PHP
$estado = "casado";
$resultado = compact('estado');
print_r($resultado);
/*
(
	[estado] => [casado]
)
*/
```
Implementandolo:
```PHP 
public function ejemplo($curso) {
	return view('cursos.show', compact('curso'));
}
```
## Recibir datos de un formulario
Para obtener la información enviada de un formulario se debe definir objeto de tipo ==Request== en el parámetro del método que mostrará la información.

```PHP
public function update(Request $request) {

}
```
Al definir el tipo del parámeto, se hace una [[Conceptos#Inyección]] que recupere los datos enviados por un formulario.

## Redirección a una ruta con envío de variable
Para dirigirse a una ruta se usa el método ==redirect== y luego se usa el método ==route== para especificar la ruta.

Veamos un ejemplo:
```PHP
return redirect () -> route('cursos.show', $curso -> id);
```
Ahora, laravel entiende que quieres enviar el id del objeto por lo que puedes omitir especificarlo.
```PHP
return redirect () -> route('cursos.show', $curso);
```
## Simplificación de instaciación
Antes para mostrar los datos de la base de datos se instanciaba un objeto del modelo y se usaba el método ==find== para obtener los datos según el id, asi como puedes ver a continuación:
```PHP
public function show($id) {
	$curso = Curso::find($id);
	
	return view('cursos.show', ['course' => $curso]);
}
```
Ahora se puede simplificar toda esa parte, solo especifica en el parámetro el tipo de dato que recibirá, el cual seria un objeto de tipo del modelo, en este caso "Curso"

Veamos como quedaría:
```PHP
public function show(Curso $course) {
	
	return view('cursos.show', compact('course'));
}
```
Laravel entenderá que quieres obtener la información según el "id" que pases y traera esa información de BD.

## Validaciones
Para poder realizar validaciones en un formulario usamos el método ==validate==. Recibe como argumento un array asociativo en donde iran los nombres de los input, los cuales serán las claves, y las restricciones, que serán el valor.

Veamos un ejemplo:
```PHP
public function store(Request $request) {
	$request -> validate([
		'name' => 'required',
		'description' => 'required',
		'category' => 'required'
	]);
}
```
Si se quiere usar mas de uno usamos este simbolo ==|== despues de cada restricción.
```PHP
public function store(Request $request) {
	$request -> validate([
		'name' => 'required|max:10',
		'description' => 'required|min:10',
		'category' => 'required'
	]);
}
```
Las restricciones se leen en orden(izquierda a derecha). Cuando una de las restricciones no se cumple, se refresca la página y con la directiva [[Blade#@error]] puedo mostrar el mensaje de error correspondiente.
### old
El método ==old== mantiene lo que el usuario escribió en el formulario cuando se refresca la página. Este método se utiliza cuando se usan validaciones en el formulario.
```HTML
<input type="text" name="name" id="nombre" value="{{old('name')}}" ><br>
```
###### Nota (old - en actualizaciones de datos)
Si al editar un dato se olvidan rellenar un campo pero ya hay modificaciones, al querer actualizar se borraran las modificaciones. Para evitar eso enviamos un valor como segundo argumento al método ==old==.
```HTML
<input type="text" name="name" value="{{old('name',$course->name)}}" id="nombre"><br>
```
Al refrescar la página se mantendrá las modificaciones, en caso las hubiera.