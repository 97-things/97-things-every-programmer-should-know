# No claves tu programa en la posición vertical

Original: Don't Nail Your Program into the Upright Position

Una vez escribí una parodia de un _test_ de C++ y satíricamente sugería
la siguiente estrategia de manejo de excepciones:

> Al realizar un montón de constructos `try…catch` a través de tu código
base, podemos, algunas veces, prevenir que nuestra aplicación aborte.
Creemos que el estado resultante es “clavar el cuerpo en posición
vertical”.

Dejando a un lado la frivolidad, realmente estaba resumiendo una lección
que recibí de Doña Amarga Experiencia. Era una clase base de nuestra
aplicación, una biblioteca de C++ hecha en casa. El código había sido
manoseado por muchos programadores en los últimos años. Contenían código
para lidiar con todas las excepciones de escape de todo lo demás. Tomando
el ejemplo de [Yossarian][1] de Catch-22, decidimos o, mejor dicho,
sentimos (decidir implicaba, más bien, pensarlo que estar en la
construcción de este monstruo) que una instancia de esta clase debería
vivir para siempre o morir en el intento.

Al final, interconectamos múltiples manejadores de excepciones.
Mezclamos excepciones estructuradas de Windows con las nativas
(¿recuerdas `try…catch` en C++? Yo tampoco). Cuando las cosas se caían
inesperadamente, tratábamos de llamarlas de nuevo, presionando los
parámetros cada vez más fuerte. Mirando atrás, me gustaría pensar que al
escribir un manejador interno de try…catch dentro de una cláusula catch
de otra, una especie de conciencia se apoderó de mí para haber tomado
accidentalmente la ruda ruta de las buenas prácticas en la aromática
pero insalubre vía de la locura. De cualquier modo, probablemente es
sabiduría retrospectiva.

No necesito decir que cualquier cosa que estuviera mal en las
aplicaciones basadas en esta clase se desvanecía como víctimas de la
Mafia en el muelle, sin dejar atrás algún rastro útil en las burbujas
que indicara qué demonios había sucedido, a pesar de las rutinas de
volcado que supuestamente grabarían el desastre. Eventualmente –un largo
eventualmente– hicimos un balance de lo que habíamos hecho, y
experimentamos vergüenza. Reemplazamos todo el lío con un mecanismo de
informe mínimo y robusto. Pero esto fue como ver muchos accidentes en la
carretera.

No te molestaré más con esto –seguramente nadie más podría haber sido
tan estúpido como nosotros lo fuimos–, excepto una discusión en línea
que tuve recientemente con un individuo, cuyo título académico declaró
que debía saberlo mejor. Estábamos discutiendo código Java en una
transacción remota. Si el código fallaba, él argumentaba, debería
capturar y bloquear la excepción in situ. (“¿Y entonces qué haría con
ello?”, pregunté. “¿Cocinarlo para la cena?”).

Citó la regla del diseñador de UI: NUNCA DEJES QUE EL USUARIO VEA UN
REPORTE DE EXCEPCIÓN, como si esto resolviera el asunto, poniéndolo en
mayúsculas y todo lo demás. Me preguntaba si era el responsable del
código de una de esas pantallas azules de los cajeros automáticos, cuyas
fotos decoran los blogs más endebles, y había sido traumatizado
permanentemente.

De cualquier modo, si llegas a verlo, asienta con la cabeza y sonríe, no
le hagas caso, mientras te deslizas hacia la puerta.


[1]: http://en.wikipedia.org/wiki/Yossarian

Autor: Verity Stob