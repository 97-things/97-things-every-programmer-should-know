# Un comentario acerca de los comentarios

Original: A Comment on Comments

En mi primera clase de programación en la universidad, el profesor nos
entregó dos hojas de codificación BASIC. En el pizarrón, se leía la
asignatura: “Escribir un programa para ingresar y promediar 10
puntuaciones de bolos”. A continuación, el profesor salió de la
habitación. ¿Qué tan difícil puede ser? No recuerdo mi solución final,
pero estoy seguro que tenía un bucle FOR/NEXT en él y no podía haber
sido de más de 15 líneas de longitud en total. Las hojas de codificación
–para los niños que leen esto, sí, solíamos escribir el código a mano
antes de ingresarlo a la computadora– permitían alrededor de 70 líneas
de código cada una. Estaba confundido sobre por qué el maestro nos había
dado dos hojas. Debido a que mi manuscrito había sido atroz, usé la
segunda en transcribir mi código muy cuidadosamente, esperando obtener
un par de puntos extras por el estilo.

Para mi sorpresa, cuando me regresaron la asignatura, al inicio de la
siguiente clase, obtuve una calificación apenas aprobatoria. (Sería un
presagio para mí el resto del tiempo en la universidad). Garabateado en
la parte superior de mi cuidadosamente copiado código: “¿Sin
comentarios?”.

No era suficiente que el profesor y yo supiéramos lo que se suponía
haría el programa. Parte de los puntos de la asignatura era enseñarme
que mi código debía explicarse por sí mismo al programador después de
mí. Es una lección que no he olvidado.

Los comentarios no son malignos. Son necesarios en la programación tanto
como los constructos más básicos de ramificaciones o ciclos. Los
lenguajes más modernos tienen una herramienta similar a javadocs que
analiza comentarios con el formato adecuado para construir
automáticamente la documentación del API. Esto es un buen comienzo, pero
no es suficiente. Dentro de tu código debería haber explicaciones acerca
de lo que se supone que está haciendo. Codificar con el viejo adagio:
“Si fue difícil de escribir, debe ser difícil de leer”, hace un pobre
favor a tu cliente, tu empleador, tus colegas o tu propio futuro.

Por otro lado, puedes irte demasiado lejos con tus comentarios.
Asegúrate de que clarifican el código, pero no lo obscurecen. Espolvorea
tu código con comentarios relevantes explicando qué debe realizar. El
comentario principal debería darle a cualquier programador suficiente
información para usarlo sin tener que leerlo, mientras que los
comentarios en línea deberían asistir al siguiente desarrollador que lo
arregle o lo extienda.

En un trabajo estuve en desacuerdo con una decisión de diseño hecha por
mis superiores. Por intentar ser sarcástico, como suelen ser los
programadores jóvenes, copié el texto del correo en el cual se me
instruía a usar su diseño en el bloque del comentario principal del
archivo. Sucedió que los administradores de esta tienda en particular
revisaron el código cuando lo envié. Fue mi primera introducción al
término “despido por límite de profesión”.

Autor: Cal Evans