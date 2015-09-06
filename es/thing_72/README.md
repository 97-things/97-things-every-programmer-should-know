# Los números de punto flotante no son reales

Original: Floating-point Numbers Aren't Real

Los números de punto flotante no son “números reales” en el sentido
matemático, a pesar de que son llamados _reales_ en algunos lenguajes de
programación, como Pascal y Fortran. Los números reales tienen una
precisión infinita y son, por lo tanto, continuos y sin pérdidas; los
números de punto flotante tiene precisión limitada, por lo que son
finitos, y son recordados como enteros “con mal comportamiento”, porque
no son están espaciados uniformemente a través de su espacio de
distribución.

Para ilustrarlo, asigna 2147483647 (el número más grande en un entero de
32 bits) a una variable `float` de 32 bits (digamos x) e imprímelo.
Verás 2147483648. Ahora imprime `x - 64`. Aún 2147483648. Ahora calcula
`x - 65` y ¡obtendrás 2147483520! ¿Por qué? Porque la separación entre
flotantes adyacentes en ese rango es de 128 y las operaciones de punto
flotante se redondean al punto flotante más cercano.

Los números de punto de flotante de la IEEE son números de precisión
fija basados en notación científica de base 2:
_1.d<sub>1</sub>d<sub>2</sub>...d<sub>p-1</sub> x 2<sup>e</sup>_, donde
*p* es la precisión (24 para `float`, 53 para `double`). El
espaciamiento entre dos números consecutivos es _2<sup>1-p+e</sup>_, lo
cual puede ser aproximado con seguridad a ε|x|, donde ε es el épsilon de
la máquina (2<sup>1-p</sup>).

Conocer el espaciamiento en los vecinos de un número de punto flotante
puede ayudarte a evitar errores numéricos clásicos. Por ejemplo, si
estás realizando un cálculo iterativo, como buscar la raíz de una
ecuación, no tiene sentido buscar una precisión más grande que el
sistema numérico puede darte en la cercanía de la respuesta. Asegúrate
que la tolerancia que pides no es menor que el espaciado ahí; de otro
modo harás un bucle infinito.

Debido a que los números de punto flotante son aproximaciones de los
números reales, inevitablemente hay un pequeño error presente. Este
error, llamado redondeo, puede llevarnos a errores sorpresivos. Por
ejemplo, cuando sustraes números cercanamente iguales, los dígitos más
significativos se cancelan entre sí, entonces lo que era el dígito menos
significativo (donde reside el error de redondeo) es promovido a la
posición más significativa en el resultado de punto flotante,
contaminando esencialmente cualquier cómputo relacionado (un fenómeno
conocido como _smearing_). Necesitas mirar muy de cerca tus algoritmos
para prevenir esa cancelación catastrófica. Para ilustrarlo, considera
resolver la ecuación _x<sup>2</sup> - 100000x + 1 = 0_ con la fórmula
cuadrática. Como los operandos en la expresión _-b + sqrt(b<sup>2</sup>
- 4)_ son cercanamente iguales en magnitud, puedes en su lugar computar
la raíz _r<sub>1</sub> = -b - sqrt(b<sup>2</sup> -4)_, y entonces
obtener _r<sub>2</sub> = 1/r<sub>1</sub>_, como en cualquier ecuación
cuadrática, _ax<sup>2</sup> + bx + c = 0_, entonces la raíz satisface
_r<sub>1</sub>r<sub>2</sub> = c /a_.

El _smearing_ puede ocurrir incluso en formas más sutiles. Supón una
librería que ingenuamente computa _e<sup>x</sup>_ con la fórmula _1 + x
+ x<sup>2</sup>/2 + x<sup>3</sup>/3! +_ ... Esto funciona bien para una
x positiva, pero considera qué pasa cuando x es un número negativo
grande. Los términos impares potenciados resultan en un número positivo
grande y sustrayendo las magnitudes de pares potenciados ni se verán
afectados en el resultado. El problema aquí es que el redondeo en los
grandes términos positivos está a un dígito de posición de la más grande
significancia que la verdadera respuesta. ¡La respuesta difiere hacia
positivo infinitamente! La solución aquí también es simple: para una x
negativa, computa _e<sup>x</sup> = 1/ e<sup>|x|</sup>_.

No podemos irnos sin decir que no deberías usar números de punto
flotante para aplicaciones financieras, para eso son las clases
decimales en lenguajes como Python y C#. Los números de punto flotante
son para un cómputo científico eficiente. Pero la eficiencia es inútil
sin precisión, ¡así que recuerda la fuente de los errores de redondeo y
codifica en consecuencia!

Autor: Chuck Allison