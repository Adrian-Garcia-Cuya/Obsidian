Es un motor de plantillas simple, proporcionado por Laravel.

Permite reemplazar secciones de plantillas por otro contenido, herencia de plantillas y crear plantillas base.

Para usuarla se debe apregar "blade" en el archivo.

Ejemplo:
___nombre_archivo.blade.php___
___prueba.blade.php___

## @yield
Esta directiva se usa para mostrar el contenido de una sección determinada. Por lo general, en la plantilla base.
```HTML
<title>@yield('title')</title>
```
Esta directiva puede recibir un segundo argumento que se mostrará por defecto en caso no haya algun valor en "@section"
## @section
Esta directiva define una sección de un contenido. Por lo general, en la plantilla hija.

El primer argumento identifica la sección definida en la plantilla base, y el segundo el valor la que tendrá esa sección. En caso no tenga se pondrá un valor por defecto, especificado en el ==@yiel==.
```Blade
@section('title','Home')
```
## @extends
Esta directiva permite heredar el diseño de una plantilla. Se le debe especificar como argumento donde se encuentra la plantilla.
```Blade
@extends(plantilla)
```
###### Nota (@extends - carpetas)
Al igual que en el método "view", si el archivo se encuentra una carpeta se hace la separación con un punto.

## @foreach
Esta directiva permite trabajas con la estructura de bucle php.
```HTML
@foreach ($cursos as $objeto)
	<p>This is course {{ $objeto->id }}</p>
@endforeach
```
## @csrf
Usar esta directiva cada vez que defina un formulario en su HTML. Esta proporciona un token oculto en su formulario con la finalidad de proteger y validar la solicitud.
## @method
Dado que los formularios HTML no pueden realizar solicitudes ==PUT==, deberá agregar un campo oculto para falsificar estos verbos HTTP.
```Blade
@method('PUT')
```
## @error
Esta directiva muestra un mensaje de error en caso haya un error de validación en el campo indicado. @error recibe el nombre del campo.
```HTML
@error('name')
	<small>*{{$message}}</small><br> <!--La varible $message muestra el mensaje de error-->
@enderror
```
