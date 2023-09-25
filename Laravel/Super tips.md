# Eliminación de cache
Cuando se modifica un archivo de configuración en laravel, por ejemplo, el archivo ".env", se debe actualizar la configuración de cache. Esto es por que laravel almacena las configuraciones en cache con el fin de evitar cargar los archivos de configuración en cada solicitud que se realice.
Importante aclarar que si se modifica y no se actualiza la caché, laravel seguirá usando la configuración anterior y los cambios no tendrán efecto.

Comando para actualizar la caché:
```PHP
php artisan config:cache
```