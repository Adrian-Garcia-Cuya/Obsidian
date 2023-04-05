# Promesas

Las promesas son objetos que son usados para trabajar con el [[1) Asincronismo]]. Representa la terminación o el fracaso de una operación asíncrona

Es algo que va pasar ahora, luego o nunca.

Una promesa tiene 3 estados:

- Pendiente (cuando se ejecuta)
- Cumplido (cuando se regresa la información deseada)
- Rechazado

Al instanciar una promesa se pasa como argumento una función anónima, la cual, tendrá dos parámetros (resolve y reject). Está función anónima retornará una de esas funciones, dependiendo de cual sea se mostrará la información al usuario o no.

\*\*Nota: \*\*se suele usar el término **thenable** , para indicar que un objeto tiene disponible un método "*then*"

```JavaScript
const promise = new Promise(function (resolve, reject) {
    resolve('hey!');
});

const cows = 15;

const countCows = new Promise(function (resolve, reject) {
    if (cows > 10 ) {
    //La función estática resolve retorna un objecto promise que es resuelta.
        resolve(`We have ${cows} cows on the farm.`);
    } else {
    //La función estática reject retorna un objecto Promise que es rechazado.
        reject("There is no cows on the farm.");
    }
});
//El "then" se utiliza para asociar las funciones que se invocarán cuando la promesa se resuelva.
//El método "then" retorna una promesa.
//Si se devuelve una Promesa ya resuelta, la Promesa devuelta por el método then queda resuelta adoptando el valor de la promesa anterior.
//La método then también devolverá un promise, para permitir encadenar varias llamadas.
//Se utiliza para los casos de éxito. Este método puede recibir dos argumentos: función callback para casos de éxito y también de fallo. Generalmente se usa solo pasando el callback de caso de éxito.
countCows.then((result) => {
    console.log(result);
}).catch((error)=> {
    console.log(error);
}).finally(()=> {
    console.log('Finally');
});
```