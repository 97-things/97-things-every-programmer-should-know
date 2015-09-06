# Un binario

Original: One Binary

He visto muchos proyectos en los cuales la compilación reescribe alguna
parte del código para generar un binario personalizado para cada
ambiente destino. Esto siempre hace las cosas más complicadas de lo que
deberían ser, e introduce el riesgo de que el equipo podría no tener
versiones consistentes en cada instalación. Como mínimo involucra la
compilación de múltiples, casi idénticas copias de software, cada una
tiene que ser desplegada en el lugar correcto. Significa más partes
movibles de lo necesario, lo que significa más oportunidad de cometer un
error.

Una vez trabajé en un equipo en el cual cada cambio tenía que ser
revisado en cada ciclo de compilación, por los que los testers se
quedaban esperando cada que se necesitaba un ajuste menor (¿mencioné que
la compilación tomaba también mucho tiempo?). También trabajé en un
equipo en el que los administradores de sistemas insistían en
reconstruir desde cero en producción (usando el mismo script que
hicimos), lo que significaba que no teníamos pruebas de que la versión
en producción era la misma que había estado bajo prueba. Y así por el
estilo.

La regla es sencilla: compila un sólo binario que puedas identificar y
promover a través de todas las etapas en la línea de liberación. Mantén
detalles específicos del entorno en el ambiente. Esto podría significar,
por ejemplo, mantenerlos en el contenedor de componentes, en un archivo
conocido o en la ruta.

Si tu equipo tiene un revoltijo de código para compilar o almacenar
todas las configuraciones destino en el código, esto sugiere que nadie
ha pensado el diseño con el suficiente cuidado para separar estas
características, que son fundamentales de la aplicación, de aquellas que
son específicas de las plataforma. O podría ser peor: el equipo sabe qué
hacer, pero no puede priorizar el esfuerzo para hacer el cambio.

Por supuesto, hay excepciones: podrías estar compilando para algún
destino que tiene importantes restricciones de recursos, pero esto no
aplica para la mayoría de nosotros que estamos escribiendo aplicaciones
de “bases de datos a pantalla y de regreso”. Alternativamente, podrías
estar viviendo con algún desorden heredado que es muy difícil de
corregir ahora mismo. En tales casos, tienes que mover gradualmente,
pero empezar tan pronto como sea posible.

Una cosa más: [mantén la información del entorno con algún control de
versiones](pon-todo-bajo-control-de-versiones). No hay nada peor que
romper una configuración de entorno y no ser capaz de imaginarte qué
cambió. La información de entorno debería ser versionada separadamente
del código, ya que cambiará a diferentes periodos y por diferentes
razones. Algunos equipos usan sistemas de control de versiones
distribuidos para esto (como bazaar y git), ya que hacen más fácil de
enviar cambios hechos en ambientes de producción –como sucede
inevitablemente– de vuelta al repositorio.

Autor: Steve Freeman