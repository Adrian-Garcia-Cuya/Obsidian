A tener en cuenta que esta configuracion se realizo teniendo instalado xampp en ubuntun y no se hizo una instalacion independiente de cada herramienta.

El primer paso es poder registrar el "dominio" que tengas en mente. Luego, se tiene que ir a la ruta a continuacion: 

```
cd /etc
```
Posterior a ello se debe buscar el archivo **hosts**.
```
ls hosts
```
Una vez visualizado lo editamos con privilegios administrativos.
```
sudo vi hosts
```

![[hosts_file.png]]

Para esta explicacion se usara el siguiente "dominio": **facturacion.test**. Solo debe agregarse como se visualiza.

Continuando, el siguiente archivo a modificar es **httpd-vhosts.conf**. Aqui especificares a donde queremos que apunte nuestro "dominio". Lo encontraremos en la siguiente ruta:

```
cd /opt/lampp/etc/extra/
```

Al igual que el archivo anterior lo modificamos teniendo privilegios administrativos.
```
sudo vi httpd-vhosts.conf
```
Y se agrega lo siguiente:

![[httpd-vhosts.png]]

Realmente, aqui solo sirve agregar "ServerName" y "DocumentRoot" pero si se requiere agregar los demas, ahi esta como ejemplo.

Finalmente, se debe descomentar una linea de un archivo de texto para que pueda leer este archivo vhosts y asi tome encuenta los **virtual hosts* que se estan agregando.

El siguiente archivo se llama **httpd.conf**. Se puede encontrar en la siguiente ruta:
```
cd /opt/lampp/etc
```
Se edita como administrador
```
sudo vi httpd.conf
```
Es un archivo extenso pero el editor "vi" permite hacer busquedas. Bastara con una busqueda sencilla como esta : /.conf

![[httpd-1.png]]

Como se puede ver esta comentado por el "#". Solo hay que quitarlo.

![[httpd-2.png]]

Y con eso ya estaria incluyendo el archivo modificado anteriormente.

Lo unico que faltaria es reiniciar xampp y eso seria todo.
