Son como un control de versiones a la base de datos que permite a su equipo definir y compartir el esquema de la base de datos. De esta manera cualquier cambio realizado por usted o alguien con el que comparta la BD podrá actualizarla con los cambios correspondientes, así también, se podrá retroceder a un estado anterior.

### Ejecutar migraciones
Al realizar tus [[Comandos#Migraciones]], las tablas se crearán en la BD y además se creará una extra en donde cada migración que se realice estará registrada. Cada registro pertenecerá a un lote de migraciones (grupo de migraciones realizadas en diferentes periodos).
### up
Este método se ejecuta al realizar lar migraciones y es donde se crearan las tablas.
```PHP
public function up() {
	Schema
	.
	.
	.
}
```
### Schema
Esta clase permite crear y manipular tablas en la BD.
### Creación de una tabla
Para crear una tabla se utiliza la clase ==Schema== junto a el método ==create==. Éste recibirá como primer argumento el nombre de la tabla y como segundo una función anónima, la cual tendrá como argumento un objeto de tipo "Blueprint", que servirá para definir la nueva tabla con la que agregaremos las columnas o campos.

Veamos un ejemplo:
```PHP
Schema::create('user', function(Blueprint $table) {
	$table -> id();
	$table -> string('name');
	$table -> string('email') -> unique();
	$table -> timestamp('email_verified_at') -> nullable();
	$table -> string('password');
	$table -> rememberToken();
	$table -> timestamps();
});
```
Analisemos cada campo que se crea.
#### id
```PHP
$table -> id();
```
Internamente al crear el campo id se le está dando el valor de "Integer", "Unsigned" (sin signo) e "Increment".
#### string
```PHP
$table -> string('email') -> unique();
```
Al utilizar el método "string" se está creando un campo de tipo varchar de 255 caracteres, si deseas cambiar el valor, agrega un segundo argumento indicando el número de caracteres (sin agregar comillas).

###### Nota (unique)
El método "unique" indica que las ocurrencias del campo deben ser unicas.
#### timestamp
```PHP
$table -> timestamp('email_verified_at') -> nullable();
```
Este método crea un campo de tipo timestamp el cual se utiliza para guardar fechas.
###### Nota (nullable)
Este método permite que el campo tenga valores null.
#### rememberToken
```PHP
$table -> rememberToken();
```
Este método crea una columna de tipo varchar de 100 caracteres. Se crea con la finalidad de que se registre el token cada vez que el usuario inicie sesión.
#### timestamps
```PHP
$table -> timestamps();
```
Crea 2 campos: creat_at y update_at. 
El campo creat_at guardará la fecha de creación de algún dato.
El campo update_at guardará la fecha de cada modificación realizada.
### down
Este método elimina las tablas.
```PHP
public function down() {
	Schema::dropIfExist('users');
}
```
### Agregar campo a una tabla
Se debe crear una migración y nombrarla siguiendo una convención. 

Ver la siguiente demostración: [[Comandos#Agregar un campo a una tabla|Agregar un campo a una tabla]]

En el método "up" estará la clase ==Schema==, donde se usará el método ==table== para agregar el campo.

Veamos un ejemplo:
```PHP
public function up() {
	Schema::table('user', function(Blueprint $table){
		$table -> string('avatar') -> nullable() -> after('email');
	});
}
```
En el método "down" debes colocar el estado anterior del campo en caso quieras revertir los cambios.
```PHP
public function down() {
	Schema::table('user', function(Blueprint $table){
		$table -> dropColumn('avatar');
	});
}
```
En este caso, eliminar el campo, ya que antes no existia.
### Modificar campo de una tabla
Se debe crear una migración y nombrarla siguiendo una convención.

Ver la siguiente demostración: [[Comandos#Modificar un campo de una tabla]]

En el método "up" estará la clase ==Schema==, donde se usará el método ==table== para modificar el campo.

Veamos un ejemplo:
```PHP
public function up() {
	Schema::table('user', function(Blueprint $table){
		$table -> string('name', 150) -> nullable() -> change();
	});
}
```
En el método "down" debes colocar el estado anterior del campo en caso quieras revertir los cambios.
```PHP
public function down() {
	Schema::table('user', function(Blueprint $table){
		$table -> string('name', 255) -> nullable(false) -> change();
	});
}
```