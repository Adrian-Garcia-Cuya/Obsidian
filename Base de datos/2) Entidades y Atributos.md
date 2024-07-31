# Entidades

Una ==entidad== es un objeto real o abstracto existente en el mundo real y es distinguible de otros objetos.

# Atributos
Los ==atributos== son las características o propiedades de una entidad.

Los circulos son los tributos y el rectagunlo es la entidad.

![[atributos.jpg]]

## Tipos de atributos
Existen tipos de atributos. Los más comunes son:

- **Atributos multi-valuados:** es cuando cada instancia/ocurrencia de un tipo de entidad contiene múltiples valores.

**Ejemplo:** Una persona puedes tener varios números de teléfonos.

Se representa gráficamente de la siguiente forma

![[atributo_multivaluado.jpg]]

- **Atributos compuestos:** tienen sub partes, es decir, otros atributos.

**Ejemplo:** Como se puede observar, el atributo "dirección" está formado por otros sub-atributos.

![[atributos_compuestos.jpg]]

- **Atributo especial o derivados:** Su valor se puede obtener a partir de valores de otros atributos.

## <ins>Entidades débiles</ins>

Hay dos razones por las cuales una entidad se consideraría débil:

**por identidad:** depende del identificador de otra entidad.

**Ejemplo:**

![[identidad.png]]

Los ejemplares tienen la llave foranea de libros, lo que la hace dependiente.

**por existencia:** depende de la existencia de otra entidad.

**Ejemplo:**

![[existencia.png]]

Si bien es cierto la entidad "Ejemplar" tiene su propio identificador, su existencia depende de la entidad "Libros", ya que, los ejemplares existen debido a que el libro existe.