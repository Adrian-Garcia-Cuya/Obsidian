La normalización es una técnica que emplea para organizar el contenido de las tablas de las bases de datos. Esto tiene como finalidad minimizar la redundancia de datos.

La **redundancia de datos** ocurre cuando la misma pieza de _datos_ existe en dos (o más) lugares separados.

Ejemplo: 
![[sin_normalizar.png]]

La normalización se componen de ciertas reglas:

### Primera forma norma (1FN)
#### Características:
- Atributos atómicos (sin campos repetidos)

Aplicando **1FN** al ejemplo anterior, la tabla quedaría de la siguiente forma:
![[1FN.png]]

### Segunda forma norma (2FN)
#### Características: 
- Cumple la 1FN.
- Cada campo de la tabla debe depender de una clave única.

Aplicando **2FN** al ejemplo anterior, la tabla quedaría de la siguiente forma:
![[2FN.png]]

### Tercera forma normal (3FN)
#### Características: 
- Cumple 1FN.
- Cumple 2FN.
- Elimine los campos que no dependan de la clave primaria.

Aplicando **3FN** al ejemplo anterior, la tabla quedaría de la siguiente forma:

![[3FN.png]]

Como se puede observar, se creo una tabla "cursos", ya que, el campo "nombre_curso" no dependía de la clave primaria. Por ellos, se creo otra tabla en donde cada curso tendrá su clave y se podrá identificar en la tabla alumnos, a que curso pertenece mediante la clave foranea.

### Cuarta forma normal (4FN)
#### Características: 
- Cumple 1FN.
- Cumple 2FN.
- Cumple 3FN.
- Los campos multivaluados se identifican por una clave única.

Aplicando **4FN** al ejemplo anterior, la tabla quedaría de la siguiente forma:

![[4FN.png]]

En esta última forma, el tributo "materia" de la tabla "materias" es un atributo multivaluado es por ello que se repite varias veces. Aplicando la 4FN, nos dice que este atributo debe tener una clave única, por tal motivo, se separó en otra tabla llamada "materias_por_alumno".


##### Anotación importante
**Regla general**: 
- cuanto tienes una cardinalidad 1 a 1 no importa a que tabla le coloques la referencia (llave foranea) es indistinto.

- Cuando tienes una cardinalidad 1:N es muy importante que la tabla donde tienes la terminación mucho, en esa tabla colocaras la llave foranea de la tabla que tiene uno (1).

Ejemplo: Posts y Usuarios

La llave foranea será usuarios (1) en la tabla Posts(N).

- Entre **la cardinalidad N:N** surge la necesidad de construir una tabla intermedia que se conecta con las 2 iniciales con cardinalidad 1:N, de esta manera podemos relacionarlas haciendo uso de llaves compuestas o llaves artificiales, dependiendo de la forma de trabajo.