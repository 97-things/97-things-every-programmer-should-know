# Prueba precisa y concretamente

Original: Test Precisely and Concretely

Es importante probar el comportamiento deseado y esencial de una unidad
de código, en vez de [probar el comportamiento incidental][1] de su
implementación en particular. Pero esto no debería ser tomado, o mal
tomado, como una excusa para las pruebas vagas. Las pruebas necesitan
ser exactas y precisas.

Como ejemplo ilustrativo podemos tomar el caso intentado y probado
múltiples veces, siendo ya todo un clásico: las rutinas de ordenamiento.
Implementar un algoritmo de ordenamiento no es necesariamente una tarea
diaria de un programador, pero el ordenamiento es una idea tan familiar
que mucha gente cree saber qué esperar de ello. Esta familiaridad
casual, sin embargo, puede hacer difícil ver más allá de ciertos
supuestos.

Cuando se le pregunta a los programadores “¿qué es lo que probarías?”,
la respuesta más común y, por mucho, es “el resultado del ordenamiento
es una secuencia ordenada de elementos”. A pesar de que es verdad, no es
toda la verdad. Cuando se les pide una condición más precisa, muchos
programadores agregan que la frecuencia resultante debe ser de la misma
longitud que el original. A pesar de que es correcto, aún no es
suficiente. Por ejemplo, dada la siguiente secuencia:

>3 1 4 1 5 9

La siguiente secuencia satisface una poscondición de estar ordenado de
manera no-descendiente y teniendo la misma longitud que la secuencia
original:

>3 3 3 3 3 3

A pesar de que satisface las especificaciones, ¡esto es también algo a
lo que ciertamente no nos referíamos! Este ejemplo está basado en un
error tomado de un código de producción real (afortunadamente capturado
antes de que fuera liberado), en el cual un simple desliz de un teclazo
o un lapso momentáneo del razonamiento nos lleva a un elaborado
mecanismo de llenar el resultado entero con el primer elemento de alguna
matriz.

La poscondición completa es que el resultado esté ordenado y que tenga
una permutación de los valores originales. Esto restringe apropiadamente
el comportamiento requerido. Que la longitud del resultado sea el mismo
que el de la longitud de la entrada viene con ello y no necesita ser
reiniciado.

Aún estipular la poscondición en la manera descrita no es suficiente
para darte una buena prueba. Una buena prueba debe ser leíble. Debe ser
comprensible y suficiente como para que leyéndola puedas ver si es
correcta (o no). A menos que ya tengas código por ahí para checar que
una secuencia se ordena y que esa secuencia contiene una permutación de
valores en otra, es muy probable que el código de prueba sea más
complejo que el código a probar. Como Tony Hoare observa: “Hay dos
manera de construir un diseño de software: una manera es hacerlo tan
simple que obviamente no hay deficiencias y la otra es construirlo tan
complicado que no hay deficiencias obvias”.

Usando ejemplos concretos eliminamos esta complejidad accidental y
oportunamente por accidente. Por ejemplo, dada la siguiente secuencia:

>3 1 4 1 5 9

El resultado del ordenamiento es el siguiente:

>1 1 3 4 5 9

Ninguna otra respuesta lo será. No aceptes sustitutos.

Los ejemplos concretos ayudan a ilustrar el comportamiento general de
una manera accesible y no ambigua. El resultado de agregar un item a una
colección vacía no es simplemente que no esté vacía: es que la colección
ahora tiene un elemento y que ese elemento es el item agregado. Dos o
más elementos calificarían como no vacío. Y estaría mal. Un sólo elemento
de un valor diferente también estaría mal. El resultado de agregar una
fila a una tabla no es simplemente que la tabla es una fila más grande.
Esto también implica que la llave para la fila puede ser usada para
recuperar la fila agregada. Y así por el estilo.

Al especificar el comportamiento, las pruebas deberían ser simplemente
exactas: también deben ser precisas.

[1]: prueba-comportamiento-requerido-no-incidental.html

Autor: Kevlin Henney