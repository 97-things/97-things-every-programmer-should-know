# Conoce tu IDE

Original: Know Your IDE

En la década de los ochenta nuestros entornos de programación eran, por
lo general, nada mejor que editores de texto glorificados… si teníamos
suerte. El resaltado de sintaxis, que damos por sentado hoy en día, era
un lujo que ciertamente no estaba disponible para todos. Los _Pretty
Printers_ para formatear bien nuestro código eran usualmente
herramientas externas que tenían que ser ejecutadas para corregir
nuestro espaciamiento. Los depuradores eran también programas separados
ejecutándose paso a paso a través de nuestro código, pero con un montón
de teclazos crípticos.

Durante la década de los noventa las compañías comenzaron a reconocer el
potencial de ingresos que pudieran derivarse de equipar a los
programadores con mejores y más útiles herramientas. El Entorno
Integrado de Desarrollo (IDE, por sus siglas en inglés) combinaba las
características de edición previas con un compilador, un depurador,
Pretty Printer y otras herramientas. Durante ese tiempo, los menús y el
ratón también se volvieron populares, lo cuál significaba que los
desarrolladores ya no necesitaban aprender combinaciones de teclas
crípticos para usar sus editores. Podían simplemente seleccionar su
comando en el menú.

En el siglo XXI los IDE se convirtieron en un lugar tan común que eran
regalados por las compañías que deseaban ganar un segmento del mercado
en otras áreas. El IDE moderno está equipado con una increíble variedad
de características. Mi favorita es la refactorización automatizada,
particularmente la _Extracción de Método_, en el cual puedo seleccionar
y convertir un fragmento de código en un método. La herramienta de
refactorización recogerá todos los parámetros que deben ser transferidos
al método, lo cuál hace extremadamente fácil modificar código. Mi IDE
detectará incluso otro fragmento de código que podría también ser
reemplazado por este método y preguntarme si deseo reemplazarlo también.

Otra característica sorprendente en los IDE modernos es la capacidad de
hacer cumplir las reglas de estilo dentro de una empresa. Por ejemplo,
en Java, algunos programadores han empezado a hacer todos los parámetros
como `final` (lo cual, en mi opinión, es una pérdida de tiempo). Sin
embargo, como ellos lo tienen como una regla de estilo, todo lo que
necesitaría hacer a continuación es configurarlo en mi IDE: obtendría
algunas advertencias por cada parámetro que no fuese `final`. Las reglas
de estilo también pueden ser utilizadas para encontrar errores
probables, tales como comparar objetos autoboxed para la igualdad de
referencia, por ejemplo, usando == en los valores primitivos que están
autoboxed en referencias a objetos.

Desafortunadamente, los IDE modernos no requieren de invertir esfuerzo
para aprender a usarlos. Cuando programé por primera vez en C bajo Unix
tuve que pasar un poco de tiempo aprendiendo cómo trabajaba el editor
vi, debido a su curva de aprendizaje. Este tiempo gastado pagó por
adelantando bellamente al paso de los años. Incluso he escrito el
borrador de este artículo con vi. Los IDE modernos tienen una curva de
aprendizaje muy gradual, la cual puede tener como consecuencia que nunca
progresamos más allá del uso básico de la herramienta.

Mis primeros pasos al aprender un IDE es memorizar los atajos de
teclado. Ya a que mis dedos están en el teclado cuando estoy escribiendo
mi código, presionar _Ctrl+Shift+I_ para alinear una variable me ahorra
tener que romper mi flujo, navegar por el menú con el ratón interrumpe
este flujo. Estas interrupciones lleva a cambios de contexto
innecesarios, haciéndome mucho menos productivo si trato de hacer todo
por el camino perezoso. La misma regla también aplica a las habilidades
del teclado: aprende a teclear, no te arrepentirás del tiempo invertido
por adelantado.

Por último, como programadores tenemos herramientas de flujo Unix que
pueden ayudarnos a manipular el código. Como si durante una
revisión de código me doy cuenta de que los programadores han nombrado 
muchas de sus clases de la misma forma, puedo encontrarlas fácilmente
usando las herramientas find, sed, sort, uniq y grep, por ejemplo:


    find . -name "*.java" | sed 's/.*\///' | sort | uniq -c | grep -v "^ *1 " | sort -r


Esperamos que un plomero que llega a nuestra casa sea capaz de usar su
soplete. Pasemos un poco de tiempo estudiando cómo ser más efectivos con
nuestro IDE.

Autor: Heinz Kabutz