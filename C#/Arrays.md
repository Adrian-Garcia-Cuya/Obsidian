# Arrays implicitos
Son array sin tipo de dato y sin longitud definida. Se define de la siguiente manera:

```C#
var datos = new[] {"juan", "dias", "andres"};
```

C# asume el tipo de dato del array apatir de los valores con los que se inicializa.

# Array de objetos

```C#
Empleados[] arrayEmployeed = new Empleados[2];
arrayEmployeed[0] = new Empleados("Juan", 44);
arrayEmployeed[1] = new Empleados("Leandro", 32);
```

# Arrays  anonimos
Al igual que en las clases anonimas , las propiedades de la clase anonima deben ser de los mismos tipos, siguiendo el ejemplo: "nombre" (string) y "edad" (int).
```C#
var personas = new[]
{
	new {Nombre = "juan", Edad = 19},
	new {Nombre = "Lucho", Edad = 29},
	new {Nombre = "Alex", Edad = 43}
};
```