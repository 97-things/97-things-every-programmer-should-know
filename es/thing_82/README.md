# Las pruebas son el rigor ingenieril del desarrollo de software

Original: Testing Is the Engineering Rigor of Software Development

Los desarrolladores aman usar metáforas torturadoras cuando se trata de
explicar a los miembros de su familia, esposas y otros no técnicos qué
es lo que hacen. Con frecuencia recurrimos a la construcción de puentes
y otras disciplinas de ingenierías “duras”. Todas estas metáforas caen
rápidamente, sin embargo, cuando intentas presionar hacia a ellas
demasiado duro. Resulta que el desarrollo de software no es como
muchas de las otras disciplinas de la ingeniería, “duras” en muchos
aspectos importantes.

Comparado con las ingenierías “duras”, el mundo del desarrollo de
software está en el mismo lugar donde los constructores de puentes
estaban cuando la estrategia común era construir el puente y lanzar algo
pesado sobre él. Si se mantenía de pie, era un buen puente. Si no,
bueno, era tiempo de regresar a la mesa de dibujo. Durante los últimos
miles de años, los ingenieros han desarrollado las matemáticas y física
que usan para una solución estructural sin tener que construirlo para
ver lo que hace. No tenemos nada como eso en el software, y quizás
nunca lo tendremos, porque el software es, de hecho, algo muy diferente.
Para una exploración profunda de la comparación entre “ingeniería” de
software y la ingeniería normal, lee el libro ["What's Software Design"][1],
escrito por Jack Reeves en C++ Journal en 1992, es un clásico. A pesar
de que fue escrito hace casi dos décadas, es aún remarcablemente exacto.
Él pintó un panorama sombrío en esta comparación, pero lo que faltaba en
1992 era una fuerte prueba _Ethos_ para el software.

Probar cosas “duras” es difícil porque tienes que construirlo para
probarlo, lo cual desalienta la construcción especulativa sólo para ver
qué pasará. Pero el proceso de construcción de software es ridículamente
barato. Hemos desarrollado todo un ecosistema de herramientas que hacen
que sea fácil hacer precisamente eso: pruebas unitarias, objetos de
imitación, arneses de pruebas y un montón de otras cosas. A otros
ingenieros les encantaría ser capaces de hacer algo y probarlo bajo
condiciones realistas. Como desarrolladores de software debemos abrazar
las pruebas como la verificación primaria (pero no la única) para el
software. En lugar de esperar por algún tipo de cálculo de software, ya
tenemos las herramientas a nuestra disposición para asegurar buenas
prácticas de ingeniería. Visto de esta manera, ahora tenemos municiones
contra los directivos que dicen: “No tenemos tiempo para pruebas”. Un
constructor de puentes nunca escuchará de su jefe: “No te molestes en
hacer el análisis estructural para esa construcción, tenemos un plazo
muy corto”. El reconocimiento de que la prueba es, de hecho, el camino
para la reproducción y la calidad de software nos permite, como
desarrolladores, regresar los argumentos contra su irresponsabilidad
profesional.

Las pruebas toman su tiempo, al igual que el análisis estructural lleva
su tiempo. Ambas actividades garantizan la calidad del producto final.
Es hora de que los desarrolladores tomen el mando de la responsabilidad
de lo que producen. Las pruebas por sí mismas no son suficientes, pero
son necesarias. Probar es el rigor ingenieril del desarrollo de
software.


[1]: http://www.developerdotstar.com/mag/articles/reeves_design.html

Autor: Neal Ford