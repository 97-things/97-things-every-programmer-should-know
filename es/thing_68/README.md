# No te repitas

Original: Don't Repeat Yourself

De todos los principios de programación, No te Repitas (_Don’t Repeat
Yourself_, DRY) es quizás uno de los fundamentales. El principio fue
formulado por Andy Hunt y Dave Thomas en _The Pragmatic Programmer_ y
subyace a muchas otras bien conocidas buenas prácticas y diseños de
patrones en software. El desarrollador que aprende a reconocer la
duplicación y entiende cómo eliminarla, a través de una abstracción
práctica y apropiada, puede producir código mucho más limpio que quien
infecta continuamente la aplicación con repetición innecesaria.


## La duplicidad es un desperdicio

Cada línea de código que va en una aplicación se debe mantener y es una
fuente potencial de futuros errores. La duplicación infla
innecesariamente el código base, dando lugar a más oportunidades para
los errores y agregando complejidad accidental al sistema. El atasco que
la duplicación agrega al sistema también hace más difícil para los
desarrolladores que trabajan con el sistema el completo entendimiento
del sistema entero, o de tener la certeza de que los cambios realizados
en un lugar no necesitan también ser hechos en otros lugares que
duplican la lógica de lo que se está trabajando. DRY requiere que “cada
pieza de conocimiento debe tener una representación única, inequívoca y
autorizada en el sistema”.


## Cambiar repetición en llamadas de procedimiento por automatización

Muchos de los procesos en el desarrollo del software son repetitivos y
fácilmente automatizados. El principio DRY se aplica en estos contextos
tan bien como en el código fuente de la aplicación. Las pruebas manuales
son lentas, propensas al error y difíciles de repetir, por lo que, si es
posible, deberían usarse los conjuntos de pruebas automatizadas.
Integrar software puede tomar mucho tiempo y ser propenso al error si se
hace manualmente, por lo que el proceso de construcción deberá ser
ejecutado tan frecuente como sea posible, idealmente en cada _check-in_.
Donde sea que existan esos dolorosos procesos que puedan ser
automatizados, deben ser automatizados y estandarizados. La meta es
asegurarse de que sólo hay una manera de llevar a cabo la tarea, y que
ésta sea lo menos dolorosa posible.


## Cambiar repetición en la lógica por abstracción

La repetición en la lógica puede tomar muchas formas. Copiar-pegar
lógica de un `if-then` o `switch-case` es uno de los casos más comunes
de detectar y corregir. Muchos patrones de diseño tiene la meta
específica de reducir o eliminar la duplicación en la lógica de una
aplicación. Si un objeto usualmente requiere que varias cosas sucedan
antes de que pueda ser utilizado, esto se puede lograr con una `Abstract
Factory` o `Method Factory`. Si un objeto tiene muchas variaciones
posibles en su comportamiento, estos comportamientos pueden ser
inyectados con el patrón de Estrategia en vez de largas estructuras `if-
then`. De hecho, la formulación de patrones de diseño es un intento de
reducir la duplicación del esfuerzo necesario para resolver problemas
comunes y discutir dichas soluciones. Adicionalmente, DRY puede ser
aplicado a estructuras, tales como esquemas de base de datos, resultando
en la normalización.

## Una cuestión de principio

Otros principios de software también están relacionados con DRY. El
principio “Uno y Sólo Uno”, el cuál aplica al comportamiento funcional
del código, puede ser pensado como un subconjunto de DRY. El principio
“Abierto/Cerrado”, el cual estipula que “las entidades de software deben
estar abiertas para la extensión, pero cerradas para la modificación”,
sólo funciona en la práctica cuando se sigue el DRY. Del mismo modo, el
bien conocido Principio de la Responsabilidad Única (SPR), que requiere
que una clase tenga “una única razón para cambiar”, se basa en DRY.

Cuando se sigue en estructura, lógica, procesos y funciones, el
principio provee una guía fundamental para los desarrolladores de
software y ayuda a la creación de aplicaciones más simples, más fáciles
de mantener y de alta calidad. Si bien hay escenarios en los cuales la
repetición puede ser necesaria para cumplir con el índice de rendimiento
u otros requerimientos (por ejemplo, desnormalización en base de datos),
esto debería ser usado sólo donde aplique directamente un problema real
en vez de uno imaginario.

Autor: Steve Smith