Es una estructura de datos que se crea sobre una o varias columnas de una tabla. Esta estructura permite una rápida localización de las filas de la tabla en base a su contenido en la columna indexada. Es decir, en lugar de tener que escanear toda la tabla para encontrar las filas que coinciden con ciertos criterios de búsqueda, el índice proporciona un camino directo hacia esas filas.

Cuando agregamos un índice a una columna, la base de datos crea una estructura de datos adicional que ordena y organiza los valores de esa columna de manera eficiente. 

# Utilidad
- **Mejora de la velocidad de búsqueda:** Al indexar columnas comunes en consultas, como campos de búsqueda o de filtrado, se acelera el proceso de búsqueda, ya que el motor de la base de datos puede utilizar el índice para encontrar rápidamente las filas relevantes en lugar de escanear toda la tabla.
- **Optimización de consultas:** Los índices pueden mejorar significativamente el rendimiento de las consultas al permitir al motor de la base de datos encontrar y acceder a los datos de manera más eficiente.
- **Ordenación de resultados:** Además de facilitar la búsqueda rápida, los índices también pueden ayudar en la recuperación de filas ordenadas por la columna indexada, lo que es útil en consultas que requieren resultados ordenados.
- **Reducción de la carga en el servidor:** Al acelerar las consultas, los índices pueden reducir la carga en el servidor de la base de datos, lo que resulta en un mejor rendimiento general del sistema.

## Tipos

**Clustered:**
- Definen el orden de los datos. Los datos en la tabla se almacenan físicamente en el mismo orden que el índice. Por lo tanto, solo puede haber un índice clustered en una tabla.
- Las filas de la tabla están ordenadas directamente por la clave primaria o el campo clave especificado en el índice clustered.

**Nonclustered:**
- No definen ningún orden específico para los datos en la tabla. Los datos en la tabla se almacenan en un orden lógico independiente del índice.
- Crean una estructura de datos separada que contiene las claves de índice y las referencias a las filas correspondientes en la tabla. Esta estructura de índice facilita la búsqueda rápida de datos basada en las claves de índice sin necesidad de reorganizar los datos físicamente en la tabla.

