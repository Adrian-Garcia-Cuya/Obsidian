## Creando objeto anonimos
Los objetos anonimos son estructuras de datos completas que no requieren una clase para instanciarse.

Para crear un objeto anonimo se debe tomar en cuenta lo siguiente, cualquier variable en __c#__ debe estar definida por un tipo de dato, por lo tanto, cuando se intente agregar un tipo de dato como: int, char, string, etc, mandara un mensaje de error. Esto se debe por que son estructuras de datos simples incorporadas en el lenguaje. Para ello se puede usar un comodin o truco usando la palabra reservada ==var==. Esta palabra hara que el lenguaje infiera el tipo de dato de la variable segun el valor asignado a este, entonces, se puede usar para crear un objeto anonimo y asi hacer que el lenguaje infiera de que es un __tipo de dato complejo__ (asi como un objeto de una clase, array, etc).

## Namespaces
Los *namespaces* son espacios de nombre donde se ubican los archivos de nuestro proyecto.
No se pueden tener clases en el mismo *namespace* pero sin en diferentes. Un *namespace* en c# puede verse como el espacio de trabajo en un proyecto.

## Using
Permite utilizar las clases de otros *namespaces*.

## Conversiones
permiten cambiar el tipo de dato de una variable. Existen 2 tipos:
 - **Conversion explicita:** ocurre cuando se realiza el cambio del tipo de dato.
```c#
 double temperatura = 34.5
 int temperaturaMadrid;
 temperaturaMadrid = (int) temperatura;
```
- **Conversion implicita:** ocurre cuando se quiere cambiar solo el alcance de tipo de dato. Por ejemplo, *int* y *long* son tipos de datos que adminten valores numericos enteros, la unica diferencia es el alcance de almacenamiento de cada uno.
```c#
int habitantesCiudad = 1000000;
long habitantesMundo = habitantesCiudad;
```
- **Conversion de texto a numero:**
```c#
string edad = "38";
int numeroEdad = int.Parse(edad);
```

## El metodo "main" 
Es el metodo de entrada de todas las aplicaciones en c#. Es decir, es el primer metodo que se ejecuta, siempre. Este es estatico debido a que cuando se inicia/ejecuta la aplicacion no hay instancias de ninguna clase por lo que necesariamente debe ser estatico para llamarlo sin realizar ninguna instancia.

## Sobrecarga de metodos
Permite definir múltiples métodos con el mismo nombre en una clase.

Para poder realizar la sobrecarga de metodo hay 2 condiciones que se deben cumplir, muy aparte de que el metodo tenga el mismo nombre de uno ya existente.

- Los metodos deben recibir diferentes *tipos* de parametos.
- Los metodos deben recibir diferentes cantidades de parametros.

# POO
## Clases
Son modelos/moldes donde se definen un grupo de caracteristicas y comportamientos de una entidad.
## Objetos
Son instancias de una clase, la cual, agrupa datos (atributos) y comportamientos (metodos).
## Encapsulacion
Consiste en restringir el acceso a los componententes (atributos y metodos) de un objeto.

## Convenciones
Las variables que tengan el modificador de acceso en **Public** deben tener la notacion **PascalCase**.

## Sobrecarga de constructores
Es el mismo concepto de sobrecarga. La diferencia, es que, aqui se da la sobrecarga cuando se requiere que el objeto tenga diferentes estados iniciales (inicializacion). Para ello, el constructor debe recibir diferente cantidad de parametros.

## this
Hace referencia al objeto actual/a la variable de clase. Por ejemplo, cuando un objeto utilice un metodo de la clase, sabra que valores son propios del objeto apartir del 'this' y cuales son recibidos por parametro o o si son creados localmente.

## Variables y metodos estaticos
En POO, normalmente se crea una copia del atributo para cada instancia que sea haga de la clase. Cuando una atributo es estatico, esta se comparte con todos los objetos, ningun objeto tiene propiamente ese atributo. Por esto mismo, se les considera variables/atributos de clase.

Este mismo concepto se aplica para los conceptos.

Algo a mencionar, todas las constantes en c# son consideradas *staticas*.

## Clases anonimas
Las clases anonimas son clases sin nombre.

Se define de la siguiente manera:
```C#
//instanciando clase anonima
var miVariable = new { Nombre = "Alberto", Edad = 19 };
```

El compilador determina el tipo de dato para las propiedades.

Se puede crear objetos de la misma clase anonima y esto va en funcion de la cantidad, del tipo y orden de las propiedades. De esta manera, se puede deducir su pertenecen a la misma clase o no.

```C#
var miVariable = new { Nombre = "Alberto", Edad = 19 };

var miOtraVariable = new { Nombre = "Ana", Edad = 16 };
```

Caracteristicas
- Son atributos publicos.
- Todos los atributos deben estar iniciados.
- Los atributos no pueden ser *static*.
- No se pueden definir metodos.