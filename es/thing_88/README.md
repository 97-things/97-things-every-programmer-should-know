# Retrocede y Automatiza, Automatiza, Automatiza

Original: Step Back and Automate, Automate, Automate


Trabajé con programadores que, cuando se les pidió un conteo del número
de líneas de código de un módulo, copiaban los archivos en un procesador
de texto y usaban la característica de “número de líneas”. Y lo hicieron
de nuevo la siguiente semana y la semana siguiente. Fue malo.

Trabajé en un proyecto que tenía un proceso de implementación engorroso,
implicaba la firma de código y mover el resultado a un servidor,
requiriendo muchos clics con el ratón. Alguien lo automatizó y el script
se ejecutó cientos de veces durante la prueba final, mucho más
frecuentemente de lo previsto. Fue bueno.

Entonces, ¿por qué la gente realiza la misma tarea una y otra vez, en
vez de retroceder y tomarse el tiempo de automatizarla?

**Concepto erróneo común #1: La automatización es sólo para las
pruebas**

Seguro, la automatización en las pruebas es genial, pero ¿por qué
detenerse ahí? Las tareas repetitivas están en cualquier proyecto:
control de versiones, compilación, construcción de archivos JAR,
generación de documentación, implementación y presentación de informes.
Para muchas de estas tareas, el script es más poderoso que el ratón.
Ejecutar tareas tediosas se convierte en algo más rápido y más fiable.

**Concepto erróneo común #2: Tengo un IDE, así que no necesito
automatizar**

¿Alguna vez has tenido una discusión con un “pero (lo revisé | compila |
pasa las pruebas) en mi máquina” con alguno de tus compañeros de equipo?
Los IDE modernos tienen miles de configuraciones posibles y es
prácticamente imposible asegurar que todos los miembros del equipo
tienen configuraciones idénticas. Los sistemas de compilación
automática, tales como Ant o Autotools, te proporcionan control y
repetitividad.

**Concepto erróneo común #3: Necesito aprender exóticas herramientas con
el fin de automatizar**

Puedes seguir con un lenguaje de shell decente (tales como bash o
Powershell) y un sistema de automatización de compilación. Si necesitas
interactuar con un sitio web, usa herramientas como iMacros o Selenium.

**Concepto erróneo común #4: No puedo automatizar esta tarea porque no
puedo manejar este tipo de formato**

Si una parte de tu proceso requiere documentos Word, hojas de cálculo o
imágenes, es cierto que puede ser un reto para la automatización, pero
¿es realmente necesario? ¿Puedes usar texto plano? ¿Valores separados
por coma? ¿XML? ¿Alguna herramienta que genere un dibujo a partir de un
archivo de texto? Con frecuencia, unos ligeros arreglos en el proceso
puede llevar a un buen resultado con una dramática reducción del tedio.

**Concepto erróneo común #5: No tengo el tiempo para averiguarlo**

No tienes que aprender todo sobre bash o Ant para empezar. Aprende sobre
la marcha. Cuando tengas una tarea que crees que pueda y deba ser
automatizada, aprende sólo lo necesario acerca de la herramienta para
hacerlo. Hazlo al inicio del proyecto cuando el tiempo es más fácil de
encontrar. Una vez que has tenido éxito, tú y tu jefe verán que tiene
sentido invertir en automatización.

Autor: Cay Horstmann