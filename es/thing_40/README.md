# Haz las Interfaces fáciles de usar correctamente y difíciles de usar incorrectamente

Original: Make Interfaces Easy to Use Correctly and Hard to Use Incorrectly

Una de las tareas más comunes en el desarrollo de software es la
especificación de la interfaz. Las interfaces ocurren al más alto nivel
de abstracción (interfaces de usuario), en la más baja (interfaces de
función) y en los niveles intermedios (interfaces de clases, de
bibliotecas, etcétera). Independientemente de que estés trabajando con
el usuario final para especificar cómo estará interactuando con un
sistema, colaborando con desarrolladores para especificar un API o
declarando funciones privadas para una clase, el diseño de interfaz es
una parte importante de tu trabajo. Si lo haces bien, será un placer
usar tus interfaces y aumentará la productividad de los demás. Si lo
haces pobremente, tus interfaces serán la fuente de frustraciones y
errores.

Las buenas interfaces son:

* Fáciles de usar correctamente. La gente que usa una interfaz bien
diseñada casi siempre usa la interfaz correctamente, porque es la ruta
de menor resistencia. En una Interfaz Gráfica de Usuario (GUI) siempre
hacen clic en el ícono, botón o entrada de menú correcta, debido a que
es obvio y algo fácil de hacer. En una API casi siempre pasan los
parámetros correctos con el valor correcto, debido a que es la manera
más natural. Con interfaces que son fáciles de usar correctamente, la
cosas funcionan.
* Difíciles de usar incorrectamente. Las buenas interfaces se anticipan a
los errores que la gente comete y hace que sea difícil –idealmente
imposible– realizarlos. Una GUI debería deshabilitar o remover comandos
que no tengan sentido en el contexto actual, por ejemplo, o una API
debería eliminar la secuencia de argumentos al permitir que los
parámetros sean pasados en cualquier orden.

Una buena manera de diseñar interfaces que son fáciles de usar
correctamente es hacer ejercicios antes de que existan. Simula una GUI
–en un pizarrón o usando fichas en una mesa– y juega con ellos antes de
que cualquier código haya sido creado. Escribe llamadas a la API antes
de que las funciones hayan sido declaradas. Revisa los casos de uso
comunes y especifica cómo quieres que se comporten las interfaces. ¿En
qué quieres que puedan hacer clic? ¿Qué quieres pasarle? Las interfaces
fáciles de usar parecen naturales, debido a que te dejan hacer lo que
quieres hacer. Es más frecuente dar con esas interfaces si las
desarrollas desde el punto de vista de los usuarios (esta perspectiva es
una de las fortalezas de la programación test-first).

Hacer las interfaces difíciles de usar incorrectamente requiere dos
cosas. Primero, debes anticiparte a los errores que los usuarios podrían
hacer y encontrar la manera de prevenirlos. Segundo, debes observar cómo
una interfaz es usada erróneamente durante las primeras liberaciones y
modifica la interfaz –¡sí, modificar la interfaz!– para prevenir tales
errores. La mejor manera de prevenir el uso incorrecto es hacer tal uso
imposible. Si los usuarios siguen queriendo hacer un “deshacer” en una
acción irrevocable, intenta hacer la acción revocable. Si ellos siguen
pasando un valor erróneo a la API, mejor modifica la API para tomar los
valores que el usuario quiere pasar.

Sobre todo, recuerda que las interfaces existen para la conveniencia de
sus usuarios, no la de sus implementadores.

Autor: Scott Meyers