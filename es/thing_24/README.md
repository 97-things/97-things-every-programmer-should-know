# Conoce tus límites

Original: Know Your Limits

> _"Man's got to know his limitations." — [Dirty Harry][1]_

Tus recursos son limitados. Sólo tienes cierto tiempo y dinero para
hacer tu trabajo, incluyendo el tiempo y dinero necesario para mantener
al día tus conocimiento, habilidades y herramientas. Sólo se puede
trabajar duro, rápido e inteligentemente por cierto tiempo. Tus
herramientas son poderosas. Tus máquinas destino son poderosas. Tienes
que respetar los límites de tus recursos.

¿Cómo respetar estos límites? Conócete a ti mismo, conoce a tu gente, tu
presupuesto y tus cosas. Especialmente, como ingeniero de software,
conoce el espacio y tiempo de la complejidad de tus estructuras de datos
y algoritmos, así como las características y rendimiento de tus
sistemas. Tu trabajo es crear el enlace óptimo de software y sistemas.

La complejidad del espacio y tiempo están dadas como la función
_O(f(n))_ donde _n_ es igual al tamaño de las entradas en el espacio
asintótico o el tiempo requerido conforme *n* incrementa hacia infinito.
Las clases de complejidad importantes para _f(n)_ incluyen _ln(n)_, *n*,
_n ln(n)_, n<sup>e</sup> y e<sup>n</sup>. Al graficar estas funciones se
muestra claramente cómo conforme _n_ se incrementa, _O(ln(n))_ es
siempre mucho más pequeña que _O(n)_ y _O(n ln(n))_, las cuales son cada
vez más pequeñas que _O(ne)_ y O(en). Como decía Sean Parent, para
lograr *n* todas las clases de complejidad se acumulan casi constamente,
casi lineal o casi al infinito.

![](http://programmer.97things.oreilly.com/wiki/images/c/c0/Clearly.jpeg)

El análisis de complejidad está en términos de una máquina abstracta,
pero el software se ejecuta en máquinas reales. Las sistemas modernos de
computadoras están organizados como jerarquías de máquinas físicas y
virtuales, incluyendo lenguajes en tiempo de ejecución, sistemas
operativos, CPU, memoria caché, memoria de acceso aleatorio, manejadores
de disco y redes. La primera tabla muestra los límites en el tiempo de
acceso aleatorio y la capacidad de almacenamiento para un servidor en
red típico.

|              | Tiempo de Acceso |  Capacidad |
|--------------|-----------------:| ----------:|
|register      |  < 1 ms          |        64b |
|cache line    |                  |        64B |
|L1 cache      |  1 ms            | 64 KB      |
|L2 cache      |  4 ns            | 8 MB       |
| RAM          | 20 ns            | 32 GB      |
| disk         | 10 ms            | 10 TB      |
| LAN          | 20 ms            | > 1 PB     |
| internet     | 100 ms           | > 1 ZB     |

Toma en cuenta que la capacidad y velocidad difiere en varios órdenes de
magnitud. El almacenamiento en caché y el _lookahead_ son usados
ampliamente en cada nivel de nuestro sistema para ocultar esta
variación, pero sólo funcionan cuando el acceso es predecible. Cuando el
caché falla es frecuente que el sistema esté arrastrándose. Por ejemplo,
inspeccionar aleatoriamente cada _byte_ en un disco duro podría tomar
hasta 32 años. Incluso inspeccionar aleatoriamente cada byte en la RAM
podría tomar 11 minutos. El acceso aleatorio no es predecible. ¿Qué lo
es? Eso depende del sistema, pero volver a acceder a elementos
recientemente usados y acceder a elementos secuencialmente suele ser una
victoria.

Los algoritmos y las estructuras de datos varían en qué tan
efectivamente usan el caché. Por ejemplo:

- La búsqueda lineal hace buen uso del _lookahead_, pero requiere _O(n)_
comparaciones.
- La búsqueda binaria de una matriz ordenada requiere sólo _O(log(n))_
comparaciones.
- La búsqueda en un árbol _van Emde Boas_ es _O(log(n))_ y es ajeno al
caché.

¿Cuál elegir? Como en el pasado análisis, midiéndolo. La segunda tabla
muestra el tiempo requerido para buscar en matrices de enteros de 64
bits vía estos tres métodos. En mi computadora:

- La búsqueda lineal es competitiva para matrices pequeñas, pero pierde
exponencialmente para matrices grandes

- _van Emde Boas_ gana sin usar las manos, gracias a su patrones de
acceso predecible.

|Elementos| lineal  | binario |   vEB   |
|:--------|--------:|--------:|--------:|
| 8       | 50      | 90      | 40      |
| 64      | 180     | 150     | 70      |
| 512     | 1200    | 230     | 100     |
| 4096    | 17000   | 320     | 160     |



_“Pagas tu dinero y te llevas tu elección”. — [Punch][2]_

[1]: http://www.youtube.com/watch?v=t2JnCXvm_Qc)
[2]: http://www.nytimes.com/1988/02/28/magazine/on-language-you-pays-yer-money.html?pagewanted=all

Autor: Greg Colvin