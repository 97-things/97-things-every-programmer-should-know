# Aprende a decir "Hola, Mundo"

Original: Learn to Say "Hello, World"

Paul Lee, nombre de usuario “leep”, comúnmente conocido como Hoppy,
tenía la reputación de experto local en temas de programación.
Necesitaba ayuda. Caminé hacia el escritorio de Hoppy y le pregunté:

— ¿Podrías echar un vistazo al código por mí?

— Seguro —dijo Hoppy—, toma una silla.

Tuve el cuidado de no derribar las latas vacías de soda apiladas en una
pirámide detrás de él.

—¿Qué código?

—En una función en un archivo —le dije.

—Echemos un vistazo a esta función.

Hoppy alejó una copia de K&R y deslizó su teclado frente a mí. ¿Dónde
está el IDE? Aparentemente Hoppy no tenía un IDE ejecutándose, sólo
algún editor que yo no podía operar. Tomó de nuevo el teclado. Unos
cuantos teclazos después y teníamos el archivo abierto –era un archivo
algo grande– y estamos observando la función –era una función algo
grande–. Él avanzó unas páginas hacia el bloque condicional que quería
cuestionarle.

— ¿Qué haría realmente esta cláusula si x es negativo? —le pregunté—.
¿Sin duda, es un error.

Había estado probando toda la mañana tratando de encontrar una manera de
forzar que x fuera negativo, pero la gran función en un gran archivo era
parte de un gran proyecto, y el ciclo de recompilar y volver a ejecutar
mis experimentos me estaba venciendo. ¿No podría un experto como Hoppy
simplemente decirme la respuesta?

Hoppy admitió que estaba seguro. Para mi sorpresa, no buscó en K&R. En
vez de ello, copió el bloque de código en un nuevo buffer del editor, lo
reindentó y lo envolvió en una función. Un poco más tarde codificó una
función `main` y lo cicló, pidiendo al usuario valores de entrada,
pasándolos a la función e imprimiendo el resultado. Guardó el buffer
como un nuevo archivo, `tryit.c`. Todo esto lo podría haber hecho yo
mismo, creo que quizá no tan rápido. Sin embargo, su siguiente paso fue
maravillosamente simple y, para ese tiempo, un poco extraño para mi
manera de trabajar

    $ cc tryit.c && ./a.out

¡Mira! Su programa, concebido unos pocos minutos antes, ahora estaba en
marcha y funcionando. Probamos unos cuantos valores y confirmó mis
sospechas (¡había tenido razón sobre algo!) y entonces cotejó la sección
correspondiente de K&R. Le agradecí a Hoppy y me fui, una vez más,
teniendo cuidado de no molestar su pirámide de latas de soda.

De regreso a mi escritorio, cerré mi IDE. Me había hecho tan familiar al
trabajo con un gran proyecto con un gran producto que había empezado a
pensar qué debía hacer. Una computadora de propósito general puede
realizar pequeñas tareas también. Abrí un editor de texto y empecé a
escribir.


    #include <stdio.h>

    int main() {
        printf("Hello, World\n");
        return 0;
    }


Autor: Thomas Guest