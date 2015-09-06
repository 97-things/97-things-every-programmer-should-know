# La regla de oro del diseño de API

Original: The Golden Rule of API Design

El diseño de API es difícil, particularmente los grandes. Si estás
diseñando una API que va a tener cientos o miles de usuarios, tienes que
pensar qué podrías cambiar en el futuro y si los cambios pueden romper
el código de tu cliente. Más allá de esto, tienes que pensar cómo te
afectan los usuarios de tu API. Si unas de tus clases API usa uno de sus
métodos internamente, tienes que recordar que un usuario podría hacer
una subclase de tu clase y sobrescribirla, y eso puede ser desastroso.
No podrías ser capaz de cambiar ese método porque alguno de tus usuarios
le ha dado un significado diferente. Tus futuras opciones de
implementación interna están a merced de tus usuarios..

Los desarrolladores de API solucionan este problema de varias formas,
pero la más fácil es bloquear el API. Si estás trabajando en Java quizás
estés tentado a hacer `final` a la mayoría de tus clases y métodos. En
C# podrías hacer `sealed` tus clases y métodos. Independientemente del
lenguaje que estés usando, podrías estar tentado a presentar tu API a
través de un singleton o usar métodos _factory_ estáticos, así puedes
defenderte de la gente que podría sobrescribir el comportamiento y usar
tu código de formas que podrían restringir tus opciones más adelante.
Todo esto parece razonable, pero ¿lo es realmente?

En la última década nos hemos dado cuenta gradualmente de que las
pruebas unitarias son una parte importante de la práctica, pero esa
lección no ha penetrado completamente la industria. La evidencia está a
nuestro alrededor. Toma arbitrariamente una clase que no ha sido probada
y que use un API de terceros e intenta escribir una prueba unitaria
para él. La mayoría de las veces encontrarás problemas. Encontrarás
que el código usando el API se pega a él como con pegamento. No hay
manera de impersonalizar las clases del API para que puedas detectar
las interacciones de tu código con ellos o proporcionar valores de
retorno para la prueba.

Con el tiempo, esto va a mejorar, pero sólo si empezamos a ver las
pruebas como un caso de uso real cuando diseñamos API.
Desafortunadamente, es un poco más complicado que sólo probar nuestro
código. Es aquí donde encaja la Regla de Oro del diseño de API: no es
suficiente escribir pruebas del API que desarrollas; tienes que escribir
pruebas unitarias para el código que usa tu API. Cuando lo haces
aprendes de primera mano los obstáculos que tus usuarios tendrán que
superar cuando intenten probar su código independientemente.

Cuando no hay una forma única de hacer fácil para los desarrolladores el
probar el código que usa tu API, ni `static`, `final` o `sealed` son
inherentemente malos constructos. A veces pueden ser útiles, pero es
importante tener en cuenta el tema de las pruebas y, para lograrlo,
tienes que experimentarlo tú mismo. Una vez que lo haces, puedes
enfocarlo como lo harías con cualquier otro reto de diseño.

Autor: Michael Feathers