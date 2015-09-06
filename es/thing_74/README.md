# El paso de mensajes lleva a una mejor escalabilidad en sistemas paralelos

Original: Message Passing Leads to Better Scalability in Parallel Systems

A los programadores se les enseña desde el primer momento de sus
estudios en computación que la concurrencia –y especialmente el
paralelismo, un subconjunto especial de la concurrencia– es difícil, que
sólo los mejores pueden tener la esperanzas de hacerlo bien y que
incluso se equivocan. Siempre hay una gran atención a _threads_,
semáforos, monitores y lo difícil que es obtener el acceso simultáneo a
variables para ser seguro en _threads_.

Es cierto, hay muchos problemas difíciles, y pueden ser muy difíciles de
resolver. Pero, ¿cuál es la raíz del problema? Memoria compartida. Casi
todos los problemas de concurrencia que la gente tiene una y otra vez se
relacionan con el uso de memoria compartida mutable: _race conditions_,
_deadlocks_, _livelock_, etcétera. La respuesta parece obvia: ¡renunciar
a la concurrencia o abstenerse de la memoria compartida!

Olvidar la concurrencia casi seguramente no es una opción. Las
computadoras tienen más y más núcleos de manera casi trimestral, por lo
que el aprovechamiento de cierto paralelismo se hace más y más
importante. No nos podemos confiar tanto en cada incremento de la
velocidad del procesador para mejorar el rendimiento de nuestra
aplicación. Obviamente, no mejorar el rendimiento es una opción, pero es
poco probable que sea aceptable para los usuarios.

Entonces, ¿podemos evitar la memoria compartida? Definitivamente.

En vez de usar _threads_ y memoria compartida como nuestro modelo de
programación, podemos usar procesos y el paso de mensajes. Los procesos
aquí sólo significan un estado protegido e independiente con código
ejecutándose, no necesariamente un proceso del sistema operativo.
Lenguajes como Erlang (y Occam antes de él) han mostrado que los
procesos son un exitoso mecanismo para la programación de sistemas
concurrentes y paralelos. Tales sistemas no tienen todo el estrés de
sincronización que la memoria compartida y los sistemas de _multi-
thread_ tienen. Más aún, hay un modelo formal –Proceso de Comunicación
Secuencial (CSP, por sus siglas en inglés \[_Communicating Sequential
Processes_\])– que puede ser aplicado como parte de la ingeniería de
tales sistemas.

Podemos ir más allá e introducir sistemas de flujo de datos como una
forma de computación. En un sistema de flujo de datos no hay un flujo de
control explícitamente programado. En vez de eso se configura un grafo
directo de operadores conectados por rutas de datos y entonces los datos
son alimentados al sistema. La evaluación es controlada por la
disponibilidad de los datos dentro del sistema. Definitivamente sin
problemas de sincronización.

Dicho todo esto, lenguajes como C, C++, Java, Python y Groovy son el
principal lenguaje del desarrollo de sistemas y todos ellos son
presentados a los programadores como lenguajes para desarrollo de
memoria compartida, sistemas de _multi-thread_. Entonces, ¿qué se puede
hacer? La respuesta es utilizar –o, si no existen, crear– bibliotecas y
_frameworks_ que proporcionan modelos de procesos y paso de mensajes,
evitando todo el uso de memoria compartida mutable.

Después de todo, no programar con memoria compartida y usar en vez de
eso paso de mensajes es probablemente la forma más exitosa de
implementar sistemas que aprovechan el paralelismo que es ahora endémico
en el hardware de computación. Quizás extrañamente, pero a pesar de que
los procesos son anteriores a los _threads_ como unidad de concurrencia,
el futuro parece estar en usar _threads_ para implementar procesos.

Autor: Russel Winder