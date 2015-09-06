# Distingue excepciones de Negocio de las excepciones Técnicas

Original: Distinguish Business Exceptions from Technical

Hay básicamente dos razones por las que las cosas van mal en tiempo de
ejecución: problemas técnicos que impiden el uso de la aplicación y la
lógica del negocio que evita hacer mal uso de la aplicación. La mayoría
de los lenguajes modernos, como LISP, Java, Smalltalk y C#, usan
excepciones para señalar ambas situaciones. Sin embargo, las dos
situaciones son tan diferentes que deberían ser tomadas por separado. Es
una fuente potencial de confusión representar ambas usando la misma
jerarquía de excepciones, sin mencionar la misma clase de excepciones.

Un problema técnico irresoluble puede ocurrir cuando hay un error de
programación. Por ejemplo, si tratas de acceder al elemento 83 de una
matriz de tamaño 17, entonces el programa está claramente fuera de
control, y debería resultar en alguna excepción. La versión más sutil es
llamar a alguna biblioteca de código con argumentos inapropiados,
causando la misma situación dentro de la biblioteca.

Sería un error intentar resolver tú mismo estas situaciones que
causaste. En vez de dejar que la excepción se eleve al nivel
arquitectónico más alto y dejar que algún mecanismo general de manejo de
excepciones haga lo que pueda para asegurar que el sistema está en un
estado seguro, tales como deshacer una transacción, registrar en la
bitácora y alertar a la gerencia, e informar (educadamente) al usuario.

Una variante de esta situación es cuando te encuentras en la “situación
de biblioteca” y quien hace el llamado rompió el contrato de tu método,
por ejemplo, pasando un argumento extraño o sin tener un objeto
dependiente configurado correctamente. Esto va a la par con el acceso al
83vo elemento de 17: quien hace la llamada debería haber comprobado; no
hacerlo es un error del programador en el lado del cliente. La respuesta
correcta es lanzar una excepción técnica.

Una diferente, pero aún situación técnica, es cuando el programa no
puede continuar debido a un problema en el ambiente de producción, como
una base de datos que no responde. En esta situación debes asumir que la
infraestructura hizo lo que pudo para resolver la situación –reparar
conexiones, reintentar un número razonable de veces– y falló. Incluso si
la causa es diferente, la situación para el código es similar: hay poco
que puedas al respecto. Así que señalamos la situación a través de una
excepción que subiremos hacia un mecanismo general de manejo de
excepciones.

En contraste a esas situaciones, tenemos la situación en la cual no
puedes completar la llamada por una razón de dominio lógico. En este
caso nos hemos encontrado una situación que es una excepción, es decir,
una inusual e indeseable, pero no un error extraño o programático. Por
ejemplo, tratar de retirar dinero de una cuenta con fondos
insuficientes. En otras palabras, este tipo de situaciones es una parte
del contrato, y lanzar una excepción es sólo una vía de retorno
alternativa que es parte del modelo y que el cliente debería tener en
cuenta y estar preparado para manejarlo. Para estas situaciones es
apropiado crear una excepción específica o una jerarquía de excepción
por separado, así el cliente puede manejar la situación en sus propios
términos.

Mezclar excepciones técnicas y excepciones de negocios en la misma
jerarquía desdibuja la distinción y confunde a quien hace la llamada
sobre qué método del contrato es, qué condiciones se requiere asegurar
antes de ejecutarlas y qué situaciones se supone debe manejar. Separar
los casos ofrece claridad e incrementa la oportunidad de que las
excepciones técnicas sean manejadas por algún framework de aplicaciones,
mientras que las excepciones de dominio del negocio son consideradas y
manejadas por el código del cliente.

Autor: Dan Bergh Johnsson