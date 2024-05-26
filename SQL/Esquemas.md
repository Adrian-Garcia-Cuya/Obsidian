Un esquema es un estructura logica que se utiliza para poder organizar y agrupar objetos dentro de la base de datos (tablas, procedimientos, vistas, etc).

Permite aislar y controlar los permisos de accesos a esos objetos. Cada objeto de una base de datos debe estar dentro de un esquema en especifico.

![[esquema-example.png]]

# Creacion de esquemas

```SQL
create schema Cobros;

create schema ventas;
```

# Creacion de tablas en esquemas

```SQL
create table ventas.clientes
(
idclientes int,
nombre int,
direccion varchar(30)
)

create table cobros.clientes
(
idclientes int,
nombre int,
direccion varchar(30)
)
```

Al estar en diferentes esquemas se pueden crear tablas con los mismos nombres. Ademas, pueden tener diferentes columnas, no es necesario que tengan lo mismo

# Consulta de tablas en esquemas

```SQL
select * from cobros.clientes

select * from ventas.clientes
```