# Pensando en estados

Original: Thinking in States

La gente en el mundo real tiene una rara relación con los estados. Esta
mañana me paré en la tienda local preparándome para otro día de
convertir cafeína en código. Debido a que mi forma favorita de hacerlo
es tomando un latte, al no encontrar leche me dijo la empleada:

—Disculpa, estamos super-dupe mega faltos de leche.

Para un programador, eso es una sentencia rara. Puedes tener leche o no.
No hay escalas cuando se trata de estar sin el lácteo. Quizás ella
estaba tratando de decirme que les faltará leche por una semana, pero el
resultado era el mismo: día de espresso para mí.

En muchas situaciones del mundo real, la actitud relajada de la gente
con los estados no es un problema. Sin embargo, desafortunadamente,
muchos programadores son también algo despistados con respecto a los
estados y eso sí es un problema.

Considere una tienda de ventas en línea que sólo acepta tarjetas de
crédito y que no factura a los clientes, tiene una clase `Orden`
conteniendo este método:


    public boolean isComplete() {
        return isPaid() && hasShipped();
    }

Razonable, ¿no es así? Bueno, incluso si la expresión es amablemente
extraída en un método en vez de copiar-pegar en todos lados, la
expresión no debería existir del todo. El hecho es que sí resalta un
problema. ¿Por qué? La orden no puede ser enviada antes de que sea
pagada. Por lo tanto, `hasShipped` no puede ser verdadero a menos que
`isPaid` sea verdadero, lo cual hace parte de la expresión redundante.
Por cuestiones de claridad puedes querer aún el `isComplete` en el
código, pero entonces debería verse como esto:


    public boolean isComplete() {
        return hasShipped();
    }

En mi trabajo veo todo el tiempo ambas: revisiones faltantes y
revisiones redundantes. Este ejemplo es pequeño, pero cuando agregas
cancelaciones y reembolso, esto se vuelve más complejo y la necesidad de
un buen manejo de estados se incrementa. En este caso, una orden puede
estar sólo en uno de tres distintos estados:

* En progreso: puede agregar o remover elementos. No se puede enviar.
* Pagado: no puede agregar o remover elementos. Puede ser enviado.
* Enviado: Terminado. No se aceptan más cambios.

Estos estados son importantes y necesitas revisar que estés en el estado
esperado antes de realizar operaciones, y que tú sólo puedas moverte a
un estado legal desde donde estás. En resumen, tienes que proteger tus
objetos cuidadosamente, en los lugares correctos.

Sin embargo, ¿cómo empezar a pensar en estados? Extrayendo expresiones
significativas a los métodos es un buen inicio, pero es sólo un
comienzo. Las bases están en entender las [máquinas de estados][1]. Se
que puedes tener malos recuerdos de tus clases de Ciencias Computacionales,
pero déjalos atrás. Las máquinas de estados no son especialmente difíciles.
 Visualízalas para hacerlas simples de entender y fáciles de hablar de
ellas. Haz tu código Test-drive para desentrañar los estados válidos e
inválidos, las transiciones y mantenlas correctas. Estudia el
[patrón State][2]. Cuando te sientas cómodo, lee sobre
[Diseño por Contrato][3]. Esto ayuda a asegurarte un estado apropiado al
validar los datos de entrada y los objetos por sí mismos al entrar y
salir de cada método público.

Si tu estado no es correcto, hay un bug y estás en riesgo de tirar a la
basura datos si no abortas. Si encuentras que las revisiones de estado
son ruidosas, aprende cómo usar una herramienta de generación de código,
[_weaving_][4] o aspectos para ocultarlos. Independientemente del
enfoque que elijas, pensar en estados hará que tu código sea más simple
y más robusto.

[1]: https://es.wikipedia.org/wiki/Aut%C3%B3mata_finito
[2]: https://en.wikipedia.org/wiki/State_pattern
[3]: https://en.wikipedia.org/wiki/Design_by_Contract
[4]: https://en.wikipedia.org/wiki/Program_transformation

Autor: Niclas Nilsson