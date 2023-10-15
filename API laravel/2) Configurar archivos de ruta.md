En la carpeta rutas se tienen dos archivos donde se ingresan las rutas (web y api).

La principal diferencia entre estos 2 archivos es el middleware que los protege.

El middleware "web" solicita el token "csrf" en cualquier peticion.

El middleware "api" no cuenta con la proteccion "csrf" debido a que las solicitudes no se enviaran desde nuestro sistema por lo que no enviaria el token "csrf".

# Versiones
Puedes tener versiones en la API. Esto te permite editar una version x  sin afectar a la version y.