# Automatiza el estándar de codificación

Original: Automate Your Coding Standard

Probablemente a ti también te sucedió. Al comenzar un proyecto todo el
mundo tiene buenas intenciones; las llamaremos “resoluciones de proyecto
nuevo”. A menudo, muchas de estas resoluciones se documentan, y las que
tienen que ver con el código terminan en el estándar de codificación del
proyecto. Durante la primera reunión, el jefe de desarrollo revisa la
documentación y, en el mejor de los casos, todos aceptan que intentarán
respetarla. Sin embargo, una vez que el proyecto se pone en marcha, las
buenas intenciones se van dejando de lado, una a una. Para cuando se
entrega el proyecto, el código es un desastre y nadie parece saber por
qué.

¿En qué momento salieron mal las cosas? Probablemente desde la reunión
inicial. Algunos miembros no estaban prestando atención; otros no lo
consideraron importante. Para peor, algunos no estuvieron de acuerdo y
ya estaban planeando rebelarse en contra del estándar. Por último,
algunos sí lo comprendieron y estuvieron de acuerdo pero, cuando la
presión del proyecto fue demasiada, tuvieron que dejar de lado algunas
convenciones. Aplicar un buen formato al código no te hará ganar puntos
con un cliente que desea más funcionalidad. De hecho, respetar un
estándar de codificación puede ser bastante aburrido si la función no
está automatizada: intenta indentar una clase a mano para comprobarlo
por tu cuenta.

Pero si es tan problemático, ¿para qué queremos un estándar de
codificación? Una de las razones para darle un formato uniforme al
código es que, de este modo, nadie se “adueñará” del código que escriba
utilizando un formato propio. Probablemente queremos evitar que los
programadores utilicen ciertos antipatrones, para así ahorrarnos algunos
errores comunes. En general, un estándar de codificación debería hacer
más fácil el trabajo grupal de un proyecto y mantener la velocidad de
desarrollo desde el principio hasta el final. Se deduce entonces que
todos deberían estar de acuerdo con el estándar; no ayuda que un
programador utilice tres espacios para indentar y otro utilice cuatro.

Hay una gran cantidad de herramientas que se pueden usar para producir
reportes de calidad de código, y para documentar y mantener el estándar
de codificación, pero ésa no es la solución completa. El estándar
debería automatizarse e imponerse siempre que sea posible. Por ejemplo,
de las siguientes maneras:

- Asegúrate de que parte del proceso de compilación sea darle formato al
código, de modo que todo el mundo lo realice cada vez que se compile la
aplicación.
- Utiliza herramientas de análisis de código estático para encontrar
antipatrones. Si se encuentra alguno, detén la compilación.
- Aprende a configurar estas herramientas para que detecten antipatrones
definidos por ti mismo y para tus proyectos específicos.
- Mide la cobertura del código, pero también evalúa automáticamente los
resultados. Nuevamente, detén la compilación si los resultados son muy
bajos.

Intenta aplicar esto en todo lo que consideres de importancia, aunque no
te será posible automatizarlo todo. Las cosas que no puedas marcar o
corregir automáticamente podrían agruparse en un conjunto de directrices
suplementarias al estándar automatizado, pero ten en cuenta que
probablemente tú y tus colegas no lo respeten con la misma diligencia.

Por último, el estándar de codificación debería ser dinámico y no
estático. A medida que el proyecto evolucione, sus necesidades también
irán cambiando, y lo que quizás pareció inteligente en un principio, no
será necesariamente inteligente algunos meses después.

Autor: Filip van Laenen