# Aplica los principios de la programación funcional

Original: Apply Functional Programming Principles

Recientemente, la comunidad programadora ha demostrado un renovado
interés por la programación funcional. Parte del motivo es que las
propiedades emergentes de este paradigma las hacen una buena opción para
abordar la transición de la industria hacia el desarrollo sobre
arquitecturas multi-core. Sin embargo, aunque es, sin duda, una
aplicación importante, no es la razón por la que este texto te exhorta a
que aprendas sobre programación funcional.

Dominar el paradigma funcional puede mejorar enormemente la calidad del
código que escribes en otros contextos. Si lo comprendes y lo aplicas a
tus diseños, lograrás un nivel mucho más alto de transparencia
referencial.

La transparencia referencial es una cualidad deseable: implica que las
funciones devuelvan siempre los mismos resultados cuando se les pase el
mismo valor, independientemente de dónde y cuándo se las invoque. Es
decir, la evaluación de una función no depende tanto de los efectos
colaterales del estado mutable –idealmente, no depende en absoluto–.

Una de las principales causas de defectos cuando se programa en
lenguajes imperativos no es otra que las variables mutables. Cualquier
persona que se encuentre leyendo esto habrá tenido que investigar alguna
vez por qué un valor no es el esperado en una situación particular. La
semántica de visibilidad puede ayudar a mitigar estos errores insidiosos
o, al menos, reducir drásticamente su ubicación; pero es probable que el
verdadero culpable de su existencia sea un desarrollo que hace uso de
mutabilidad excesiva.

Y la industria no nos ayuda mucho con este problema. La mayoría de la
documentación introductoria sobre orientación a objetos tácitamente
promueve este tipo de prácticas, porque a menudo utilizan como ejemplo
una serie de objetos con un tiempo de vida relativamente largo,
invocando métodos mutadores unos sobre otros, lo cual puede ser
peligroso. Sin embargo, con un buen desarrollo guiado por pruebas,
particularmente asegurándose de [“simular roles, no objetos“][1], se
puede evitar la mutabilidad excesiva.

El resultado neto será un diseño que generalmente posee una mejor
distribución de responsabilidades con una mayor cantidad de funciones
–más pequeñas– que trabajan sobre los argumentos que se les pasa, en
lugar de hacer referencia a miembros mutables. Habrá menos defectos y
también será menos complejo detectarlos, porque es más fácil localizar
dónde se introdujo un valor no deseado que deducir el contexto
específico que resulta en una asignación errónea. Un diseño de este tipo
establecerá un nivel mucho más alto de transparencia referencial; y, de
seguro, nada fijará mejor estas ideas en tu cabeza que estudiar un
lenguaje de programación funcional, en el cual este modelo de
computación es la norma.

Por supuesto, este enfoque no es la mejor opción para todas las
situaciones. Por ejemplo, en sistemas orientados a objetos de este
estilo suele lograr mejores resultados con el desarrollo del modelo de
dominio (es decir, en el cual la interacción de las funciones sirve para
descomponer la complejidad de las reglas de negocio) y no tanto con el
desarrollo de la interfaz de usuario.

Domina el paradigma de la programación funcional y podrás –con criterio–
aplicar en otros contextos las lecciones que aprendas. Tus sistemas
orientados a objetos (para empezar) se llevarán mejor con las bondades
de la transparencia referencial y, contrario a lo que muchos te dirán,
estarán más cerca de su contraparte funcional. De hecho, algunos incluso
afirman que, en el fondo, los paradigmas de programación funcional y
orientada a objetos no son más que un mero reflejo el uno del otro, una
especie de yin y yang computacional.

[1]: http://www.jmock.org/oopsla2004.pdf

Autor: Edward Garson