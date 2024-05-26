# Include
Le indica a la API que relacion debe incluir en la respuesta.
![[Pasted image 20240413220250.png]]

# Sort
Ordena los registros. El signo "-" indica que el orden debe ser descendente y cuando no se especifica ningun signo se entiende que el orden sera ascendente.
![[Pasted image 20240413220424.png]]

# Sparse Fildsets
Se utiliza para definir que atributos queremos de uno o varios recursos.
![[Pasted image 20240413220554.png]]Aqui solo se especifica el atributo 'content' y es lo unico que se muestra en 'attributes'.

# Filter
Se utiliza para filtrar los resultados.
![[Pasted image 20240413220713.png]]

# Page
Se utiliza para paginar la informacion.
![[Pasted image 20240413220835.png]]
'size' para indicar la cantidad de recursos que deseamos obtener y 'number' para indicar en que pagina te encuentras.


# Content Negotiation
Tanto las peticiones del cliente como las respuestas del servidor deben tener el header:
![[Pasted image 20240413221015.png]]
