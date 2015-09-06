# ¡No ignores ese error!

Original: Don't Ignore that Error!

Una tarde, estaba caminando por la calle para verme con unos amigos en
un bar. No habíamos compartido una cerveza en algún tiempo y quería
verlos de nuevo. Con las prisas, no miré por dónde iba. Tropecé con el
borde de una esquina y caí de bruces . Bueno, me lo merecía por no poner
atención, supongo.

Me dolía la pierna, pero tenía prisa por ver a mis amigos. Así que me
levanté y seguí. Conforme caminaba el dolor se ponía cada vez peor. A
pesar de que al inicio lo desestimaba como una conmoción, me di cuenta
rápidamente de que había algo mal.

Pero me apresuré hacia el bar de todos modos. Estaba en agonía en el
momento en que llegué. No tuve una gran noche, porque estaba
terriblemente distraído. En la mañana fui al médico y me enteré de que
me había fracturado el hueso de la espinilla. De haberme detenido cuando
sentí el dolor, habría prevenido un montón del daño adicional que me
causé por seguir caminando. Probablemente fue el peor día-después de mi
vida.

Muchos programadores escriben código como mi desastrosa salida en la
noche.

¿Error, cuál error? No va a ser grave. Honestamente. Puedo ignorarlo.
Esta no es una estrategia ganadora para un código sólido. De hecho, es
pura flojera (de la mala). No importa que tan poco probable creas que es
un error en tu código, siempre debes revisarlo y tomarlo en cuenta.
Todas las veces. No estás ahorrando tiempo si no lo haces: estás
almacenando problemas potenciales en el futuro.

Reportamos errores en nuestro código de distintas formas, incluyendo:

- **Códigos de Retorno**. Pueden ser usados como valores resultantes de
una función para significar “no funcionó”. Los códigos de error son
bastante fáciles de ignorar. No verás nada en el código que resalte el
problema. De hecho, se ha convertido en una práctica estándar ignorar
algunos retornos de valores de las funciones estándares de C. ¿Qué tan
frecuentemente revisas el valor de retorno de `printf`?
- **errno**. Es una curiosa aberración de C, un conjunto de variables
globales para señalar errores. Es fácil ignorarlas, difíciles de usar y
da lugar a todo tipo de problemas desagradables; por ejemplo, ¿qué pasa
cuando tienes múltiples hilos llamando a la misma función? Algunas
plataformas te aíslan del dolor aquí; otras no.
- **Excepciones**. Son una forma más soportada por los lenguajes
estructurados para señalar y manipular errores. Y puedes ignorarlos. ¿O
no? He visto muchos códigos como estos:


        try {
            // ...do something...
        }
        catch (...) {} // ignore errors

La salvación en este horrible constructo es que resalta el hecho de que
estás haciendo algo moralmente dudoso.

Si ignoras un error, te haces de la vista gorda y haces de cuenta que
nada ha pasado, corres un gran riesgo; así como mi pierna terminó en un
peor estado por no haber dejado de caminar inmediatamente, a pesar de
que conduce a una falla muy compleja, enfrenta los problemas lo antes
posible. Mantén una cuenta breve.

No manejar errores conduce a:

- Código frágil. Código que se llena con errores excitantes y difíciles de
encontrar.
- Código inseguro. Los crackers frecuentemente explotan los pobres
manejos de errores para irrumpir en los sistemas de software.
- Estructura pobre. Si es un tedio enfrentar continuamente los errores
que hay en tu código, probablemente tengas una pobre interfaz. Expresa
tu interfaz de tal manera que los errores sean menos intrusivos y su
manejo sea menos oneroso.

Al igual que debes comprobar todos los posibles errores en tu código,
necesitas exponer todas las condiciones potenciales de error en tus
interfaces. No ocultarlos, pretendiendo que tus servicios siempre
funcionarán.

¿Por qué no comprobamos si hay errores? Hay un serie de excusas comunes.
¿Con cuál de ellas estás de acuerdo? ¿Cómo contrarrestar cada una?

- El manejo de errores estorba el flujo del código, haciéndolo difícil
de leer y difícil de detectar en el flujo “normal” de ejecución.
- Es un trabajo extra y tengo la fecha de entrega inminente.
- Sé que esa llamada de función nunca retornará un error (`printf`
siempre funciona, `malloc` siempre retorna nueva memoria); si falla
tenemos problemas mayores.
- Es sólo un programa de juguete y no necesita ser escrito con un nivel
digno de producción.

Autor: Pete Goodliffe