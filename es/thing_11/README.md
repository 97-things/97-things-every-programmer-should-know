# Averigua qué haría el usuario (tú no eres el usuario)

Original: Ask "What Would the User Do?" (You Are not the User)

Todos tendemos a asumir que los demás piensan como nosotros, pero no es
así. Los psicólogos lo llaman efecto del falso consenso. Cuando la gente
piensa o actúa de un modo diferente a nosotros es muy probable que
(subconscientemente) los consideremos defectuosos en cierto modo.

Este prejuicio explica por qué a los programadores les cuesta tanto
ponerse en el lugar de los usuarios. Los usuarios no piensan como
programadores. Para empezar, pasan mucho menos tiempo usando
computadoras y no saben, ni les interesa, cómo funcionan. Esto significa
que no pueden recurrir a ninguna de las pilas de técnicas para resolver
problemas que son tan comunes entre programadores. Los usuarios no saben
reconocer los patrones ni indicaciones que los programadores manejan
para trabajar y lidiar con las interfaces.

La mejor manera de entender cómo piensan los usuarios es observándolos.
Pídele a un usuario que realice una tarea utilizando una aplicación
similar a la que estás desarrollando. Asegúrate de que sea una tarea en
serio: “agrega una columna de números” está bien; “calcula tus gastos
del mes pasado” es mejor. Evita tareas muy específicas, como “¿puedes
seleccionar estas celdas y agregar una fórmula SUMA debajo?”; es una
pregunta algo obvia. Haz que el usuario te explique en detalle el
proceso que realiza. No lo interrumpas. No intentes ayudarlo. Pregúntate
todo el tiempo por qué está haciendo eso.

Lo primero que notarás es que los usuarios realizan una serie de cosas
de manera similar. Intentan completar las tareas en el mismo orden y
cometen los mismos errores en los mismos lugares. Deberías diseñar tu
aplicación en torno a esta conducta base. Esto es algo que difiere de
las reuniones de diseño, en las cuales se suelen hacer preguntas como:
“¿y si el usuario quisiera…?”. Estos planteamientos conducen al
desarrollo de funciones demasiado complejas y generan confusión sobre lo
que los usuarios realmente desean. Observarlos eliminará esta confusión.

Verás que los usuarios suelen atascarse. Cuando tú te atascas, buscas
una solución. Cuando los usuarios se atascan, reducen su foco de
atención; se les vuelve más complicado ver una solución al problema en
otro lugar de la pantalla. Ésta es una de las razones por las que los
textos de ayuda son una mala solución al mal diseño de interfaces de
usuario. Si debes agregar instrucciones o textos de ayuda, asegúrate de
hacerlo justo al lado de las áreas problemáticas. Esta limitación de los
usuarios es el motivo por el que los tooltips son más útiles que los
menús de ayuda.

Los usuarios tienden a salir del paso de alguna manera. Encontrarán algo
que funcione y se aferrarán a ello sin importar lo complejo que sea,
pero es mejor proveer un modo obvio de hacer las cosas que dos o tres
atajos.

También te encontrarás con que hay una marcada diferencia entre lo que
los usuarios dicen que quieren y lo que realmente quieren. Lo cual es
preocupante, ya que para averiguar los requerimientos lo normal es
preguntarles. Es por esto que el mejor modo de relevar los
requerimientos es observando a los usuarios. Pasar una hora con ellos es
mucho más informativo que pasar un día suponiendo qué quieren.

Autor: Giles Colborne