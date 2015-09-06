# Escribe las pruebas para las personas

Original: Write Tests for People

Estás escribiendo pruebas automatizadas para una parte o todo tu código
de producción. ¡Felicidades! ¿Estás escribiendo tus pruebas antes de que
escribas el código? ¡¡Mucho mejor!! El sólo hacerlo te convierte en uno
de los primeros adoptantes de las más avanzadas prácticas de la
ingeniería de software. Pero, ¿estás escribiendo buenas pruebas? ¿Cómo
saberlo? Una manera es preguntar: “¿para quién estoy escribiendo estas
pruebas?”. Si la respuesta es “para mí, para ahorrarme el esfuerzo de
corregir errores” o “para el compilador, con eso puede ser ejecutado”,
entonces las apuestas están en que no estás escribiendo las mejores
pruebas posibles. Así que, ¿para quién deberías estar escribiendo las
pruebas? Para las personas que tratan de entender tu código.

Las buenas pruebas actúan como documentación para el código que estás
probando. Describen cómo funciona el código. Por cada escenario de uso
la(s) prueba(s): Describe el contexto, un punto inicial o precondiciones
que deben ser satisfechas; ilustra cómo el software es invocado;
describe los resultados esperados o poscondiciones a ser verificadas.

Los diferentes escenarios de uso tendrán una versión distinta de cada
una de ellas. Las personas que tratan de entender tu código deberían
poder mirar unas cuantas pruebas y, al comparar estas tres partes de las
pruebas en cuestión, ver qué causa que el código se comporte diferente.
Cada prueba debería ilustrar claramente la relación de causa y efecto
entre estas tres partes. Esto implica que lo que no es visible en las
pruebas es tan importante como lo que es visible. Mucho código en las
pruebas distrae al lector con trivialidades sin importancia. Cuando sea
posible oculta dichas trivialidades detrás de llamados a métodos con
significado; la refactorización “Extraer Método” es tu mejor amigo. Y
asegúrate de darle a cada prueba un nombre con significado que describa
el escenario de uso particular, con esto el lector de la prueba no tiene
que hacer ingeniería inversa de cada prueba para entender de qué se
tratan los distintos escenarios. Entre ellos, el nombre de las clases de
prueba y los métodos de clases deben incluir, al menos, el punto inicial
y cómo el software está siendo invocado. Esto permite que la cobertura
de prueba sea verificada vía un rápido escaneo de los nombres de los
métodos. También puede ser útil incluir los resultados esperados en el
nombre del método de prueba, mientras esto no cause que el nombre sea
demasiado largo para ver o leer.

También es buena idea poner a prueba tus pruebas. Puedes verificar que
detectan el error al incluir dicho error en el código de producción (por
supuesto, en una copia privada que desecharás). Asegúrate que reporte
los errores de manera significativa. También debes verificar que tus
pruebas hablan claramente a una persona que trata de entender tu código.
La única manera de hacerlo es tener a alguien que no está familiarizado
con tu código para que lea tus pruebas y te diga qué ha aprendido.
Escucha cuidadosamente lo que te diga. Si no entendió algo no es porque
no sea muy brillante. Es más probable que tú no fueras muy claro.
(¡Continúa e invierte los roles, lee sus pruebas!).

Autor: Gerard Meszaros