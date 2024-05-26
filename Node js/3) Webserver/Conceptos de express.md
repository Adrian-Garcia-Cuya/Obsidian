
# Servicio de archivos estáticos en Express
Configuracion del middleware *static* para servir (enviar los archivos para que los usuario lo visualicen y utilicen) archivos estaticos. Indica donde se encuentra los archivos estaticos en el servidor.
```node js
app.use(express.static('public'));
```

# Public
Es una carpeta que muestra contenido *publico*, cualquier persona que tenga el *url* puede visualizarlo.

