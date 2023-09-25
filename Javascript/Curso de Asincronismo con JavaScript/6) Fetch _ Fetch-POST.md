# Fetch & Fetch-POST

Es una API que permite realizar peticiones HTTP asíncronas, basado en [[5) Promesas | promesas ]].

Una petición básica de fetch es realmente simple de realizar. Eche un vistazo al siguiente código:

```JavaScript
fetch('http://example.com/movies.json')
  .then(response => response.json())
  .then(data => console.log(data));
```

El uso de fetch() más simple toma un argumento (la ruta del recurso que quieres obtener) y devuelve un objeto Promise conteniendo la respuesta.

Actividad de la clase:

```JavaScript
import fetch from "node-fetch";

const API = 'https://api.escuelajs.co/api/v1';

function postData (urlAPI, data) {
//para enviar información se debe pasar 2 argumentos. El primero es la URL y el segundo es un objeto con ciertas propiedades.
    const response = fetch(urlAPI, {
        method: 'POST', //indicamos el método http.
        mode: 'cors', //Determina el modo que quieres usar para la request - cors: bloquea la información.
        credentials: 'same-origin',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(data) //Aquí colocamos la información que se enviará
    });
    return response;
}

const data = {
    "title": "Second Course",
    "price": 213,
    "description": "A description",
    "categoryId": 1,
    "images": ["https://placeimg.com/640/480/any"]
}

postData(`${API}/products`, data)
.then(response => response.json())
.then(data => console.log(data));
```