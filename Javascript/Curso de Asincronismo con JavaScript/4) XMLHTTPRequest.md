# XMLHTTPRequest

Es un objeto de Javascript que permite realizar peticiones HTTP asíncronas (AJAX).

```JavaScript
//creamos una función la cual recibirá dos parámetros. La URL y el callback
function fetchData(urlApi, callback) {
    let xhttp = new XMLHttpRequest(); //Se crea un objeto xhttp que nos permitirá realizar peticiones

    xhttp.open('GET', urlApi, true); //Este método inicializa una solicitud recién creada o reinicializa una existente
    xhttp.onreadystatechange = function (event) {//Este evento se activa cada vez que el readyState cambia.
    //La propiedad "readyState" devuelve el estado en el que se encuentra un objeto XHR.
    //La propiedad "status" muestra los códigos de estado de respuesta HTTP.
        if (xhttp.readyState === 4 && xhttp.status === 200) {
        //El método "parse" convierte los datos que envía el servidor a objetos javascript.
        //La propiedad "responseText" devuelve una cadena que es la respuesta a la consulta.
            callback(null, JSON.parse(xhttp.responseText));
        }else {
            const error = new Error ('Error' + urlApi);
            return callback(error, null);
        }
    }

    xhttp.send();//El método "send" envía la solicitud al servidor.
}
```

```JavaScript
//Se invoca a la función creada y le damos dos argumentos. La URL Y el callback (en este caso es una función anónima).
//1) Aquí se obtuvo una colección de objetos js.
fetchData(`${API}/products`, function(error1, data1) {
    if (error1) return console.error(error1);
    //Se volverá a invocar la función dentro de esta misma las veces que sea requerida.
    //2) Se obtuvo el primer objeto js de la colección. 
    fetchData(`${API}/products/${data1[0].id}`, function(error2, data2) {
        if (error2) return console.error(error2);
        3) Por último, se obtiene el nombre de la categoría.
        fetchData(`${API}/categories/${data2?.category?.id}`, function(error3, data3) {
            if (error3) return console.error(error3);
            console.log(data1[0]);
            console.log(data2.title);
            console.log(data3.name);
        });
    });
});
```