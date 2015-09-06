# Comenta sólo lo que el código no dice

Original: Comment Only What the Code Cannot Say

La diferencia entre teoría y práctica es más grande en la práctica que
en la teoría –una observación que aplica a los comentarios–. En teoría,
la idea general de comentar código suena como algo útil: ofrece al
lector detalles, una explicación de lo que está pasando. ¿Qué podría ser
más útil que ser útil? En la práctica, sin embargo, los comentarios
frecuentemente se convierten en una plaga. Así como otras formas de
escritura, existen habilidades para escribir buenos comentarios. Mucho
de esa habilidad es saber cuándo no escribirlos.

Cuando el código está mal formado, los compiladores, intérpretes y otras
herramientas se aseguran de objetar. Si el código es, de algún modo,
funcionalmente incorrecto, las revisiones, los análisis estáticos, las
pruebas y el uso diario en un ambiente de producción eliminará muchos de
los errores. ¿Qué me dices de los comentarios? En The Elements of
Programming Style, Kernighan y Plauger notaron que “un comentario tiene
valor de cero (o negativo) si es erróneo”. Y, sin embargo, tales
comentarios ofrecen poco y sobreviven en un código base de una manera
que los errores de codificación nunca pueden. Proporcionan una fuente
constante de distracción y desinformación, un lastre sutil pero
constante en el pensamiento de un programador.

¿Qué hay con los comentarios que no están técnicamente mal, pero no
agregan valor al código? Son ruido. Los comentarios que parlotean el
código no ofrecen algo extra al lector –decir algo una vez en código y
otra vez en lenguaje natural no lo hace más verdadero o más real–. El
código comentado no es código ejecutable, por lo que no tiene un efecto
útil para el lector, ni en tiempo de ejecución. También se vuelve rancio
fácilmente. Los comentarios relacionados a la versión y el código
comentado tratan de abordar preguntas sobre las versiones y la historia.
Estas preguntan ya han sido respondidas, de forma más eficiente, por las
herramientas de control de versiones.

Una prevalencia de comentarios ruidosos e inconsistentes en el código
base anima a los programadores a ignorar todos los comentarios, ya sea
saltándolos o tomando medidas activas para ocultarlos. Los programadores
tienen muchos recursos y le darán vuelta a cualquier cosa que se perciba
como dañino: plegando los comentarios; cambiando el esquema de color,
así los comentarios y el color de fondo se igualan; creando scripts para
filtrar comentarios. Para salvar el código base de las malas
aplicaciones de la ingenuidad del programador, y reducir el riesgo de
pasar por alto cualquier comentario de valor genuino, los comentarios
deberían ser tratados como si fueran código. Cada comentario debería
agregar algo de valor al lector, de otro modo es un desperdicio que
debería ser removido o reescrito.

¿Qué lo califica como valioso? Los comentarios deberían decir algo que
¿el código no hace y no puede decir. Un comentario que explica lo que
¿una pieza de código ya debería decir es una invitación para cambiar la
¿estructura del código o las convenciones de codificación para que hable
¿por sí mismo. En vez de compensar la pobreza en el nombre de los
¿métodos o de las clases, renómbralos. En vez de comentar secciones en
¿funciones largas, extrae las funciones pequeñas cuyos nombres capturen
¿las intenciones de las anteriores partes. Intenta expresar tanto como
¿sea posible a través del código. Cualquier déficit entre lo que puedes
¿expresar en código y lo que deseas expresar en su totalidad se
¿convierte en un candidato plausible para un comentario útil. Comenta lo
¿que el código no puede decir, no lo que el código no dice.

Autor: Kevlin Henney