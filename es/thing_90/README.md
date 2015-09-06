# Sólo el código dice la verdad

Original: Only the Code Tells the Truth

La semántica final de un programa está dada por el código que se
ejecuta. ¡Si esto es únicamente en formato binario, será una lectura
difícil! El código fuente debe, sin embargo, estar disponible si se
trata de tu programa, cualquier desarrollo de software comercial típico,
un proyecto de software libre o código en un lenguaje interpretado de
forma dinámica. Al mirar el código fuente, el significado del programa
debería ser evidente. Para saber qué hace el programa, el código es, en
última instancia, de lo que puedes estar seguro. Hasta el documento de
requisitos más preciso no dice toda la verdad: no contiene el relato
detallado de lo que el programa está haciendo, sólo las intenciones de
más alto nivel del analista de requerimientos. Un documento de diseño
podría capturar un diseño planeado, pero carece del nivel necesario de
detalle de la implementación. Estos documento pueden perder sincronía
con la implementación actual… o simplemente se han perdido. O nunca
fueron escritos, en primer lugar. El código fuente puede ser lo único
que queda.

Con esto en mente, pregúntate: ¿qué tan claro es tu código al decirte a
ti o a cualquier otro programador qué es lo que está haciendo?

Podrías decir: “Oh, mis comentarios te dirán todo lo que necesitas
saber”. Pero recuerda que los comentarios no son código en ejecución.
Pueden ser tan malos como cualquier otra forma de documentación. Existe
una tradición que dice que los comentarios son incondicionalmente algo
bueno, así que algunos programadores escriben más y más comentarios,
incluso reiniciando y explicando trivialidades que son obvias en el
código. Ésa es la forma errónea de clarificar tu código. Si tu código
tiene comentarios, considera refactorizar para que no los tenga. Los
comentarios extensos pueden saturar el espacio en la pantalla e incluso
pueden ser ocultados automáticamente por tu IDE. Si necesitas explicar
un cambio, hazlo en el mensaje de confirmación del sistema de control
de versiones, no en el código.

¿Qué se puede hacer para hacer que tu código diga la verdad lo más claro
posible? Lucha por buenos nombres. Estructura tu código con respecto a
la funcionalidad cohesiva, que también facilita la nomenclatura.
Desacopla el código para conseguir ortogonalidad. Escribe pruebas
automatizadas explicando el comportamiento previsto y comprueba las
interfaces. Refactoriza sin piedad cuando aprendas cómo codificar una
solución mejor y más sencilla. Haz que tu código sea tan sencillo como
sea posible para leer y entender.

Trata a tu código como a cualquier otra composición, como un poema, un
ensayo, un blog público o un email importante. Elabora lo que expresas
con cuidado, de modo que haga lo que debe y comunique tan directamente
como sea posible lo que está haciendo, para que comunique tus
intenciones cuando no estés. Recuerda que el código útil se usa mucho
más tiempo de lo previsto. Los programadores de mantenimiento te lo
agradecerán. Y, si eres un programador de mantenimiento y el código en
el que estás trabajando no dice la verdad fácilmente, aplica las
directrices anteriores de manera proactiva. Establece algo de cordura en
el código y mantén tu propia cordura.

Autor: Peter Sommerlad