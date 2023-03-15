Para pasar los datos a un componente se crea un atributo y se utiliza la directiva "v-bind" .

En este caso se define el atributo "curso" y se pasa los datos. 
```HTML
<div id="app">
    <template v-for="course in courses"  :key="course.id">
        <detail-course :curso="course"></detail-course>
    </template>
</div>
```

# Props
Se trata de **atributos personalizados de la etiqueta HTML del componente**. Nos permiten pasar datos a nuestros componentes al momento de utilizarlos.

Para recibir esa información se define la propiedad ==props== en el componente y se le asigna un array que tendrá la información que se envia por el atributo.
```Javascript
app.component('detail-course', {
    data() {
        return {  
        }
    },
    props: ['curso'], //Una vez se recibe la informacion, esta se puede usar como si fuera una propiedad del componente.
    template://se muestran los datos
    `   
        <h1>{{curso.name}}</h1>
        <p>El precio del curso es: {{curso.price}}</p>
    `
})
```