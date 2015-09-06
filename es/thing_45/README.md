# Implementa rápido y con frecuencia

Original: Deploy Early and Often

Depurar el proceso de implementación e instalación suele posponerse
hasta que se acerca el final del proyecto. En algunos proyectos, la
escritura de herramientas de instalación es delegada a un ingeniero de
entrega, quien asume la tarea como un “mal necesario”. Las revisiones y
demostraciones son realizadas a partir de un ambiente hecho a mano para
asegurarse de que todo funciona. El resultado es que el equipo no
obtiene la experiencia en el proceso de implementación o sobre el
ambiente de implementación hasta que quizás es demasiado tarde para
hacer los cambios.

El proceso de instalación/implementación es lo primero que ve el
cliente, y un proceso simple de instalación/implementación es el primer
paso para tener un ambiente de producción fiable (o, al menos, fácil de
depurar). El software implementado es lo que el cliente usará. El no
garantizar que la implementación configura la aplicación correctamente
hará que el cliente tenga preguntas antes de que use tu software
exhaustivamente.

Iniciar tu proyecto con un proceso de instalación te dará tiempo para
evolucionar el proceso conforme se vaya moviendo en el ciclo de
desarrollo del producto y la posibilidad para realizar cambios al código
de la aplicación para que la instalación sea más fácil. Ejecutar y
probar el proceso de instalación en un ambiente limpio periódicamente
también provee un chequeo en el que no tendrás suposiciones en el código
que se base en los ambientes de desarrollo o de prueba.

Poner la implementación al último significa que el proceso de
implementación puede necesitar ser más complicado para evitar las
suposiciones en el código. Lo que parece una buena idea en un IDE, en el
cual tienes el control total de un entorno, puede hacer que un proceso
de implementación sea mucho más complicado. Es mejor saber todas las
ventajas y desventajas más temprano que tarde.

A pesar de que “ser capaz de implementar” desde el principio, no parece
tener mucho más valor de negocio comparado con ver una aplicación
ejecutándose en la computadora portátil del desarrollador, la verdad es
que mientras no puedas demostrar tu aplicación en entorno final habrá un
montón de trabajo que hacer antes de que puedas ofrecer un valor
empresarial. Si el fundamento de poner en marcha el proceso de
implementación es que es algo trivial, entonces hazlo de todos modos, ya
que es a bajo costo. Si es demasiado complicado, o si hay demasiadas
incertidumbres, haz lo que harías con el código de una aplicación:
experimenta, evalúa y refactoriza el proceso de implementación conforme
avances.

El proceso de instalación/implementación es esencial para la
productividad de los clientes o de su equipo de servicio profesionales,
por lo que deberías hacer pruebas y refactorizar este proceso sobre la
marcha. Probamos y refactorizamos el código fuente de todo el proyecto.
La implementación no se merece menos.

Autor: Steve Berczuk