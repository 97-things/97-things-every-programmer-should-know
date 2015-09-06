# Toma ventaja de las herramientas de análisis de código

Original: Take Advantage of Code Analysis Tools

El valor de las pruebas es algo que está siendo inculcado a los
desarrolladores de software desde las primeras etapas de su jornada de
programación. En años recientes el aumento de las pruebas unitarias,
desarrollo basado en pruebas (test-driven), y los métodos ágiles han
visto un surgimiento de interés en hacer más pruebas en todas las fases
del ciclo de desarrollo. Sin embargo, las pruebas es sólo una de las
muchas herramientas que puedes usar para mejorar la calidad del código.

Lejos, en la neblina del tiempo, cuando C era todavía un nuevo fenómeno,
el tiempo de CPU y el almacenamiento de cualquier tipo eran un bien
escaso. Los primeros compiladores de C eran conscientes de esto, así que
reducían el número de pases que hacían a través del código quitando
algunos análisis semánticos. Esto significaba que el compilador
comprobaba sólo un pequeño subconjunto de errores que podían ser
detectados al compilar. Para compensarlo, Stephen Johnson escribió una
herramienta llamada _lint_ –la cual remueve la pelusa de tu código– que
implementaba algunos de los análisis estáticos que habían sido quitados
por el compilador de C. Las herramientas de análisis estático, sin
embargo, ganaron la reputación de obtener gran número de advertencias
con falsos positivos y avisos sobre convenciones estilísticas que no
siempre es necesario seguir.

El panorama actual de los lenguajes, compiladores y herramientas de
análisis estático es muy diferente. La memoria y el tiempo de CPU ahora
son relativamente baratos, por lo que los compiladores se puede permitir
detectar más errores. Casi cualquier lenguaje cuenta con, al menos, una
herramienta que comprueba violaciones de estilo, errores comunes y
algunos errores astutos que pueden ser difíciles de capturar, tales como
potenciales desreferencias de punteros nulos. Las herramientas más
sofisticadas, como _Split_ para C o _Pylint_ para Python, son
configurables, lo que significa que puedes escoger cuáles errores y
advertencias emite la herramienta con un archivo de configuración, a
través de la línea de comandos o en tu IDE. _Splint_ incluso te
permitirá anotar el código con comentarios que te dará mejores consejos
sobre cómo funciona tu programa.

Si todo lo demás falla y te encuentras buscando errores simples o
violación de normas que no son capturados por tu compilador, IDE o
herramienta _lint_, entonces siempre puedes llevar tu propio revisor
estático. Esto no es tan difícil como suena. La mayoría de los
lenguajes, particularmente aquellos etiquetados como dinámicos, exponen
su árbol sintaxis abstracto y herramientas de compilación como parte de
su biblioteca estándar. Vale la pena saber los rincones polvorientos de
la biblioteca estándar que son usados por el equipo de desarrollo del
lenguaje que estás usando, ya que frecuentemente contienen gemas ocultas
que son útiles para análisis estático y pruebas dinámicas. Por ejemplo,
la biblioteca estándar de Python contiene un desensamblador que te dice
el código bytecode usado para generar algún código compilado o código
objeto. Esto suena como una herramienta obscura para escritores de
compiladores en el equipo python-dev, pero es realmente útil para las
situaciones diarias. Una cosa que puede desensamblar esta biblioteca es
el último trazo de pila (_stack trace_), dándote una retroalimentación
sobre exactamente cuál instrucción de _bytecode_ lanzó la última
excepción no capturada.

Así que no dejes que las pruebas sean el final de tu aseguramiento de
calidad; toma ventaja de las herramientas de análisis y no tengas miedo
de complicarte.

Autor: Sarah Mount