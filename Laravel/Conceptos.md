## ¿Qué es Laravel?
Es un framework de código abierto escrito en PHP. 

Se utiliza para crear aplicaciónes y servicios web.

Esta basado en el patrón MVC.

## Framework
Es un entorno de trabajo con código pre-escrito por una comunidad de expertos programadores.

## Utilizamos el siguiente comando para instalar Laravel:
```Git
$ composer global require laravel/installer
```
## Crear un proyecto nuevo Laravel
```Git
$ laravel new (nombre del proyecto)
```
## Namespace
Es el espacio en donde se encuentra un determinado archivo.

## env
Este archivo se insertarán los datos para conectarse a la base de datos. Esto para tener una mayor seguridad en tu proyecto, ya que, este archivo no se sube al repositorio.

## Inyección de dependencias
El hecho de recibir los objetos de los que depende una clase o método por parámetro, es lo que se conoce como inyección.

## Contenedor de servicios
Esta herramienta instancia los objetos que se deben inyectar e inyectarlos en los métodos necesarios.

Para que los intancie primero se debe indicar la clase la cual hará una instancia.

Veamos un ejemplo:
```PHP
use Illuminate\Http\Request;
```
De esta manera se obtiene una instancia de la solicitud HTTP en el ==contenedor de servicios== y este se encargara de realizar la inyección cuando la clase o el método lo requiera.

#### Importante
Hay casos que puede ser necesario especificar la clase del objeto que se está inyectando como dependencia en el método, pero en el caso de los "Query Scopes" de Laravel, Laravel se encarga de inyectar automáticamente el objeto QueryBuilder en el método, por lo que no es necesario especificar la clase del objeto en la definición del método.
### Inyección
El "contenedor de servicios" hará una inyección cuando, el método o clase, al recibir sus parámetros definan el tipo de dato.

Veamos un ejemplo:
```PHP
public function update(Request $request) {
	return $request;
}
```
Al retornar la variable $request veremos toda la información enviada por el método post.

## Cambiar nombres visualmente de los inputs al mostrar un mensaje de error
Para cambiar el nombre de los inputs al mostrar el error, ya sea, que están en inglés o "x" razones, se debe ir al archivo "validation.php" que está ubicado en la capeta "lang".
![[lang_validation.png]]
Luego, dirigirse al final del archivo, ahí encontrarás la variable "attributes". Aquí reemplazaras el nombre de los inputs con el nombre que quieres que aparezca.

Los nombres de los inputs, serán las claves y el valor, el nombre por los que quieras cambiar.
```PHP
'attributes' => [
	'name' => 'nombre'
],
```
Resultado:
![[resultado_cambio_input.png]]