## Consola Artisan
Artisan es la interfaz de lineas de comando que viene con Laravel. Proporciona una serie de comandos que ayudará en el desarrollo de las aplicaciones web.

Para ver la lista de todos los comandos artisan use este comando:
```Git
php artisan list
```
## Creación de clases
Para poder crear nuevas clases con la estructura necesaria para que sea funcional en Laravel, se utiliza el siguiente comando:
```Git
php artisan make
```
### Crear un controlador
Para crear una controlador se utliza el siguiente comando:
```Git
php artisan make:controller (nombre_del_controlador)
```
Es buena práctica agregar ==controller== al final del nombre del controlador.
```Git
php artisan make:controller HomeController
```
### Crear una migración
Para crear una migración se utliza el siguiente comando:
```Git
php artisan make:migration (nombre_de_la_migracion)
```
Es buena práctica agregar un "create" al inicio y un "table" al final del nombre.
```Git
php artisan make:migration create_cursos_table
```
### Crear un modelo
Para crear un modelo se utiliza el siguiente comando:
```Git
php artisan make:model (nombre_del_modelo)
```
La convención que  se le da al nombre para el modelo es un poco diferente. Si nombras tus modelos en inglés, eloquent entendera que quieres administrar la tabla con el mismo nombre pero en plural (sigue la gramática inglesa). Es decir:
```Git 
php artisan make:model Category
```
Eloquent entenderá que quieres administrar la tabla ==categories==.

Por otro lado, si nombras tus modelos en español simplemente agregará una "s". Tener cuidado con esto. 
```Git
php artisan make:model nivel
```
Eloquent entenderá que quieres administrar la tabla nivel==s==.
### Crear un seeder
Para crear un seeder se utiliza el siguiente comando:
```Git
php artisan make:seeder (nombre_del_seeder)
```
Es buena práctica agregar ==seeder== al final del nombre del seeder.
```Git
php artisan make:seeder CursoSeeder
```
### Crear un factory
Para crear un factory se utiliza el siguiente comando:
```Git
php artisan make:factory (nombre_del_factory)
```
Es buena práctica agregar ==factory== al final del nombre del factory.
```Git
php artisan make:factory CursoFactory --model=Curso
```
#### Importante
La primera parte del nombre del factory (Curso) debe ser igual al nombre del modelo(Curso). Esto es porque si la primera parte es diferente, laravel no encontrará el factory a ejecutar para ese modelo.
### Crear un FormRequest
Para crear un FormRequest se utiliza el siguiente comando:
```Git
php artisan make:request (nombre_del_FR)
```
Es buena práctica nombrarlo con el nombre del método y del controlador en donde se quiere hacer la validación.
```Git
php artisan make:request StoreCurso
```
## Migraciones
Para migrar tus migraciones a la base de datos se utiliza el siguiente comando:
```Git
php artisan migrate
```
### Estado de migraciones
Para ver las migraciones que se han ejecutado hasta el momento, se utiliza el siguiente comando artisan:
```Git
php artisan migrate:status
```
### Revertir migraciones
Para revertir la última migración se utiliza el comando ==rollback==. Este comando revierte el último lote de migraciones.
```Git
php artisan migrate:rollback
```
#### Revertir una cantidad determinada
Se puede revertir un número específico de migraciones usando la opción ==step== del comando ==rollback== 

Veamos un ejemplo:
```Git
php artian migrate:rollback --step=5
```
Esto revertirá las últimas 5 migraciones.
#### Revertir y migrar
El comando "migrate:refresh" revertirá todas sus migraciones y luego ejecutará el comando "migrate".
```Git
php artisan migrate:refresh
```
###### nota (revertir y migrar - down)
Este comando ejecuta el método ==down== que se encuenta en los archivos de migraciones. Si se llega a escribir mal el nombre de la tabla o metodo, no se eliminará.

Lo mismo sucede con el rollback.
### Eliminar tablas y migrar
El comando "migrate:fresh" aliminará todas tus tablas de la BD y luego ejecutará el comando "migrate".
```Git
php artisan migrate:fresh
```
### Agregar un campo a una tabla
Se utiliza el mismo comando para crear una migración pero el nombramiento tiene otra convención.

Veamos un ejemplo:
```Git
php artisan add_(nombre campo agregar)_to_(nombre tabla modificar)_table
```
```Git
php artisan add_avatar_to_users_table
```
Esto generará la estructura para agregar el campo.
### Modificar un campo de una tabla
Primero se debe instalar una dependencia para poder modificar una columna.
```Git
composer require doctrine/dbal
```
Luego, se utiliza el mismo comando para crear una migración pero el nombramiento tiene otra convención.
```Git
php artisan make:migration update_(nombre campo modificar)_property_to_(nombre tabla modificar)_table
```
```Git
php artisan make:migration update_name_property_to_users_table
```
El nombre "property" no es necesario colocarlo, es una sugerencia al cambio de una propiedad del campo.