# No tengas miedo de romper cosas

Original: Don't Be Afraid to Break Things

Todos los que tiene experiencia en el sector indudablemente han
trabajado en un proyecto en el que el código base era, en el mejor de
los casos, precario. El sistema es factorizado pobremente y cambiar
alguna cosa siempre lleva a descomponer otra característica no
relacionada. Cada vez que se añade un módulo, la meta del programador es
cambiar lo menos que sea posible, y contener la respiración durante cada
lanzamiento. Esto es el equivalente de jugar _Jenga_ con vigas de acero
en un rascacielos, y se dirige a un desastre.

La razón por la que realizar cambios es tan destroza-nervios se debe a
que el sistema está enfermo. Necesita un médico, de lo contrario su
condición sólo empeorará. Ya sabes lo que está mal en tu sistema, pero
tienes miedo de romper los huevos para hacer tu omelet. Un cirujano
experto sabe que deben hacerse cortes para operar, pero también sabe que
esos cortes son temporales y se curan. El resultado final de la
operación bien vale el dolor inicial y el paciente debe sanar y estar en
un mejor estado del que tenía antes de la operación.

No tengas miedo de tu código. ¿A quién le importa si algo se rompe
temporalmente mientras mueves las cosas? Un miedo paralizante a los
cambios es lo que tiene a tu proyecto en este estado, de entrada.
Invertir el tiempo para refactorizar se pagará por sí mismo varias veces
durante el tiempo de vida de tu proyecto. Un beneficio adicional es que
la experiencia de tu equipo al lidiar con el sistema enfermo los hace
expertos en saber cómo debería funcionar. Aplica este conocimiento en
vez de resentirte. Trabajar con un sistema que odias es algo en lo que
nadie debería gastar su tiempo.

Redefine las interfases internas, reestructura módulos, refactoriza
código copiado-pegado y simplifica tu diseño reduciendo dependencias.
Puedes reducir significativamente la complejidad del código eliminando
“casos límite”, que, a menudo, resultan de características
incorrectamente acopladas. Realiza lentamente la transición de la vieja
estructura a la nueva, haciendo pruebas en el camino. Tratar de realizar
una larga refactorización en “un gran golpe” causará suficientes
problemas como para hacerte considerar abandonar todo el esfuerzo a la
mitad del camino.

Sé el cirujano que no tiene miedo a cortar las partes enfermas para
hacer espacio a la cura. La actitud es contagiosa e inspirará a otros a
empezar en los proyecto de limpieza que han estado posponiendo. Mantén
una lista de “higiene” de las tareas que el equipo siente que valen la
pena para el bien general del proyecto. Convence a la administración de
que, a pesar de que estas tareas podrían no producir resultados visibles,
reducirán los gastos y agilizarán las futuras versiones. Nunca dejes de
preocuparte por la “salud” general del código.

Autor: Mike Lewis