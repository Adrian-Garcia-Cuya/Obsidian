Los componentes tienen un lugar designado en donde crearse. Lo puedes ver a continuación: 

![[carpeta_componentes.png]]

# Denominar componentes
Existe una regla o buena práctica, al momento de nombrar los componentes creados, estos deben tener dos palabras. Por ejemplo: "MyComponent". Vue nos dice que se debe realizar con la finalidad de evitar futuros conflictos con las etiquetas "HTML", ya que, estas tienen solo un nombre. Por ejemplo, sin que sepas, llamas a tu componente igual que una etiqueta "HTML" y por consiguiente, se generaría un error.

En este caso se nombro al componente ==CounterNumber==.

# Secciones de un componente

1. ==Template==: Aquí irá el código "HTML" del componente.
3. ==Script==: Información relevante del componente (agregar otro componente,definir data, etc).
4. ==style==: Aquí irán los estilos del componente.

# Agregar un componente a otro

Esto se realiza en la sección "script" del componente en donde se deasea agregar otro componente. Primero hay que importarlo, luego definir un el campo "components" y ahí agregar el nombre del o los componentes.

Veamos un ejemplo:

En este caso, se está agregando un componente al componente padre (App). Como se puede ver, en "export default", en el campo "components", irán los nombres de los componentes que se quieren agregar.

```Javascript
//<script>
import CounterNumber from ./components/counterNumber.vue;

export default {
	name:'App',
	components: {
		CounterNumber
	}
}
//</script>
```

Luego, para poder usar el componente solo se debe agregar su etiqueta al template.

```HTML
<template>

<img alt="Vue logo" src="./assets/logo.png">
<CounterNumber></CounterNumber>//uso del componente creado en el template del componente padre

</template>
```

#### Importante (scoped)
Para que los estilos agregados al componente solo afecten a si mismo. Es neceserio agregar el atributo ==scoped==.
```HTML
<style scoped>
	h1 {
		color: red;
	}
</style>
```

# Ejercicio del contador en un componente
Es similar al primer ejercicio al usar el CDN pero aqui será usando un entorno de trabajo.

Esto se realizará en el componente creado llamado ==CounterNumber==.

Vista del template del componente:
```HTML
<template>
    <h1>Hola desde el componente counter number 😂</h1>
    <button @click="disminuir()" :disabled="contador==0"> //se desabilita cuando el componente es = 0.
        -
    </button>
    {{ contador }}
    <button @click="aumentar()">
        +
    </button>
</template>
```

Funcionalidad del componente:
```Javascript
//<script>
export default {
    data() {
        return {
            contador: 0
        }
    },
    methods: {
        disminuir(){
            this.contador--;
        },
        aumentar(){
            this.contador++;
        }
    }
}
//</script>
```
