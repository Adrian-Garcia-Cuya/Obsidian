Son reglas o restricciones que se definen para los datos de una tabla.

**Primary key:**
- Insertar registros unicos.
- No permite insertar null.
- Solo permite un unico PK.
- Facilita el enlace/relacion entre tablas
- Las tablas que tienen  la llave primaria son llamadas tablas principales/de referencia.
```SQL
--Agregar un constraint de llave primaria
ALTER TABLE Personas
ADD CONSTRAINT PK_enlace PRIMARY KEY (idpersona);
--ADD CONSTRAINT 'nombre_personalizado_de_restrinccion' PRIMARY KEY (idpersona);
```
```SQL
--Eliminar un constraint de llave primaria
ALTER TABLE Personas DROP CONSTRAINT PK_enlace
```

**Foreign Key**
- Previene acciones que puedan dañar los enlaces/relaciones entre tablas.
- Realiza un enlace con una llave primaria.
- Las tablas que tienen una llave foranea son llamadas tablas secundarias/hijas.
- Evita insertar datos que no sean compatibles con el campo de la llave primaria. Es decir, los valores ingresados deben estar en el campo de la llave primaria, caso contrario, generara un error.
```SQL
--Agregar un constraint de llave foranea
ALTER TABLE ordenes
--ADD CONSTRAINT FK_ordenes_cliente FOREIGN KEY REFERENCES 'table_name'('primary_key');
ADD CONSTRAINT FK_ordenes_cliente FOREIGN KEY REFERENCES clientes(id_cliente);
--Eliminacion en cascada
ADD CONSTRAINT FK_ordenes_cliente FOREIGN KEY REFERENCES (id_cliente) ON DELETE CASCADE; 
```
```SQL
--Eliminar un constraint de llave primaria
ALTER TABLE ordenes DROP CONSTRAINT FK_ordenes_cliente
```

**Unique:**
- Asegura que las ocurrencias de un campo sean unicos.
- Puede haber mas de un campo con la restrinccion 'unique'.
- Permite valores 'null'.

```SQL
--Agregar un constraint de unique
ALTER TABLE Personas
ADD CONSTRAINT UQ_idpersona unique (idpersona);
--ADD CONSTRAINT 'nombre_personalizado_de_restrinccion' unique (idpersona);

--Eliminar un constraint de unique
ALTER TABLE Personas DROP CONSTRAINT UQ_idpersona
```

**Check**
- Delimita un rango de valores.
```SQL
ALTER TABLE Personas
ADD CONSTRAINT CK_edad check (edad>=18);

ALTER TABLE Personas DROP CONSTRAINT CK_edad
```

**Default**
- Asigna una valor por defecto.

```SQL
ALTER TABLE Personas
ADD CONSTRAINT DF_ciudad default 'default_value' for 'filed_name'
ADD CONSTRAINT DF_ciudad default 'no tiene' for ciudad

ALTER TABLE Personas DROP CONSTRAINT DF_ciudad
```

**Identity**
- Incrementa su valor a medida que se registran filas.
- Generalmente se utiliza como identificador de las filas de una tabla.

###### Nota
El uso de constraint permite personalizar el nombre de la regla o restrinccion. A diferencia de agregar la restriccion al momento de crear la tabla, por ejemplo, agregar directamente la llave primaria en la creacion de una tabla.