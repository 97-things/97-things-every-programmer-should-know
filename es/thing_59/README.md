# Mantén limpia la compilación

Original: Keep the Build Clean

¿Alguna vez has visto una lista de advertencias de compilación del largo
de un ensayo sobre mala codificación y pensado: “debería hacer algo al
respecto, pero ahora no tengo tiempo”? Por otro lado, ¿alguna vez has
visto esa solitaria advertencia que acaba de aparecer en una compilación
y simplemente la arreglaste?

Cuando inicio un nuevo proyecto desde cero no hay advertencias, no hay
desorden, no hay problemas. Pero conforme crece la base de código, si no
pongo atención, el desorden, las costras, las advertencias y los
problemas pueden empezar a apilarse. Cuando hay mucho ruido, es más
difícil encontrar la advertencia que realmente quiero leer entre los
cientos de advertencias que no me importan.

Para hacer las advertencias útiles de nuevo, trato de usar una política
de tolerancia cero a advertencias desde la compilación. Incluso si la
advertencia no es importante, le hago frente. Si no es crítica, pero aún
relevante, la arreglo. Si el compilador advierte sobre una potencial
excepción de puntero nulo, arreglo la causa, incluso si “sé” que el
problema nunca se presentará en producción. Si la documentación embebida
(Javadoc o similar) hace referencia a parámetros que han sido quitados o
renombrados, limpio la documentación.

Si es algo que realmente no me importa, pregunto al equipo si podemos
cambiar nuestra política de advertencias. Por ejemplo, encontré que
documentando los parámetros y un valor de retorno de un método en muchos
casos no agrega ningún valor, así que no debería ser una advertencia si
faltan. O al actualizar una nueva versión del lenguaje de programación
el código que anteriormente estaba bien ahora emita advertencias. Por
ejemplo, cuando Java 5 introdujo `generics` todo el código antiguo que
no especificaba el parámetro de tipo generic nos daba una advertencia.
Éste es el tipo de advertencias por las que no quiero ser molestado (al
menos, todavía no). Tener un conjunto de advertencias que está fuera
del camino de la realidad no le sirve a nadie.

Al asegurarme de que la compilación está siempre limpia no tendré que
decidir si una advertencia es irrelevante cada vez que me la encuentro.
Ignorar cosas es un trabajo mental y necesito deshacerme de todo el
trabajo mental innecesario que pueda. Tener una compilación limpia
también hace fácil para alguien más hacerse cargo de mi trabajo. Si dejo
las advertencias, alguien más tendrá que encontrar qué es relevante y
qué no lo es. O simplemente ignorar todas las advertencias, incluyendo
las importantes.

Las advertencias de tu compilador son útiles. Sólo necesitas deshacerte
del ruido para empezar a notarlas. No esperes hacer esa “gran limpieza”.
Cuando alguna aparece y no la quieres ver, hazle frente de inmediato.
También corrige la fuente de la advertencia, suprime esa advertencia o
corrige las políticas de advertencia de tu herramienta. Mantener limpia
la compilación no se trata sólo de mantenerla limpia de errores de
compilación o fallos de pruebas: las advertencias son también una parte
importante y fundamental de la higiene del código.

Autor: Johannes Brodwall