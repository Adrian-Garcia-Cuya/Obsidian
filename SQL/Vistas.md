Es una tabla virtual que se construye a partir de una consulta definida a una o más tablas. Esta consulta incluye una selección específica de columnas, que puede basarse en criterios o condiciones predefinidas. 

# Utilidad
El propósito de una vista es proporcionar una manera conveniente de acceder a datos y simplificar consultas recurrentes.

## Creacion de una vista

```SQL
CREATE VIEW Mayores_30
AS
SELECT nombre, apellido, telefono, edad
FROM clientes WHERE edad>30
```
## Modificacion de una vista
Para modificar una vista solo es necesario agregar la palabra 'alter' y luego la estructura es la misma, incluso la consulta en si. Es ahi, donde se realiza la modificacion.

En este caso se esta agregado la columna "fecha_nacimiento".

```SQL
ALTER VIEW Mayores_30
AS
SELECT nombre, apellido, telefono, edad, fecha_nacimiento
FROM clientes WHERE edad>30
```

## Eliminar una vista

```SQL
DROP VIEW Mayores_30
```