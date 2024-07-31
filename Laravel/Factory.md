Este componente permite llenar la base de datos con datos de prueba.
A diferencia de los seeders, los factorys llenarán los datos por nosotros y no estaremos llenando registro por registro.

Primero que nada, se debe indicar el modelo al que estará relacionado el factory.
```PHP
use App\Models\Curso
```
Luego, se crea un atributo "model" que almacenará el modelo correspondiente.
```PHP
protected $model = Curso::class;
```
Puedes seguir la convención en caso no quieras especificar manualmente el modelo que usara un factory. 

Ver: [[Comandos#Crear un factory]].
## Agregando datos falsos
Para agregar datos se deben especificar todos los campos de tu tabla en el "return" del método ==definition==
```PHP
public function definition() {
	return [
		'name' => $this -> faker -> sentence(),
		'description' -> $this -> faker -> paragraph(),
		'category' => $this -> faker -> randomElement(['diseño ux','diseño ui'])
	]
}
```
Luego, utilizamos faker para generar estos datos de falsos y despues colocamos el método correspondiente.
###### sentence()
Genera una oración.
###### paragraph()
Gernera un párrafo.
###### randomElement()
Inserta, de manera aleatoria, los datos ingresados.

## Ejecutar factory
Para ejecutar los factories, se realiza desde el seeder por defecto (es lo que recomienda laravel).

![[Ejecucion_factory.png]]

Veamos un ejemplo:
```PHP
use App\Models\Curso; //importar el modelo para poder interactuar con la base de datos, y asi poder insertar los datos falsos generados.
```
```PHP
public function run() {
	Curso::factory(50) -> create(); //el valor en el método factoria son las cantidad de filas que deseas generar
}
```
Finalmente, ejecutas el comando [[Seeders#nota (seeders - comando)]] para insertar los datos falsos a la BD.