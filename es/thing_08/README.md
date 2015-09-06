# Aprende a usar las herramientas de línea de comandos

Original: Know How to Use Command-line Tools

Hoy en día, muchas herramientas de desarrollo de software se empaquetan
como Entornos Integrados de Desarrollo (IDE, Integrated Development
Environments). Microsoft Visual Studio y el proyecto de software libre
Eclipse son dos ejemplos populares, aunque hay muchos otros. Hay muchas
razones por las cuales nos gustan los IDE. No sólo porque son fáciles de
usar, sino que también alivian al programador de pensar en un montón de
pequeños detalles que involucran el proceso de construcción.

La facilidad de uso, sin embargo, tiene su lado negativo. Por lo
general, cuando una herramienta es fácil de usar, es debido a que está
tomando decisiones por ti y haciendo un montón de cosas automáticamente
detrás de la escena. Por lo tanto, si un IDE es el único entorno de
programación que siempre has usado, quizás nunca entiendas completamente
lo que tus herramientas están haciendo. Haces clic en un botón, algo de
magia ocurre, y un archivo ejecutable aparece en la carpeta del
proyecto.

Al trabajar con las herramientas de línea de comandos vas a aprender
mucho más sobre lo que están haciendo cuando se está construyendo el
proyecto. Escribir tus propios archivos `make` te ayudará al entendimiento
de todos los pasos (compilar, ensamblar, enlazar, etcétera) que están en
la construcción de un archivo ejecutable. Experimentar con las muchas
opciones de la línea de comandos de esas herramientas también es una
experiencia educacional valiosa. Para empezar con el uso de las
herramientas de construcción en línea de comandos, puedes usar las de
software libre, como GCC, o las proporcionadas por tu IDE propietario.
Después de todo, un IDE bien diseñado es sólo una interface gráfica para
un conjunto de herramientas de línea de comandos.

Además de mejorar tu entendimiento del proceso de construcción, hay
algunas tareas que pueden ser realizadas de forma más fácil o eficiente
con las herramientas de línea de comandos que con un IDE. Por ejemplo,
las capacidades de buscar y reemplazar provistas por las utilerías
`grep` y `sed` son más poderosas que aquellas que encuentras en IDEs.
Las herramientas de línea de comandos inherentemente soportan secuencias
de comandos (scripting), lo cuál permite la automatización de tareas,
como calendarizar _builds_ diarios, crear múltiples versiones de un
proyecto y la ejecución de conjuntos de pruebas. En un IDE este tipo de
automatización puede ser más difícil (si no imposible) de realizar
debido a que las opciones de construcción son usualmente especificadas
usando cajas de diálogo del GUI (Interface Gráfica de Usuario) y el
proceso de construcción es invocado con el clic del ratón. Si nunca has
dado un paso fuera de un IDE, quizá nunca te diste cuenta de que estos
tipos de tareas automatizadas son posibles.

Pero, espera. ¿Acaso el IDE no existe para hacer el desarrollo más fácil
y para mejorar la productividad del programador? Bueno, sí. La propuesta
presentada aquí no es que debes dejar de usar un IDE. La propuesta es
que deberías “mirar debajo de la cortina” y entender lo que el IDE está
haciendo por ti. La mejor manera de hacerlo es aprender a usar las
herramienta de línea de comandos. Luego, cuando vuelvas a usar tu IDE,
tendrás un mucho mejor entendimiento de qué es lo que está haciendo por
ti y cómo puedes controlar el proceso de construcción. Por otra parte,
una vez que domines el uso de las herramientas de línea de comandos y
experimentes el poder y flexibilidad que ofrecen, quizás podrías
encontrar que prefieres la línea de comando sobre el IDE.

Autor: Carroll Robinson