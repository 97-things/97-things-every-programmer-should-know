# La comunicación entre procesos afecta el tiempo de respuesta de la aplicación

Original: Inter-Process Communication Affects Application Response Time

El tiempo de respuesta es crítico en la usabilidad del software. Pocas
cosas son tan frustrantes como esperar a que responda algún sistema de
software, especialmente cuando nuestra interacción involucra ciclos
repetidos de estímulos y respuestas. Nos sentimos como si el software
estuviera desperdiciando nuestro tiempo y afectando nuestra
productividad. Sin embargo, las causas del pobre tiempo de respuesta son
poco apreciadas, especialmente en las aplicaciones modernas. Mucha
literatura de administración de rendimiento aún se enfoca en estructuras
de datos y algoritmos, temas que pueden hacer una diferencia en algunos
casos, pero que son mucho menos propensos a dominar el rendimiento en
las modernas aplicaciones empresariales multicapa.

Cuando el rendimiento es un problema en tales aplicaciones, mi
experiencia ha sido que examinar estructuras de datos y algoritmos no es
el lugar adecuado para buscar mejoras. Los tiempo de respuesta dependen
más del número de comunicaciones remotas entre procesos (IPC, _inter-
process communications_) conducidas en respuesta a un estímulo. Aunque
puede haber otros cuellos de botella locales, el número de IPC remotas
domina usualmente. Cada IPC remota contribuye a latencia no-despreciable
para el tiempo de respuesta global, y estas contribuciones remotas se
suman, especialmente cuando incurren en secuencia.

Un buen ejemplo es la carga ondular en una aplicación usando mapeo
objeto-relación (ORM, _object-relational mapping_). La carga ondular
describe la ejecución secuencial de muchas llamadas a la base de datos
para seleccionar los datos necesarios para construir un objeto gráfico
(vea: “Lazy Load”, del libro de Martin Fowler: Patterns of Enterprise
Application Architecture). Cuando el cliente de la base de datos es un
servidor de aplicaciones de capa intermedia renderizando una página web,
estas llamadas a la base de datos son ejecutadas usualmente en secuencia
en un solo hilo. Sus latencias individuales se acumulan, lo que
contribuye al tiempo de respuesta global. Incluso si cada llamada a la
base de datos toma sólo 10 minutos, una página que requiera mil llamadas
(que no es poco común) exhibirá al menos un tiempo de respuesta de 10
segundos. Otros ejemplos incluyen la invocación de servicios web,
respuestas HTTP desde un navegador web, invocación de objetos
distribuidos, mensajería de petición-respuesta (reply-request) e
interacción con redes de datos en protocolos de red personalizados.
Entre más IPC remotas se necesiten para responder a un estímulo, mayor
será el tiempo de respuesta.

Hay algunas estrategias relativamente obvias y bien conocidas para
reducir el número de IPC remotas por estímulo. Una estrategia es aplicar
el [principio de parsimonia][1], optimizando la interfaz entre procesos,
así el número exacto de datos para el propósito a mano es intercambiado
con la mínima cantidad de interacciones. Otra estrategia es paralelizar
las IPC donde sea posible, así el tiempo de respuesta global es llevado
principalmente por la latencia de IPC más larga. Una tercera estrategia
es almacenar en caché los resultados de IPC previos, así los futuros
IPC pueden ser evitados al usar caché local en su lugar.

Cuando estés diseñando una aplicación, ten en cuenta el número de IPC en
respuesta a cada estímulo. Al analizar aplicaciones que sufren de un
rendimiento pobre, a menudo me he encontrado radios de IPC-estímulo de
miles a 1. La reducción de este radio, ya sea mediante caché,
paralelizando o alguna otra técnica, vale mucho más la pena que cambiar
la selección de estructuras de datos o ajustar un algoritmo de
ordenamiento.

[1]: https://es.wikipedia.org/wiki/Navaja_de_Ockham

Autor: Randy Stafford