## Async
Es una palabra reservada que define una función asíncrona.
## Await
Es un operador que se utiliza para esperar una promesa y obtener su valor de cumplimiento.
Recordar que esta palabra se usa dentro de las funciones asíncronas.

Veamos un ejemplo:
```Javascript
const fnAsync = () => {
    return new Promise((resolve, reject) =>{
        (true)
            ? setTimeout(() => resolve('Async!!!'), 2000)
            :reject(new Error('Error!'));
    });
}  

const anotherFn = async () => { //se crea la función asíncrona
    const somethig = await fnAsync(); //usamos el await para esperar a que la función termine
    console.log(somethig);
    console.log('hello');
}

console.log('Before');
anotherFn();
console.log('after');
```