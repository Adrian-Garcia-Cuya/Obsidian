# Machine Learning
El **Machine Learning**(Aprendizaje Automático)  es un campo de la IA, el cual, a través de algoritmos, se da la capacidad a la computadora de encontrar patrones en datos masivos y apartir de ellos realizar predicciones.

# Ramas del Machine Learning

## Aprendizaje supervisado
Esta rama consiste en darle a la maquina un conjunto de "datos etiquetados"(**labeled data**, datos para los que ya conoce la respuesta de destino), es decir, se le dice al modelo es que lo que queremos que aprenda.

Por ejemplo: 

Se tiene una heladería y durante los últimos años hemos estado registrando diariamente datos climatológicos, temperatura, mes, día de la semana, etc., y también hemos hecho lo propio con el número de helados vendidos cada día. En este caso, seguramente nos interesaría entrenar un modelo que, a partir de los datos climatológicos, temperatura, etc. (características del modelo) de un día concreto, nos diga cuántos helados se van a vender (la etiqueta a predecir).

### Tipos de Aprendizaje supervisado

#### Aprendizaje supervisado por clasificación
Se usa cuando el resultado deseado es una etiqueta discreta, es decir, una etiqueta dentro de un conjunto finito de etiquetas posibles.

Con conjunto finito se refiere a un limite de valores posibles

Por ejemplo: Saber si un alumno aprobo o desaprobo. En este caso de tiene algo llamado "clasificación binaria" debido a que su conjunto finito es de dos valores.
###### Algoritmos de clasificación
- Regresión logística
- Máquinas de vectores de soport
- Árboles de decisión clasificación
#### Aprendizaje supervisado por regresión
Se predice un valor real basado en entradas pasadas. Estos algoritmos se usan para predecir valores de salida basados en algunas características(features) de entrada obtenidas de los datos.

El **resultado es un número**. Es decir, el resultado de la técnica de machine learning que estemos usando será un valor numérico, dentro de un conjunto infinito de posibles resultados.
###### Algoritmos de Regresión
- Regresión lineal
- Regresión polinimeal
- Vectores de soporte de regresión
- Árboles de decisión
- Borsques aleatorios

##### Nota 
Las **varibles independientes** son las características(features).
Las **variables dependientes** son las etiquetas u objetivo. Resultado.
## Aprendizaje no supervisado