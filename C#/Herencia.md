En el contexto de la Programación Orientada a Objetos (POO), la herencia es un mecanismo que permite a una clase (llamada clase hija o subclase) reutilizar, extender y modificar el comportamiento (metodos) definido en otra clase (llamada clase padre o superclase).

Cuando se define la jerarquia de la herencia se debe consultar cuales serian las caracteristicas y comportamientos comunes. De esta manera definiran los atributos y metodos de la clase padre.

![[herencia.png]]

Un consejo para definir quien sera la clase padre es puede hacer mediante la relacion *es un*. Por ejemplo, director  *es un* jefe y jefe *es un* empleado.

# Class Object
Esta clase se le considera una *super clase*, esto debido a que cualquier clase que se cree en una aplicacion en .net siempre heredara de esta clase. Aun que no se pueda observar que se hereda de esta *super clase*, internamente se hace esta herencia.

![[Pasted image 20240524082512.png]]
Estos metodos que siempre aparecen en el intellisense de visual studio pertenecen a esa *super clase*.

# Base
La instruccion *base* llama al constructor de la clase padre. Por defecto, cuando no se tiene un constructor en la clase padre, internamente, las clases hijas tiene la instruccion *base* que llama al constructor por defecto pero cuando se define el constructor en la clase padre necesariamente se debe utilizar la instruccion *base* para su llamando.

Veamos un ejemplo:

```C#
class Mamiferos
{
	private String nombreSerVivo;

	public Mamiferos(String nombre)
	{
		this.nombreSerVivo = nombre;
	}
}

class Caballo : Mamiferos
{

	public Caballo(String nombreCaballo) : base(nombreCaballo) { }
}
```

En este ejemplo muestra la definicion de constructor en la clase *Mamifero*. Luego, la clase *Caballo* extiende/hereda de la clase *Mamifero*. Como hay definido un constructor, la clase hija necesariamente debe hacer el llamado/ejecucion del constructor de la clase padre y enviarle los parametros que solicita. Para ello, se defini el constructor de la clase hija el cual recibira una variable, despues se hace el llamado mediante la instruccion *base* a la clase padre y se envia el valor solicitado.

Se crea el constructor de la clase hija porque es necesario que esto suceda al crear una instancia de la clase. Para que de esta forma pueda inicializarce la propiedad, en este caso, *nombreSerVivo*.

# Principio de sustitucion
