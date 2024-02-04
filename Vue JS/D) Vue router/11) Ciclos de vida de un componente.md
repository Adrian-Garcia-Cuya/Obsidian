# Que son?
Cada instancia de componente Vue pasa por una serie de pasos de inicialización cuando se crea. Durante este proceso, se le permite al desarrollador poder ingresar su codigo en determinadas etapas y asi realizar ciertas tareas.

# Métodos del ciclo de vida
Hay gran cantidad de metodos pero los mas usados son los siguientes:
1. 1. beforeCreate(): Se ejecutara antes de que se cree el componente.
2. 2. created(): Se ejecutara luego de crearse el componente.
3. 3. mounted(): Se ejecutara cuando se monte el componente. Es decir, cuando se renderize el contenido y el usuario lo pueda visualizar.
4. 4. updated(): Se ejecuta cuando hay un cambio en el DOM. Por ejemplo, cambiar el contenido de un componente.
5. 5. unmounted(): Se ejecutara cuando se desmonte un componente. Por ejemplo, queremos mostrar otro componente al hacer clic en un 'enlace'. Lo que pasara es que se va a desmontar el componente actual y se montara uno nuevo.
![[Pasted image 20231209151222.png]]
###### Nota
El método created es ideal para recuperar información de la base de datos o una API.

