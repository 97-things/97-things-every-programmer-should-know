# ¿Cómo usar un Gestor de Errores?

Original: How to Use a Bug Tracker

Como sea que lo llames: bug, defecto o incluso “efecto del lado de
diseño”, no hay manera de alejarse de ellos. Saber enviar un buen
reporte de error y lo que se debe buscar son habilidades para mantener
un proyecto que se lleve bien.

Un buen reporte de error necesita tres cosas:

* Cómo reproducir el error, lo más preciso posible, y la frecuencia con
que esto hará que aparezca el error.

* ¿Qué debería haber ocurrido? Al menos en tu opinión.
* ¿Qué ocurrió realmente? Toda la información que has registrado.

La cantidad y calidad de la información reportada dice mucho acerca de
quién reporta y del error mismo. Los errores con enojo o tensión (“¡esta
función apesta!”) nos dice que los desarrolladores estaban teniendo un
mal momento, pero no más. Un error con gran cantidad de contexto para
que sea más fácil reproducirlo gana el respeto de todo el mundo, incluso
si detiene una liberación.

Los errores son como un conversación, con toda la historia ahí en frente
de todos. No culpes a otros o niegues la existencia del error. En vez de
eso pide más información o considera qué pudiste haber olvidado.

Cambiar el estatus de un error, por ejemplo, de Abierto a Cerrado, es
una declaración pública de lo que se piensa del error. Tomarse el tiempo
de explicar por qué crees que el error debería estar cerrado ahorrará
horas de tedio en justificarlo a directores y clientes frustrados.
Cambiar la prioridad de un error es similar a las declaraciones
públicas, y sólo porque es trivial no significa que alguien está dejando
de usar el producto.

No sobrecargues los campos del error para tu propio propósito. Agregar
“VITAL:” al campo de título de error puede hacer que sea fácil ordenar
los resultados en algún informe, pero hará que eventualmente sea copiado
por otros e inevitablemente será mal escrito o necesitará ser removido
para su uso en algún otro informe. En vez de eso usa un nuevo valor o un
nuevo campo, y documenta cómo el campo se supone debe ser usado, así
otras personas no tienen que repetirlo.

Asegúrate que todos sepan cómo encontrar el error en el que se supone
está trabajando el equipo. Esto se puede hacer mediante una consulta
pública con un nombre obvio. Asegúrate que todos están usando la misma
consulta, y no la actualices sin primero informar al equipo que estás
cambiando algo en lo que todos están trabajando.

Recuerda, un error no es una unidad estándar de trabajo, como tampoco
una línea de código es una unidad precisa de esfuerzo.

Autor: Matt Doar