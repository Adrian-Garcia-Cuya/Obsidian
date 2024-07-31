Los seeders es un componente de laravel que sirven para inicializar las tablas con datos.

Antes que nada, se debe indicar la ruta del modelo para que se pueda utilizar su clase.

```PHP
use App\Models\Cursos
```
## Inserción de datos de prueba
Para usar poder insertar datos a la tabla solo es necesario crear un objeto con sus respectivas propiedades.
```PHP
$curso = new Curso;
$curso -> name = "Framework Laravel";
$curso -> description = "Laravel es lo mejor que pudo crear el mundo";
```
Luego, si se desea enviar esa información a la BD se agrega lo siguiente:
```PHP
$curso -> save();
```
Cada que se inserte un dato por primera vez se le asignará un id (en caso sea auto-incrementable), y cuando se quiera modificar solo se debe realizar lo mismo de arriba, ya que, ese objeto ahora tendrá el id.
```PHP
$curso -> name = "Laravel 9";

$curso -> save();
```
## Ejecución del seeder
Finalmente, para que las tablas tengan estos valores se debes realizar el siguiente comando, en caso ya migraras:
```Git
php artisan migrate:fresh 
```
y luego con este comando ejecuta el seeder por defecto:
```Git
php artisan db:seed
```
Es buena práctica tener separado tus datos de prueba en un seeder aparte, ya que, estos se incrementaran demasiado.
###### nota (seeders - comando)
Existe un comando que unen los dos anteriores:
```Git
php artisan migrate:fresh --seed
```
También existe un comando en caso todavía no migres tus tablas:
```Git
php artisan migrate --seed
```

## LLamado de seeders
Para llamar un seeder creado por ti se utiliza el método ==call== y como argumento debes pasar el nombre del seeder que creaste. Este se debe usar en el método "run", que está en el seeder por defecto.

Veamos un ejemplo:
```PHP
public function run() {
	$this -> call(nombre_del_seeder);
}
```
```PHP
public function run() {
	$this -> call(cursoSeeder::class);
}
```
