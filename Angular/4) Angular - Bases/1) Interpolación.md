## Interpolación
Consiste en agregar/incrustar expresiones js en las platillas. Para usar la interpolación solo debe agregarse las llaves dobles *{{ }}*. 

Ejemplo:
```HTML
<h3>Current customer: {{ currentCustomer }}</h3>
```

El HTLM está enlazado al componente, lo que permite mostrar los valores de las propiedades que contenga el componente. Angular reemplazará "currentCustomer" por su valor asignado.


