# Actúa con prudencia

Original: Act with Prudence

>“En todo lo que emprendas, actúa con prudencia y considera las consecuencias”
>_Anónimo_

No importa qué tan cómoda se vea una agenda de trabajo al comienzo de una
iteración, no podrás evitar sentirte bajo presión en algún momento. Si te
encuentras en una situación en la que tienes que elegir entre “hacerlo
bien” o “hacerlo rápido”, suele ser tentador “hacerlo rápido” y pensar
que regresarás a corregirlo más adelante. Cuando te haces esta promesa a
ti mismo, a tu equipo, al cliente, lo haces en serio. Pero a menudo la
siguiente iteración trae nuevos problemas y te debes enfocar en ellos.
Este tipo de trabajo aplazado se conoce como deuda técnica y no es un
buen amigo.  Martin Fowler, en su [taxonomía de la deuda técnica][1],
la llama específicamente deuda técnica deliberada, la cual no debería
confundirse con la deuda técnica inadvertida.

La deuda técnica es como un préstamo: te trae beneficios en el corto
plazo, pero deberás pagar intereses hasta terminar de saldarla. Tomar
atajos a la hora de programar hace que sea más difícil agregar
funcionalidad o refactorizar tu código; las soluciones rápidas son un
caldo de cultivo para defectos y casos de prueba muy frágiles. Mientras
más tiempo las abandones, peor se ponen. Para cuando te decidas a
corregir el problema puede que haya toda una pila de malas decisiones de
diseño acumulada encima del problema original, haciendo que el código
sea mucho más difícil de refactorizar y corregir. De hecho, es sólo
cuando las cosas están tan mal como para tener que arreglarlas, que
realmente vuelves y corriges el problema. Pero para entonces suele ser
tan difícil corregirlo que no te puedes permitir el tiempo ni correr el
riesgo.

Hay ocasiones en las que debes incurrir en la deuda técnica para cumplir
con una fecha límite o para implementar una pequeña parte de una
función. Intenta esquivar esos casos; sólo hazlo si la situación lo
exige. Pero (y éste es un gran pero) debes mantener un ojo sobre la
deuda técnica y pagarla tan pronto como puedas o las cosas se irán
rápidamente cuesta abajo. Apenas te hayas endeudado, escribe una tarjeta
o registra el problema en tu sistema de seguimiento para asegurarte de
no olvidarlo.

Si planeas pagar la deuda en la próxima iteración, el costo será mínimo.
Pero si la abandonas, se incrementarán los intereses y esto también
deberá registrarse para que el costo permanezca a la vista. Hacer esto
resaltará el impacto que tiene la deuda técnica del proyecto sobre el
valor de la empresa y permitirá una priorización de pago. Cómo calcular
y realizar el seguimiento de los intereses dependerá de cada proyecto,
pero deberás hacerlo.

Paga la deuda técnica tan pronto como puedas; sería imprudente no
hacerlo.

[1]: http://martinfowler.com/bliki/TechnicalDebtQuadrant.html

Autor: Seb Rose