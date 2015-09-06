# Escoge tus herramientas con cuidado

Original: Choose Your Tools with Care

Las aplicaciones modernas rara vez son construidas desde cero. Se
ensamblan usando herramientas existentes –componentes, bibliotecas y
frameworks– por una serie de buenas razones:

* Las aplicaciones crecen en tamaño, complejidad y sofisticación, mientras
el tiempo para desarrollarlas decrece. Se hace un mejor uso del tiempo e
inteligencia del desarrollador, si pueden concentrarse en escribir más
código del dominio del negocio y menos código de infraestructura
* Los componentes y frameworks ampliamente utilizados con frecuencia
tienen menos errores que aquellos desarrollados en casa.
* Hay un montón de software de alta calidad disponible en la red de
forma gratuita, lo cual significa menores costos de desarrollo y mayor
probabilidad de encontrar desarrolladores con el interés y experiencia
necesaria.
* La producción y mantenimiento de software es un trabajo humanamente
intensivo, por lo que comprarlo podría ser más barato que construirlo.

Sin embargo, escoger la mezcla completa de herramientas para tu
aplicación puede ser un negocio riesgoso que requiere pensarlo un poco.
De hecho, hay unas cuantas cosas que deberías tener en mente mientras
estás haciendo la elección:

* Las diferentes herramientas pueden estar basadas en distintos supuestos
sobre su contexto –por ejemplo, la infraestructura circundante, modelo
de control, modelo de datos, protocolos de comunicación, etcétera – lo
cual puede llevar a un diferencial de arquitectura entre la aplicación y
las herramientas. Dichas diferencias conducen a *hacks* y *workarounds*
que harán el código más complejo de lo necesario.
* Las diferentes herramientas tienen diferentes ciclos de vida, y
actualizar una de ellas podría convertirse en algo extremadamente
difícil y una tarea que consume tiempo en cada nueva funcionalidad,
cambios de diseño o incluso correcciones de errores que podrían causar
incompatibilidades con las otras herramientas. Entre más grande sea el
número de herramientas, peor es el problema en el que puede convertirse.
* Algunas herramientas requieren configuraciones, lo que frecuentemente
significa uno o más archivos XML, lo cual se sale de control muy rápido.
La aplicación puede terminar como si fuese escrita toda en XML más unas
cuántas líneas de código en algún lenguaje de programación. La
complejidad en la configuración hará la aplicación difícil de mantener
y de extender.
* Ocurre un vendor-lock cuando el código que depende en gran medida en un
proveedor específico termina siendo arriesgado por él en varias formas:
mantenimiento, rendimiento, habilidad para evolucionar, precio, etc.
* Si planeas usar software libre, puedes descubrir que no es tan libre
después de todo. Quizás necesites comprar soporte comercial, lo cual no
necesariamente va a ser barato.
* Los términos de licenciamiento importan, incluso para el software libre.
Por ejemplo, en algunas compañías no es aceptable usar software
licenciado bajo los términos de la licencia GNU, debido a su naturaleza
viral, es decir, el software desarrollado con él debe ser distribuido
junto con su código fuente.

Mi estrategia personal para mitigar estos problemas es comenzar poco a
poco, usando sólo las herramientas que son absolutamente necesarias.
Usualmente el enfoque inicial está en quitar la necesidad de participar
en la programación (y los problemas) de infraestructura de bajo nivel,
por ejemplo, usando algún middleware en vez de usar sockets para
aplicaciones distribuidas. Y entonces agregar más si es necesario.
También tiendo a aislar las herramientas externas de mis objetos de
dominio del negocio con respecto a interfaces y capas de presentación,
así puedo cambiar la herramienta, si lo tengo que hacer, con sólo una
pequeña dosis de dolor. Un lado positivo de este enfoque es que
generalmente termino con una aplicación más pequeña que usa menos
herramientas externas de lo que originalmente se pronosticó.

Autor: Giovanni Asproni