# ¿Qué son los Callbacks?

El callback es una función que se pasa a otra función como un argumento.

```JavaScript
function sum(num1, num2) {
    return num1 + num2;
}

function calc(num1, num2, callback) {
    return callback(num1, num2);
}
// no colocar paréntesis a "sum" ya que si se coloca se estaría llamando directamente a la función y generaría un error.
console.log(calc(2, 2, sum));
```