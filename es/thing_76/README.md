# Pon todo bajo Control de Versiones

Original: Put Everything Under Version Control

Pon todo lo que tienen tus proyectos bajo control de versiones. Los
recursos que necesitas están ahí: herramientas libres como Subversion,
Git, Mercurial y CVS; abundante espacio en disco; servidores baratos y
poderosos; una red ubicua; e incluso servicios de hospedaje de
proyectos. Después de instalar el software de control de versiones todo
lo que necesitas para poner tu trabajo en su repositorio es ejecutar el
comando apropiado en un directorio limpio que contenga tu código. Y sólo
hay dos nuevas operaciones básicas por aprender: enviar el cambio en tus
códigos al repositorio y actualizar tu directorio de trabajo a la
versión del repositorio.

Una vez que el proyecto está bajo el control de versiones es obvio que
puedes rastrear su historia, ver quién ha escrito qué código, y referir
una versión del archivo o proyecto a través de un identificador único.
Más importante, puedes hacer grandes cambios sin miedo; no más código
comentado, sólo en caso de que lo necesites en el futuro, porque la
versión anterior vive de manera segura en el repositorio. Puedes (y
deberías) etiquetar una versión de software con un nombre simbólico, así
podrás revisitarlo en el futuro en la versión exacta del software que tu
cliente ejecuta. Puedes crear ramificaciones de desarrollo paralelo: la
mayoría de los proyectos tienen una rama de desarrollo activo y una o
varias más de mantenimiento de versiones publicadas que son apoyadas
activamente.

Un sistema de control de versión minimiza la fricción entre
desarrolladores. Cuando los programadores trabajan en partes diferentes
del software esto se integra casi por arte de magia; cuando se empalma
el código el sistema lo nota y permite que resuelvan los conflictos. Con
un poco de configuración adicional el sistema puede notificar a todos
los desarrolladores de cada cambio enviado, estableciendo un
entendimiento común sobre el progreso del proyecto.

Al configurar el proyecto no seas tacaño: coloca todos los activos del
proyecto bajo control de versiones. Además del código fuente, incluye la
documentación, herramientas, scripts de creación, casos de prueba, obras
de arte, e incluso bibliotecas. Con el proyecto completo y seguro en el
repositorio (respaldado regularmente) se reduce al mínimo el daño de
perder tu disco o datos. Configurar el ambiente de desarrollo en una
máquina nueva consiste simplemente en traerse el proyecto desde el
repositorio. Esto simplifica la distribución, construcción y las pruebas
de código en diferentes plataformas: en cada máquina un simple comando
de actualización se asegurará que el software está en la versión actual.

Una vez que ha visto la belleza de trabajar con un sistema de control de
versiones, seguir unas cuantas reglas hará que tú y tu equipo sean más
eficaces:

* Enviar cada cambio lógico en una operación separada. Agrupar muchos
cambios hará difícil desenredarlo en el futuro. Esto es especialmente
importante al hacer una refactorización en todo el proyecto o cambios de
estilo, los cuales pueden oscurecer otras modificaciones.
* Acompañar cada envío con un mensaje explicativo. Como mínimo describir
brevemente lo que ha cambiado, pero si también deseas grabar la
justificación del cambio, entonces éste es el mejor lugar para
almacenarlo.
* Por último, no enviar código que rompa la construcción de un proyecto,
de lo contrario se volverá impopular con los otros desarrolladores del
proyecto.

La vida bajo un control de versión es demasiado buena como para
arruinarla con errores fácilmente evitables.

Autor: Diomidis Spinellis