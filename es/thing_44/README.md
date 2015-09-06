# Las herramientas Unix son tus amigas

Original: The Unix Tools Are Your Friends

Si en mi camino al exilio en una isla desierta tuviera que escoger entre
un IDE y un conjunto de herramientas Unix, yo escogería las herramientas
Unix sin pensarlo dos veces. Aquí están las razones por las cuáles
deberías dominar las herramientas Unix.

Primero, los IDE se enfocan en lenguajes específicos, mientras las
herramientas Unix pueden trabajar con cualquier cosa que aparezca en
modo textual. En los ambientes de desarrollo de hoy en día, donde los
nuevos lenguajes y notaciones florecen cada año, aprender a trabajar de
la forma Unix es una inversión que se pagará con el tiempo una y otra
vez.

Además, mientras los IDE ofrecen sólo los comandos que sus
desarrolladores concibieron, con las herramientas Unix puedes realizar
cualquier tarea imaginable. Piensa en ello como (los clásico pre-
Biónico) bloques Lego: creas tus propios comandos combinando las
pequeñas pero versátiles herramientas Unix. Por ejemplo, la siguiente
secuencia es una implementación basada en texto del análisis de firmas
de Cunningam; una secuencia de cada punto y coma, llaves y comillas que
puede revelar mucho sobre el contenido del archivo:

    for i in *.java; do echo -n "$i: " sed 's/[^"{};]//g' $i | tr -d
    '\n' echo done

En suma, cada operación del IDE que aprendes es específica a esa tarea;
por ejemplo, agregar un nuevo paso de depuración en la configuración de
construcción del proyecto. En contraste, afilar tus habilidades con las
herramientas Unix te hace más efectivo en cualquier tarea. Como un
ejemplo, he empleado la herramienta sed en la secuencia de comandos
precedentes para modificar la construcción de un proyecto para la
compilación cruzada en múltiples arquitecturas de procesador.

Las herramientas Unix fueron desarrolladas en una época en la que una
computadora multiusuario tenía 128kB de RAM. El ingenio que tuvo su
diseño significa que en estos días pueden manejar enormes conjuntos de
datos con extremada eficiencia. La mayoría de las herramientas trabajan
como filtros, procesando sólo una línea a la vez, significando que no
hay límite superior en la cantidad de datos que pueden manejar. ¿Quieres
buscar un número de ediciones almacenadas en medio terabyte del respaldo
de la Wikipedia en inglés? La simple invocación de


    grep '<revision>' | wc –l

te dará la respuesta sin siquiera sudar. Si encuentras una secuencia de
comandos útil, puedes empacarla fácilmente en un script de shell, usando
algunos poderosos constructos de programación, tales como hacer piping
de datos en ciclos y condicionales. Más impresionante aún, los comandos
Unix ejecutados como _pipelines_, como el arriba descrito, distribuirá
su carga con naturalidad a través de las muchas unidades de
procesamiento de los CPU multi-core modernos.

Su génesis en “pequeño es bello” y las implementaciones de software libre
de las herramientas Unix las hacen disponibles ubicuamente, incluso en
plataformas de recursos restringidos, como mi reproductor multimedia de
la sala o el router DSL. Es poco probable que tales dispositivos
ofrezcan una poderosa interface gráfica, pero frecuentemente incluyen la
aplicación BusyBox, la cual provee la mayoría de las herramientas
comúnmente usadas. Y si estás desarrollando en Windows, el ambiente
cygwin te ofrece todas las herramientas Unix imaginables, en forma de
ejecutable y código fuente.

Por último, si ninguna de las herramientas disponibles se adecua a tus
necesidades, es muy fácil extender el mundo de las herramientas Unix.
Sólo escribe un programa (en cualquier lenguaje que elijas) que juegue
con unas pocas y sencillas reglas: tu programa debe realizar sólo una
tarea sencilla; debe leer datos como líneas de texto de su entrada
estándar y debe mostrar los resultados sin adornos, encabezados ni otros
ruidos en su salida estándar. Los parámetros que afectan la operación de
la herramienta se dan en la línea de comandos. Sigue estas reglas y
“tuya será la Tierra y todo lo que hay en ella”.

Autor: Diomidis Spinellis