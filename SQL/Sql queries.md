 Obtener todas las bases de datos creadas en el gestor.
```Sql
select * from sys.databases
```

Obtener todas las tablas creadas en la base de datos :
```Sql
select * from sys.tables
```

Cambiar el nombre de una base de datos:
```Sql
ALTER DATABASE 'database_current' modify name = 'new_name'
```

Renombrar un tabla:
```Sql
exec sp_rename 'old_table_name', 'new_table_name'
```

Eliminar una columna de una tabla:
```Sql
alter table 'table_name'
drop column 'column_name'
```

Renombrar el campo de un atabla:
```Sql
exec sp_rename 'database.field_name', 'new_field_name'
exec sp_rename 'Empleados.idempleado', 'id'
```

Insertar registros de una tabla a otra:
```Sql
insert into salarios(nombre, apellido, salario)
select nombre, apellido, salario from empleados
where salario > 2500;
```

Indicar  la cantidad de registros a mostrar (*top* funciona con filtros tambien):
```Sql
select top 5 * from empleados;
```

Indicar, porcentualmente, la cantidad de registros a mostrar:
```Sql
select top 50 percent * from empleados;
// Mostrara solo el 50% de todos los registros
```

Realizar consulta con valores null:
```Sql
select * from clientes where nombre is null;

// No nulos
select * from clientes where nombre is not null;

// Se puede utilizar con filtros
```

Ver el valor inicial de la llave primaria de una tabla:
```SQL
select ident_seed('table_name');
```

Ver el valor de incremento de la llave primaria para cada registro de una tabla:
```SQL
select ident_incr('table_name');
```

Muestra valores unicos en la consulta. "Elimina" valores duplicados:
```SQL
select distinct pais from clientes
where compras is null
```

Cambiar el tipo de datos de una columna en una consulta:
```SQL
-- "CAST('column_name' as 'data_type'(length))"
select nombre + ' ' + apellido + ' ' +cast(edad as varchar(2)) [Nombre completo] from empleados
```

Excluir datos de una columna:
```SQL
select * from empleados
where not puesto = 'Gerente' and not puesto = 'Desarrollador'
```

# Operador like & not like

### Like
Muestra todas las ocurrencias que comiencen con un caracter especificado:
```SQL
select * from clientes
where name like 'A%'
```

Muestra todas las ocurrencias que terminen con un caracter especificado:
```SQL
select * from clientes
where name like '%A'
```
Cuando el simbolo *%* se ubica a la derecha especifica que los resultados deben tener como primer caracter la letra especificada. Si esta a la izquierda, las ocurrencias deben terminar con el caracter especificado.

Muestra todas las ocurrencias que contengan al menos tengan un caracter del especificado:
```SQL
select * from clientes
where name like '%A%'
```

Muestra todas las ocurrencias que contengan el segundo caracter, el caracterc especificado.
```SQL
select * from clientes
where name like '_a%'
```
Los guiones bajos indican el posicionamiento del caracter a buscar. En este caso, se especifica que el caracter debe esta en la segunda posicion (por el *_*) y que comience hacia la izquierda (por la ubicacion del *%*).

Muestra todas las ocurrencias que comiencen y terminen con los caracteres especificados:
```SQL
select * from clientes
where nombre like 'a%o'
```

### Not like

Se pueden utilizar las combinaciones mencionandas anteriormente pero en este caso se niega, por ejemplo:
```SQL
select * from clientes
where nombre not like 'a%'
```

Esta consulta mostrara todas las ocurrencias de la columna "nombre" que no tengan como primer caracter la letra "a".

