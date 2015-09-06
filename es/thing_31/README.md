# Dos fallos pueden hacer un acierto (y es difícil de arreglar)

Original: Two Wrongs Can Make a Right (and Are Difficult to Fix)

El código nunca miente, pero puede contradecirse. Algunas
contradicciones llevan a esos momentos de: “¿cómo es posible que esto
funcione?”.

En una [entrevista][1], el diseñador principal del software del módulo
lunar Apolo 11, Allan Klumpp, reveló que el software que controlaba los
motores tenía un error que hacía el módulo de aterrizaje inestable. Sin
embargo, otro error fue compensado por el primero y el software fue
usado por los aterrizajes lunares del Apolo 11 y 12 antes de que el
error fuera encontrado y arreglado.

Considera una función que retorna un estatus de finalización. Imagina
que retorna `false` cuando debería regresar un `true`. Ahora imagina que
la llamada de función olvida comprobar el valor de retorno. Todo
funciona bien hasta que un día alguien nota la falta de verificación y
la inserta.

O considera una aplicación que almacena su estado en un documento XML.
Imagina que uno de los nodos está escrito incorrectamente como
“TimeToLive” en vez de “TimeToDie”, como la documentación dice que
debería. Todo parece estar bien mientras el código de escritura y el
código de lectura contienen ambos el mismo error. Pero arregla uno, o
agrega una nueva aplicación de lectura del mismo documento, y la
simetría se rompe, al igual que el código.

Cuando dos defectos en el código crean un defecto visible, el enfoque
metodológico para arreglar la falla puede, por sí mismo, romperlo. El
desarrollador recibe un reporte de error, encuentra el defecto, lo
arregla y lo vuelve a probar. Sin embargo, el fallo reportado aún
ocurre, debido a que un segundo defecto está en funcionamiento. Así que
el primer arreglo se quita, el código es inspeccionado hasta que el
segundo defecto es encontrado, y un arreglo se aplica. Pero el primer
defecto ha regresado, el fallo reportado aún se ve, así que se deshace
el segundo arreglo. El proceso se repite, pero ahora el desarrollador ha
desestimado dos posibles soluciones y está buscando una tercera, que
nunca va a funcionar.

La interacción entre dos defectos de código que aparecen como un defecto
visible no sólo hace difícil arreglar el problema, además, lleva a los
desarrolladores a callejones sin salida, sólo para descubrir que
intentaron la respuesta correcta desde el inicio.

Esto no pasa sólo en el código: el problema también existe en los
documentos de requerimientos escritos. Y puede extenderse, viralmente,
de un lugar a otro. Un error en el código compensa un error en la
descripción escrita.

Puede extenderse a la gente también: los usuarios aprenden que cuando la
aplicación dice “Izquierda” se refiere a la “Derecha”, así que ajustan
su comportamiento, incluso lo pasan al nuevo usuario: “recuerda que la
aplicación dice que hagas clic al botón izquierdo cuando realmente se
refiere al botón derecho”. Arregla ese error y, de repente, los usuarios
necesitan reentrenamiento.

Fallos sencillos pueden ser fáciles de ver y de arreglar. Son los
problemas con múltiples causas, que necesitan múltiples cambios, los que
son difíciles de resolver. En parte es porque los problemas fáciles
tienden a ser arreglarlos con relativa rapidez y se quedan los más
difíciles para una fecha posterior.

No hay un consejo simple que se pueda dar en cómo localizar fallos
surgidos de defectos simpatéticos. Es necesario darse cuenta de la
posibilidad, una cabeza clara y voluntad de considerar todas las
posibilidades.


[1]: http://www.netjeff.com/humor/item.cgi?file=ApolloComputer

Autor: Allan Kelly