En escenarios de validación más complejos se utilizan las "solicitudes de formulario". Estas son clases de solicitudes personalizadas que contienen su propia lógica de validación y autorización.

Para crear un FR puedes ver el: [[Comandos#Crear un FormRequest]]

Una vez creado la clase tendrás dos funciones: ==authorize & rules==
## Authorize
Aquí ira la lógica neceseria para verificar que el usuario tenga los permisos necesarios.

Si tiene los permisos se debe retornar ==true== sino debe retornar ==false==.
```PHP
public function authorize() {
  return true;
}
```
## rules
Aquí estarán las validaciones personalizadas.

Para que este método se ejecute, el método "Authorize" debe retornar "true".

Las validaciones irán dentro del array que se retornará.
```PHP
public function rules() {
	return [
		'name' => 'required|max:10',
		'description' => 'required|min:10',
		'category' => 'required'
    ];
}
```
También puedes cambiar el nombre de los inputs que se mostrarán al generar un error de validación. Para ello, se crea un método llamado ==attributes==.
```PHP
public function attributes() {
	return [
		'name' => 'nombre de curso'
	];
}
```
Si deseas cambiar los mensajes de error puedes hacerlo creando el método ==messages==.
```PHP
public function messages() {
	return [
		'description.required' => 'Debe ingresar una descripcion del curso'
	];
}
```
## Usar las validaciones
Ahora, para usar estas validaciones debes importar esta clase en el controlador.
```PHP
use App\Http\Requests\StoreCurso;
```
Luego, enviar como argumento un objeto de tipo StoreCurso al método (en este caso ==store==).
```PHP
public function store(StoreCurso $request) {
	//Este objeto StoreCurso obtendra los datos del formulario, al igual que el objeto Resquest, y hará las validaciones indicadas en el método.
}
```
