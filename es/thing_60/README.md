# Mejora el código quitándolo

Original: Improve Code by Removing It

_Menos es más_. Es una máxima un poco trillada, pero algunas veces es
cierto.

Una de las mejoras que he hecho en nuestro código base en las últimas
semanas es eliminar trozos de él.

Hemos escrito el software siguiendo los principios de XP, incluyendo
YAGNI (You Aren’t Gonna Need It [No vas a necesitarlo]). La naturaleza
humana es así, inevitablemente nos quedamos cortos en unos pocos
lugares.

Observé que el producto estaba tomando demasiado tiempo para ejecutar
ciertas tareas, tareas sencillas que deberían ser casi instantáneas.
Esto era porque estaban sobreimplementadas; adornadas con campanas y
silbatos adicionales que no eran requeridos, pero que en ese momento
parecían una buena idea.

Simplifiqué el código, mejorando el rendimiento del producto y
reduciendo el nivel de entropía global del código al quitar las
características infractoras del código base. Afortunadamente, mis
Pruebas Unitarias me dijeron que no había roto nada durante la
operación.

Una experiencia sencilla y completamente satisfactoria.

Así que ¿por qué terminó ahí ese código innecesario? ¿Por qué un
programador sintió la necesidad de escribir código adicional y cómo pasó
la última revisión o el proceso entre pares? Es casi seguro que sucedió
algo como esto:

* Era un poco de diversión extra y el programador quería escribirlo.
(Sugerencia: escribir código porque agrega valor, no porque te
divierte).
* Alguien pensó que podría ser necesario en el futuro, así que sintió que
era mejor escribirlo ahora. (Sugerencia: esto no es YAGNI. Si no lo
necesitas en este momento, no lo escribas ahora mismo).
* No parecía ser un gran “extra”, así que era más fácil implementarlo en
vez de regresar con el cliente para ver si era requerido. (Sugerencia:
siempre toma más tiempo escribir y mantener código adicional. Y el
cliente siempre está disponible. Una partecita extra de código se vuelve
una bola de nieve en descenso con el paso del tiempo, convirtiéndose en
una gran parte de trabajo que necesita ser mantenido).
* El programador inventó requisitos adicionales que no fueron
documentados, ni discutidos para justificar la función adicional. El
requerimiento era en realidad falso. (Sugerencia: los programadores no
establecen los requerimientos del sistema; el cliente sí).

¿En qué trabajas ahora mismo? ¿Es todo necesario?

Autor: Pete Goodliffe