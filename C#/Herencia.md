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

# # Principio de sustitucion liskov

## Que es?
El principio de sustitución de Liskov es uno de los cinco principios SOLID. Este principio establece que las instancias de una clase (padre) deben poder ser reemplazadas 
por instancias de sus subclases sin alterar el comportamiento del programa. En otras palabras, una clase hija debe ser capaz de implementar todos los métodos de 
la clase padre sin cambiar su comportamiento.

## Que utilidad tiene?
Aplicar este principio ayuda a garantizar una correcta aplicación de la herencia, evitando que el programa se rompa o se altere debido a una mala implementación. 
Es fundamental para mantener la coherencia y la integridad del diseño de software orientado a objetos.

Veamos un ejemplo:

```C#
public class Archivos
{
	public string Nombre {get; set}
	
	public void Escribir()
	{/*Escribo*/}
	
	public void Leer()
	{/*Leo*/}
}

public class ArchivosSoloLectura : Archivos
{
	public new void Escribir()
	{
		throw new Exception();
	}
}

public class ArchivosOcultos : Archivos
{
	public new void Leer()
	{
		throw new Exception();
	}
}
```

Se tiene la clase padre *Archivos*, la cual, cuenta con 2 metodos, *Escribir* y *Leer*. Luego se ven 2 clases *ArchivosSoloLectura* y *ArchivosOcultos* que heredan de *Archivos*. Como se puede observar cada una tiene un metodo generando un error, esto es debido a que conceptualmente no es posible *Escribir* en un *ArchivoSoloLecutra* y por tal razon se oculta el metodo de la clase padre y se usa el metodo de la clase hija para lanzar un mensaje de error. Esto mismo se aplicaria para *ArchivosOcultos*.

Claramente es una practica inadecuada que no sigue este princio.

Una forma de agregar es separando el codigo e implementado las interfaces correspondientes para cada situacion.

Veamos:

```C#
public interface Ileeible
{
	public void Leer();
}
public interface IEscribible
{
	public void Escribir();
}
public abstract class ArchivoBase
{
	public string? Nombre { get; set; }
}
public class Archivo3 : ArchivoBase, IEscribible, Ileeible
{
	public void Escribir()
	{
		//Escribo
	}

	public void Leer()
	{
		//leo
	}
}
public class ArchivosSoloLectura3 : ArchivoBase, Ileeible
{
	public void Leer()
	{
		//leo
	}
}

public class ArchivosOcultos : ArchivoBase, IEscribible
{
	public void Escribir()
	{
		//escribo
	}
}
```