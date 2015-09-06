# Lenguajes Específicos del Dominio (DSL)

Original: Domain-Specific Languages

Cada vez que escuches una discusión de expertos de cualquier dominio, ya
sean jugadores de ajedrez, maestros de jardín de niños o agentes de
seguros, notarás que su vocabulario es un poco diferente del lenguaje
diario. Es parte de los Lenguajes Específicos del Dominio (DSL). Un
dominio específico tiene un vocabulario especializado para describir
cosas que son particulares de ese dominio.

En el mundo del software, los DSL tratan sobre expresiones ejecutables
en un lenguaje específico de un dominio con un limitado vocabulario y
gramática que es legible, entendible y –afortunadamente– escribible por
expertos del dominio. Los DSL dirigidos a desarrolladores de software o
científicos han estado por aquí desde hace un largo tiempo. Por ejemplo,
el “pequeño lenguaje” de Unix encontrado en archivos de configuración y
los lenguajes creados con el poder de macros de LISP son de los más
viejos ejemplos.

Los DSL son comúnmente clasificados como internos o externos:

- Los DSL internos son escritos en un lenguaje de programación de
propósito general, cuya sintaxis se ha inclinado a parecerse más al
lenguaje natural. Es más fácil para los lenguajes que ofrecen azúcar
sintáctica y posibilidades de formato (ej. Ruby y Scala) que para otros
que no lo hacen (ej. Java). Muchos DSL internos envuelven API
existentes, bibliotecas o código de negocio para proveer un contenedor
con un acceso más alucinante a sus funcionalidades. Son ejecutados con
sólo correrlos. Dependiendo en la implementación y el dominio, son
usados para construir estructuras de datos, definir dependencias,
ejecutar procesos o tareas, comunicarse con otros sistemas o validar
entradas de usuario. La sintaxis de un DSL interno están contenidas en
el lenguaje anfitrión. Hay muchos patrones –por ejemplo, constructores
de expresiones, encadenadores de métodos y anotaciones– que pueden
ayudarte a doblar el lenguaje anfitrión de tu DSL. Si el lenguaje
anfitrión no requiere recompilación, entonces un DSL interno puede ser
desarrollado rápidamente trabajando lado a lado con los expertos del
dominio.
- Los DSL externos son expresiones gráficas o textuales de un lenguaje,
aunque los DSL textuales tienden a ser más comunes que los gráficos. Las
expresiones textuales pueden ser procesadas por una cadena de
herramientas que incluyen léxico, un analizador, un transformador de
modelo, generadores, y cualquier otro tipo de posprocesamiento. Los DSL
externos son frecuentemente leídos en modelos internos, los cuales
forman los fundamentos para su posterior procesamiento. Es útil definir
una gramática (por ejemplo, en EBNF). Una gramática provee un punto de
partida para la generación de partes de la cadena de herramientas (por
ejemplo, editor, visualizador, generador de analizadores). Para los DSL
sencillos, un analizador hecho a mano podría ser suficiente; usando, por
ejemplo, expresiones regulares. Los analizadores personalizados pueden
llegar a ser difíciles de manejar si se espera mucho de ellos, así que
tiene sentido mirar las herramientas diseñadas específicamente para
trabajar con gramáticas del lenguaje; por ejemplo, openArchitectureWare,
ANTlr, SableCC y AndroMDA. Es también común el definir DSL externos como
los dialectos XML, aunque la legibilidad es frecuentemente un problema;
sobre todo para los lectores no técnicos.

Siempre debes tomar en cuenta la audiencia objetivo de tu DSL. ¿Son
desarrolladores, administradores, clientes de negocio o usuarios
finales? Tienes que adaptar el nivel técnico del lenguaje, las
herramientas disponibles, ayuda de sintaxis (por ejemplo, intellisense),
validación temprana, visualización y representación a tu audiencia
prevista. Al ocultar detalles técnicos, los DSL pueden empoderar a los
usuarios, dándoles la habilidad para adaptar los sistemas a sus
necesidades sin requerir la ayuda de los desarrolladores. También puede
acelerar el desarrollo debido al potencial de distribución de trabajo
después de que el framework inicial está en su sitio. El lenguaje puede
evolucionar gradualmente. Hay también disponibles diferentes rutas de
migración para expresiones existentes y gramática.

Autor: Michael Hunger