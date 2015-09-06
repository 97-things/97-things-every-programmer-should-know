# Cuando Programadores y Testers colaboran

Original: When Programmers and Testers Collaborate

Algo mágico sucede cuando los testers y programadores empiezan a
colaborar. Hay menos tiempo perdido mandando bugs de ida y de regreso a
través del sistema de rastreo de defectos. Menos tiempo se desperdicia
intentando imaginar si algo es realmente un error o una nueva
característica, y más tiempo es usado desarrollando buen software para
satisfacer las expectativas de los clientes. Hay muchas oportunidades
para comenzar a colaborar, incluso antes de que la codificación inicie.

Los testers pueden ayudar a los clientes a escribir y automatizar las
pruebas de aceptación usando el lenguaje de su dominio con herramientas
tales como _Fit_ (_Framework for Integrated Test_). Cuando estas prueban
son entregadas a los programadores antes de que la codificación inicie,
el equipo está practicando el Desarrollo Conducido por Pruebas de
Aceptación (_Acceptance Test Driven Development_, ATDD). Los
programadores escriben sus arreglos para ejecutar las pruebas, y
entonces codifican para hacer que las pruebas pasen. Estas pruebas se
convierten en parte de la suite de regresión. Cuando esta colaboración
ocurre, las pruebas funcionales se completan de manera temprana, lo que
da tiempo para las pruebas exploratorias en condiciones extremas o a
través de flujos de trabajo con un rango más amplio.

odemos dar un paso más adelante. Como tester puedo suministrar la
mayoría de mis ideas de prueba antes de que los programadores codifiquen
una nueva característica. Cuando le pregunto a los programadores si
tienen alguna sugerencia, ellos casi siempre me proveen la información
que me ayuda con una mejor cobertura de pruebas, o me ayuda a evitar
gastar mucho tiempo en pruebas innecesarias. Frecuentemente hemos
prevenido defectos porque las pruebas clarifican muchas de las ideas
iniciales. Por ejemplo, en un proyecto en el que estaba, la prueba _Fit_
que le di al programado mostraba los resultados esperados de una
consulta que respondía a una búsqueda con comodines. El programador
pretendía codificar sólo búsquedas de palabras completas. Pudimos hablar
con el cliente y determinar la interpretación correcta antes de que la
codificación iniciara. Al colaborar prevenimos el defecto, lo cual nos
ahorró a ambos un montón de tiempo.

Los programadores pueden colaborar con los testers para crear también
una automatización exitosa. Ellos entienden las buenas prácticas de
codificación y pueden ayudar a los testers a configurar una robusta
_suite_ de automatización de pruebas que funcione para todo el equipo.
Muchas veces he visto proyectos de automatización que fallan porque las
pruebas están mal diseñadas. Las pruebas intentan probar mucho o los
testers no han entendido lo suficiente acerca de la tecnología para ser
capaces de mantener las pruebas independientes. Los testers son
frecuentemente el cuello de botella, así que tiene sentido para los
programadores el trabajar con ellos en las tareas como la
automatización. Al trabajar con los testers para entender qué puede ser
probado tempranamente, quizás al proporcionar una herramienta sencilla,
dará a los programadores otro ciclo de retroalimentación que les
ayudará, a largo plazo, a entregar mejor código.

Cuando los testers dejan de pensar que su único trabajo es romper el
software y buscar errores en el código de los programadores, los
programadores dejan de pensar que los testers “van por ellos” y están
más abiertos a la colaboración. Cuando los programadores empiezan a
darse cuenta de que son responsables de construir calidad dentro de su
código, el realizar pruebas es algo natural para el producto y el equipo
puede automatizar más pruebas de regresión juntos. La magia del trabajo
en equipo comienza.

Autor: Janet Gregory