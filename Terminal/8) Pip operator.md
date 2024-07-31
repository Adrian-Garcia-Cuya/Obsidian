Un pipe operator de acuerdo a su nombre sería un tubo (me gusta verlo mas como un puente) para conectar funciones. En esta clase el profe enseña esto pero con dos funciones que no permiten entenderlo del todo bien y tampoco a la primera, como soy docente pensé que muchos necesitarian una forma mas clara para entederlo. Con un ejemplo mejor, aquí está:

**ls** es un comando que nos sirve para mostrar una lista de los archivos y directorios. De modo tal que si hacemos **ls** estando en home, este comando nos va mostrar la lista de los archivos y directorios (carpetas) ejemplo:

`ls Midirectorio index.html nombres.txt error.txt output.txt`

**sort** es un comando que nos permite ordenar alfabeticamente las lineas de archivos de texto. De modo tal que si tenemos una archivo de texto llamado nombres con los siguientes nombres(cada uno en una línea): Carlos Maria Andrés. y aplicamos el comando sort, sucederá lo siguiente

`sort nombres.txt Andres Carlos Maria`

Sí, como te diste cuenta los ordenó alfabeticamente. Y entonces para que se usa el **Pipe operator**? Un **pipe operator** toma los resultados o datos (output) obtenidos de la ejecución de un primer comando para que el segundo comando los use como entrada (input) al ejecutar su proceso y entonces la ejecución de ese segundo comando se hace sobre el resultado (output) del primero.

Por ejemplo si quisieramos ver los directorios y archivos de nuestro home de manera ordenada alfabeticamente tendriamos que hacer lo siguiente.

`ls | sort`

y de este modo obtendríamos lo siguiente:

`ls | sort Midirectorio error.txt index.html nombres.txt output.txt`

Lo que sucedió aquí es que tomamos el resultado del primer comando :ls (la lista de nombres de directorios y archivos) y a ésta, se ejecutó el proceso del segundo comando: sort. Y como resultado obtuvimos nuestra lista de home organizada alfabeticamente (la terminal toma las letras mayusculas como prioridad, es por esto que "Midirectorio" está en primer lugar)

Esta vista ordenada de archivos y directorios en home fue posible gracias al pipe operator ya que recordemos que **sort** es un comando que si se ejecuta solo (sin un pipe operator), funcionará unicamente con archivos de texto.