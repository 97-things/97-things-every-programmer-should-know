# Los grandes datos interconectados pertenecen a una base de datos

Original: Large Interconnected Data Belongs to a Database

Si tu aplicación está manejando un conjunto de elementos de datos
grandes, persistentes e interconectados, no dudes en almacenarlos en una
base de datos relacional. En el pasado los Sistemas de Administración de
Bases de Datos Relacionales (RDBMS, por sus siglas en inglés) solían ser
caros, escasos, complejos y unas bestias indomables. Ya no es el caso.
Hoy en día los RDBMS son fáciles de encontrar, lo más probable es que el
sistema que estás usando ya tenga uno o dos instalados. Algunos RDBMS
muy capaces, como MySQL y PostgreSQL, están disponibles como software
libre, por lo que el costo de compra ya no es un tema. Aún mejor, los
llamados sistemas de bases de datos embebidos se pueden vincular como
bibliotecas directamente en tu aplicación, requiriendo casi ninguna
configuración o administración; dos notables proyectos de software libre
son SQLite y HSQLDB. Estos sistemas son extremadamente eficientes.

Si los datos de tu aplicación son más grandes que la RAM del sistema,
una tabla indexada del RBDMS tendrá un rendimiento de órdenes de
magnitud más rápida que la colección de mapas de tu biblioteca, que
gastará páginas de memoria virtual. Los productos de bases de datos
modernos pueden crecer fácilmente con tus necesidades. Con el cuidado
adecuado, puedes ampliar una base de datos embebida a un sistema más
grande cuando sea requerido. Después, puedes cambiar de un producto de
software libre a uno mejor soportado o un sistema propietario más
poderoso.

Una vez que sepas los trucos de SQL, la creación de aplicaciones
centradas en bases de datos es una alegría. Después de que hayas
almacenado tus datos correctamente normalizados en la base de datos es
fácil extraer eficientemente los hechos con una consulta SQL legible; no
hay necesidad de escribir ningún código complejo. Un solo comando SQL
puede realizar cambios de datos complejos. Para modificaciones únicas,
digamos, un cambio en la forma en que organizas los datos, ni siquiera
necesitas escribir código: sólo lanza la interface directa de SQL. Esta
misma interface también te permite experimentar con consultas, dejando a
un lado el ciclo de compilación-edición de un lenguaje de programación
regular.

Otra de las ventajas de basar tu código en un RDBMS implica manejar las
relaciones entre los elementos de tus datos. Puedes describir las
limitaciones de consistencia en los datos en una manera declarativa,
evitando el riesgo de que los apuntadores se cuelguen si olvidas
actualizar los datos en un caso extremo. Por ejemplo, puedes especificar
que en caso de que un usuario sea eliminado, entonces los mensajes
enviados por ese usuario deberían ser eliminados también.

También puedes crear enlaces eficientes entre tus entidades almacenadas
en la base de datos en el momento que lo desees, simplemente creando un
índice. No hay necesidad de realizar caras y extensas refactorizaciones
de campos de clases. Además, codificar en torno a una base de datos
permite que varias aplicaciones accedan a tus datos en manera segura.
Esto hace fácil actualizar tu aplicación para el uso concurrente y
también permite codificar cada parte de tu aplicación usando el lenguaje
y plataforma más adecuada. Por ejemplo, puedes escribir el _back-end_
XML de una aplicación web en Java, algunos scripts de autoría en Ruby y
una interfaz de visualización en Processing.

Finalmente, recuerda que el RDBMS sudará duro para optimizar los
comandos SQL, lo que te permitirá concentrarte en la funcionalidad de tu
aplicación en vez de la refinación de algoritmos. Los sistemas avanzados
de bases de datos incluso tomarán ventaja de los procesadores multi-core
a tus espaldas. Y, conforme la tecnología mejora, también el rendimiento
de tu aplicación

Autor: Diomidis Spinellis