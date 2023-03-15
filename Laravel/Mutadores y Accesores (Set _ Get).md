## Accesor (get)
Los accesores permiten acceder y mostrar los atributos. Para ello se pasa el valor del atributo.
```PHP
get: fn($value) => ucwords($value)
```
El accesor modificará el valor del atributo pero será meramente visual. En este caso al pedir ver el atributo, antes de mostrarlo, el accesor tomará ese valor y usará el método ==ucwords==.
## Mutador (set)
Los mutadores permiten modificar los atributos. Para ello se pasa el valor del atributo.
```PHP
set: fn($value) => strtolower($value)
```
En este caso, modifica el valor a minúscula toda la palabra y lo almacena en la BD.
## Creación de mutador y accesor
Para crear los mutadores y accesores se crea un método protegido en el modelo, el cual, tendrá como nombre el atributo que se quiere modificar.

Veamos un ejemplo:
```PHP
protected function name(): Attribute { //retorna una instancia de clase 
	return new Attribute(
		//funciones flecha
		get: fn($value) => ucwords($value),//convierte la primera letra de las palabras en mayúscula.
		set: fn($value) => strtolower($value)//convierte las palabras en minúscula.
	);
}
```