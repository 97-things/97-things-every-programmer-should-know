# El Principio de Responsabilidad Única

Original: The Single Responsibility Principle

Uno de los principios fundamentales de un buen diseño es: reúna las
cosas que cambian por la misma razón y separe aquellas cosas que cambian
por diferentes razones.

Este principio es conocido también como el Principio de la
Responsabilidad Única o SRP (por sus siglas en inglés). En definitiva,
se dice que un subsistema, módulo, clase o incluso una función no debe
tener más de una razón para cambiar. El ejemplo clásico es una clase que
tiene métodos relacionados con reglas de negocio, reportes y base de
datos:

    public class Empleado {
      public Money calculaPago() ...
      public String reportaHoras() ...
      public void guardar() ...
    }


Algunos programadores podrían pensar que poner estas tres funciones en
la misma clase es perfectamente apropiado. Después de todo, se supone
que las clases son colecciones de funciones que operan sobre las
variables comunes. Sin embargo, el problema es que las tres funciones
cambian por razones totalmente distintas. La función `calculaPago`
cambiará cada vez que las reglas de negocio para calcular el pago
cambien. La función `reportaHoras` cambiará cada vez que alguien quiera
otro formato para el informe. La función `guardar` cambiará cada vez que
los DBA cambien el esquema de base de datos. Estas tres razones de
cambio se combinan para hacer a `Empleado` muy volátil. Cambiará por
alguna de estas razones. Más importante aún, las clase que depende de
`Empleado` será afectadas por estos cambios.

El buen diseño de sistemas significa que separamos el sistema en
componentes que pueden ser implementados de forma independientemente. La
implementación independiente significa que si cambiamos un componente no
tenemos que volver a implementar alguno de los otros. Sin embargo, si
`Empleado`es muy utilizado por muchas otras clases en otros componentes,
entonces es probable que cada cambio a `Empleado` cause que los otros
componentes tengan que volverse a implementar; negando así el mayor
beneficio del diseño de componentes (o SOA, si se prefiere un nombre más
de moda).


    public class Empleado {
      public Money calculaPago() ...
    }

    public class ReporteadorEmpleado {
      public String reportHora(Empleado e) ...
    }

    public class RepositorioEmpleado {
      public void guardar(Empleado e) ...
    }


La simple división mostrada arriba resuelve estos problemas. Cada una de
estas clases se puede colocar en un componente para sí mismas. O, mejor
dicho, todos las clases de reporteo pueden ir en el componente de
reporteo. Todas las clases relacionadas con base de datos pueden estar
en el componente de repositorios. Y todas las reglas de negocios pueden
entrar en el componente de reglas de negocio.

El lector astuto verá que aún existen dependencias en la solución
anterior. Ese `Empleado` aún depende de las otras clases. Si se modifica
`Empleado`, es probable que las otras clases se tengan que volver a
compilar e implementar. Por lo tanto `Empleado` no se puede modificar y
después implementar independientemente. Sin embargo, las otras clases
pueden ser modificadas e implementadas independientemente. Ninguna
modificación de alguna clase puede forzar a cualquiera de los otras a
ser recompiladas o reimplementadas. Incluso `Empleado` podría ser
implementada independientemente a través de un uso cuidadoso del
Principio de Inversión de Dependencias (DIP), pero eso es un tema para
[otro libro][1].

La aplicación cuidadosa del SRP, separando las cosas que cambian por
diferentes razones, es una de las claves para la creación de diseños que
tienen una estructura de componentes de implementación
independientemente.


[1]: http://www.amazon.com/dp/0135974445/

Autor: Uncle Bob