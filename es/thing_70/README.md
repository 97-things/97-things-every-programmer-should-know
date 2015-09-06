# ¡No toques ese código!

Original: Don't Touch that Code!

Nos ha pasado a todos en algún momento. Tu código fue llevado al
servidor de _staging_ para las pruebas del sistema y el director de
pruebas te lo regresa diciendo que tiene un problema. Tu primera
reacción es “rápido, déjame arreglarlo, sé qué está mal”.

En un sentido más amplio, sin embargo, lo que está mal es que como
desarrollador creas que deberías tener acceso al servidor de _staging_.

En la mayoría de los ambientes de desarrollo basado en web la
arquitectura puede fragmentarse así:

- Desarrollo local y pruebas unitarias en la máquina del desarrollador.
- Servidor de desarrollo, en el que se realizan las pruebas de
integración, manuales o automáticas.
- Servidores de _staging_, en el cual el equipo de Control de Calidad y
los usuarios realizan las pruebas de aceptación.
- Servidor de producción.

Sí, hay otros servidores y servicios salpicados por ahí, como el control
de código fuente (SCC, _Source Code Control_) y el sistema de tickets,
pero tienes la idea. Usando este modelo, un desarrollador –incluso un
desarrollador experimentado– nunca debería tener acceso más allá del
servidor de desarrollo. La mayor parte del desarrollo es hecho en la
máquina del desarrollador usando su mezcla favorita de IDE, máquinas
virtuales y una apropiada cantidad de magia negra para la buena suerte.

Una vez que el código se envía al SCC, ya sea automática o manualmente,
debería ser pasado al servidor de desarrollo, en el cual puede ser
probado y ajustado, si es necesario, para asegurarse de que todo
funciona. A partir de este momento, sin embargo, el desarrollador es un
espectador en el proceso.

El director de _staging_ debería empaquetar y desplegar el código al
servidor de _staging_ del equipo de Control de Calidad. Así como los
desarrolladores deberían no tener acceso a nada más allá del servidor de
desarrollo, el equipo de Control de Calidad y los usuarios no tienen
necesidad de tocar nada en el servidor de desarrollo. Si está listo para
las pruebas de aceptación, libéralo y envíalo, no pidas al usuario
“mirar algo muy rápido” en el servidor de desarrollo. Recuerda, a menos
que estés codificando el proyecto tú solo, que otras personas tienen
código ahí y podría no estar listo para lo mire el usuario. El encargado
de liberaciones es la única persona que debería tener acceso a ambos.

Bajo ninguna circunstancia –nunca, en lo absoluto– debe un desarrollador
tener acceso al servidor de producción. Si hay algún problema, el
personal de soporte debería solucionarlo o requerir que lo arreglen.
Después de enviarlo al SCC, ellos pasarán un parche desde ahí. Algunos
de los mayores desastres de programación de los que he sido parte han
tenido lugar porque alguien _ejeeemmm**yo**eejeeemm_ violó esta última
regla. Si está descompuesto, producción no es el lugar para arreglarlo..

Autor: Cal Evans