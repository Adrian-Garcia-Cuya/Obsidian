Las excepciones son errores que surgen en el momento de ejecucion del programa que escapan al control del programador.

Cuando se quiera utilizar una excepcion generica (Exception ex) se puede omitir colocarlo en el catch.
```C#

try
{
	minumero = int.Parse(Console.ReadLine());
}
catch
{
	Console.WriteLine("No has introducido un valor numerico valido");
	minumero = 0;
}
```

# Lanzamiento de excepciones especificas
Cuando se requiera utilizar una clase de excepcion especifica se puede realizar de la siguiente manera:
```C#
throw new ArgumentOutOfRangeException();
```
La palabra reservada *throw* permite lanzar excepciones.
# Excepciones con filtros
Cuando se requiera manejar una excepcion en especifico sin contar todas las que se pueden generar en la aplicacion podemos realizar lo siguiente:
```C#
try
{
    minumero = int.Parse(Console.ReadLine());
}// capturamos una excepcion en especifico o generica
catch (Exception ex) when (ex.GetType()!=typeof(FormatException)) //GetType(retorna la excepcion generada)
{
    Console.WriteLine("No has introducido un valor numerico valido " +ex);
    minumero = 0;
}
catch (FormatException ex)
{
    Console.WriteLine("Has introducido texto");
    minumero = 0;
}
```
Como se puede observar se utiliza la clausula *when* la cual nos va a permitir poder *filtrar* las excepciones. En este caso se quiere manejar todas exceptuando **FormatException** porque se manejara de forma independiente.

# Finally
**Finally** es un bloque unido al **try catch**, el cual siempre va al final y siempre se ejecuta.

Normalmente se utiliza cuando se requiere que algo siempre se ejecute, asi el programa pueda realizar la accion u ocurra una excepcion. Por ejemplo, conexiones a base de datos y lectura de ficheros de la computadora requiere cierta conexion, la cual consume recursos del equipo, por lo tanto, asi se de bien o mal la conexion esta debe cerrarse para que no siga consumiendo recursos.

Ejemplo de uso:
```C#
System.IO.StreamReader archivo = null;

try
{
    string linea;

    int contador = 0;

    string path = @"C:\Users\user\Desktop\test.txt";

    archivo = new System.IO.StreamReader(path);

    while ((linea = archivo.ReadLine()) != null)
    {
        Console.WriteLine(linea);

        contador++;
    }

}catch (Exception e)
{
    Console.WriteLine("Error con la lectura del archivo");
}
finally
{
    if(archivo != null) archivo.Close();

    Console.WriteLine("Conexion con el fichero cerrada");
}
```
# Checked
Verifica rigurosamente cada una de las variables dentro de su bloque con la finalidad de encontrar si hay una desbordamiento en una de ellas. Si es el caso, generara una excepcion.

Ejemplo:
```C#
checked
{
	int numero = int.MaxValue;

	int resultado = numero + 20;

	Console.WriteLine(resultado);
}
```

Tambien se puede usar el **checked** para una variable en especifico de la siguiente manera:
```C#
int resultado = checked(numero + 20);
```

Normalmente cuando sucede este tipo de excepcion c# no genera una excepcion, en cambio, trata de manejarlo y devuelve una respuesta erronea, esto con la finalidad de no decaiga el rendimiento de la aplicacion en caso se tenga multiples operaciones con el mismo problema.

Podemos cambiar la configuracion de esto de la siguiente manera:

Damos clic derecho en el proyecto y seleccionamos **propiedades**.

![[project-properties.png]]

Luego nos aparecera la siguiente ventana y hacemos clic en **compilacion**

![[project-configurate.png]]

Ahora, bajamos un poco y damos clic en **Avanzado**

![[project-avanced.png]]

Finalmente, damos clic en **verificar desbordamiento aritmetico**.

![[project-verify-overflow.png]]

De esta manera cada excepcion de desbordamiento que se genere, tambien se generara el respectivo error.
#### Nota - unchecked
El unchecked permite omitir la generacion del error asi este configurado, como se hice hace un momento. Practicamente devuelve lo mismo que cuando no se configura nada.

Se puede utilizar esta palabra reservada para situaciones especificas donde no necesariamente requieras generar un error de desbordamiento para una variable.

Ejemplo:
```C#
int resultado = unchecked(numero + 20);
```
### Importante
El checked unicamente funciona con variables de tipo de dato **int** o **long**. Al usarlo con otros no funcionara.