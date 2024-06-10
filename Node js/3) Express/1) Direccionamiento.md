Hace referencia a como una aplicacion decide que hacer cuando recibe una solicitud/peticion de un cliente, a partir de un punto final (endpoint) en específico.

Ejemplo:

```javascript
import express from 'express';

const app = express();

app.get('/', (req, res) => {
	res.send('Hello word');
});

//'/' -> esto es el 'endpoint'
```

# Vías de acceso de ruta
Son las diferentes formas de definir y gestionar rutas, para asi, manejar solicitudes HTTP en una aplicación.

Tipos de rutas en express:

- Rutas básicas:
```javascript
app.get('/', function (req, res) {
  res.send('root');
});
```

```javascript
app.get('/about', function (req, res) {
  res.send('about');
});
```

- Rutas con patrones de serie
```javascript
app.get('/ab?cd', function(req, res) {
  res.send('ab?cd');
});


app.get('/ab*cd', function(req, res) {
  res.send('ab*cd');
});
```

- Rutas con expresiones regulares
```javascript
app.get(/a/, function(req, res) {
  res.send('/a/');
});
```

# Manejadores de ruta
Son funciones que se ejecutan cuando el servidor recibe una solicitud HTTP. Practicamente, indican como debe responder la aplicacion ante las solicitudes HTTP.

## Parámetros de un manejador de rutas
Un manejador de rutas en express recibe 3 parámetros:

- **req (request) :** es el objeto de la solicitud que contiene informacion de la solicitud HTTP, como: parámetros, cuerpo, encabezados, etc.
- **res (response):** es el objeto de respuesta que se utiliza para enviar una respuesta HTTP al cliente.
- **next:** ?? -> buscar informacion luego de ver los middlewares.

# Metodos de respuesta
Para devolver una respuesta, express brinda una serie de metodos a través del objeto de respuesta **"res"**, a partir de ellos, se puede enviar una respuesta al cliente y, de esta manera, terminar el ciclo de solicitud/respuesta (cumplimiento del procesamiento de la solicitud del cliente).

Algunos metodos de respuesta:

 ![[response-methods.png]]