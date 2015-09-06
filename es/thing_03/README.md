# Antes de Refactorizar

Original: Before You Refactor

En algún punto todo programador necesitará refactorizar código
existente. Pero antes de hacerlo por favor piensa en lo siguiente, ya
que tú y otras personas podrían ahorrar una gran cantidad de tiempo (y
dolor):

* El mejor enfoque para la reestructuración comienza por hacer un balance
del código base existente y las pruebas escritas contra ese código. Esto
ayudará a entender las fortalezas y debilidades del código en su estado
actual, por lo que puedes asegurar que retienes los puntos fuertes,
mientras evitas los errores. Todos pensamos que podemos hacerlo mejor
que el sistema actual… hasta que terminamos con algo que no es mejor –o
incluso peor– que la anterior encarnación, debido a que fallamos en
aprender de los errores existentes en el sistema.
* Evita la tentación de volver a escribir todo. Es mejor reusar tanto
código como sea posible. No importa que tan feo sea el código, ya ha
sido probado, revisado, etcétera. Desechar el código viejo
–especialmente si está en producción– significa que estás desechando
meses (o años) de pruebas sobre el aguerrido código que podría haber
tenido ciertos atajos y correcciones críticas de errores de los cuales
no estás enterado. Si no tomas esto en cuenta, el nuevo código que se
escriba podría terminar mostrando el mismo error misterioso que fue
reparado en el código antiguo. Esto desperdiciará un montón de tiempo,
esfuerzo y conocimiento adquiridos a través de los años.
* Muchos cambios incrementales son mejores que un cambio masivo. Los
cambios incrementales permiten medir el impacto en el sistema más
fácilmente a través de la retroalimentación, como las pruebas. No es
divertido ver cientos de pruebas fallidas después de realizar un cambio.
Esto puede conducir a la frustración y presión que puede, a su vez, dar
lugar a malas decisiones. Un par de pruebas fallidas es fácil de manejar
y provee un enfoque más manejable.
* Después de cada iteración es importante asegurar que las pruebas
existentes pasan. Agrega nuevas pruebas si las pruebas existentes no son
suficientes para cubrir los cambios realizados. No deseches las pruebas
del código antiguo sin la debida consideración. En la superficie algunas
de estas pruebas podrían no parecer aplicables a tu nuevo diseño, pero
será de utilidad el esfuerzo de investigación a fondo de las razones por
las cuales estas pruebas en particular fueron añadidas.
* Las preferencias personales y el ego no deben ponerse en el camino. Si
algo no está roto, ¿para qué arreglarlo? Que el estilo o la estructura
del código no se ajuste a tus preferencias personales no es una razón
válida para reestructurarlo. Pesar que podrías hacer un mejor trabajo
que el programador previo no es una razón válida tampoco.
* La nueva tecnología es razón insuficiente para refactorizar. Una de las
peores razones para refactorizar se debe a que el código actual está muy
por detrás de las buenas tecnologías que tenemos hoy en día, y creemos
que un nuevo lenguaje o framework puede hacer las cosas mucho más
elegantemente. A menos que un análisis de costo-beneficio muestre que el
nuevo lenguaje o framework beneficiará la funcionalidad, mantenimiento o
productividad, es mejor dejar las cosas como están.
* Recuerda que los humanos cometen errores. Reestructurar no siempre
garantiza que el nuevo código será mejor o tan bueno como el intento
anterior. He visto y sido parte de muchos intentos de reestructuración
fallidos. No fue bonito, pero fue humano.

Autor: Rajith Attapattu