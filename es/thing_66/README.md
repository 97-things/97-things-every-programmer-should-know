# No seas lindo con tus datos de prueba

Original: Don't Be Cute with Your Test Data

Se estaba haciendo tarde. Estaba tirando cosas en un repositorio de
datos para probar el diseño de página en el que estaba trabajando.

Me apropié de los miembros de The Clash para los nombres de usuario.
¿Nombres de empresas? Los títulos de las canciones de Sex Pistols
servirían. Ahora necesito algunos símbolos de la bolsa de valores, sólo
cuatro letras en mayúsculas.

Usé las palabras de **cuatro** letras.

Parecía inofensivo. Sólo algo para divertirme, y quizás también a los
otros desarrolladores el día siguiente antes de enlazarlo a fuentes de
datos reales. La mañana siguiente un gerente de proyecto tomó algunas
capturas de pantallas para una presentación.

La historia de la programación está llena de este tipo de cuentos de
guerra. Cosas que los desarrolladores y diseñadores hicieron “y que
nadie más vería”, las cuales inesperadamente se vuelven visibles.

El tipo de fuga puede variar, pero, cuando sucede, puede ser mortal para
la persona, equipo o compañía responsables. Los ejemplos incluyen:

- Durante una junta para revisión de estatus, un cliente hace clic en un
botón que todavía no ha sido implementado. El mensaje dice: “No hagas
clic en eso de nuevo, idiota”. .
- A un programador de mantenimiento de un sistema heredado se le había
dicho que añadiera un mensaje de error y decidió usar la salida de
registros “detrás de la escena” existentes para lograrlo. Los usuarios
repentinamente se enfrentaban con mensajes como: “¡Santos errores de
base de datos, Batman!”, cuando algo se descomponía.
- Alguien confundió las pruebas con la interfaz de administración en vivo
y hace una entrada de datos “graciosos”. Los clientes detectaron un
“Masajeador personal con forma de Bill Gates” de $1 millón de dólares a
la venta en su tienda en línea.

Como para apropiarnos del viejo adagio de “una mentira puede viajar por
la mitad del mundo mientras la verdad se está poniendo los zapatos”, en
estas fechas y épocas una metedura de pata puede ser tuiteada y
facebookeada antes de que cualquiera de los desarrolladores de la zona
horaria esté despierto para hacer algo al respecto.

Incluso tu código fuente no está necesariamente libre del escrutinio. En
2004, cuando un comprimido del código fuente de Windows 2000 se abrió
camino en las redes de intercambio de archivos, algunos muchachos lo
revisaron en busca de profanidad, insultos y otros comentarios graciosos
(el comentario // TERRIBLE HORRIBLE NO DIOS QUE MAL HACK, debo admitir,
¡se vuelve adecuado para mí de vez en cuando desde entonces!).

En resumen, cuando escribas cualquier texto en tu código –ya sea
comentarios, registros, mensajes o datos de prueba– siempre pregúntate a
ti mismo cómo se verá si se convierte en algo público. Esto te ahorrará,
todo el tiempo, algunas caras rojas.

Autor: Rod Begbie