# Haz pruebas mientras duermes (y los fines de semana)

Original: Test While You Sleep (and over Weekends)

Tranquilo. No me refiero a centros de desarrollo a larga distancia,
horas extra en fin de semana o trabajar de noche. En vez de ello, quiero
llamar tu atención sobre la cantidad de poder de cómputo que tenemos a
disposición. Específicamente, cuánto no estamos aprovechando para hacer
nuestras vidas como programadores un poco más fáciles. ¿Constantemente
estás teniendo dificultades para tener suficiente poder de cómputo
durante la jornada de trabajo? Si es así, ¿qué están haciendo tus
servidores de prueba fuera de las horas de trabajo normal? A menudo
están sin carga durante la noche y los fines de semana. Puedes usar eso
a tu favor.

- ¿Te has sentido culpable de confirmar un cambio sin ejecutar todas las
pruebas? Una de las razones principales de que los programadores no
ejecutan los conjuntos de pruebas antes de hacer commit al código se
debe a la cantidad de tiempo que puede tomar. Cuando las fechas límite
se avecinan y la presión acecha, los humanos naturalmente empezamos a
tomar atajos. Una forma de abordar esto es romper los largos conjuntos
de pruebas en dos o más perfiles. Uno pequeño, un perfil de pruebas
obligatorio que sea rápido de ejecutar, te ayudará a asegurarte de que
las pruebas se ejecuten antes de cada commit. El total de lo perfiles
(incluyendo el perfil obligatorio, sólo para estar seguros) puede ser
automatizado para ejecutarse durante la noche, listo para reportar los
resultados en la mañana.
- ¿Has tenido suficiente oportunidad de poner a prueba la estabilidad de
tu producto? Las pruebas de más larga duración son vitales para
identificar fugas de memoria y otros problemas de estabilidad. Rara vez
se ejecutan durante el día, ya que consumen tiempo y recursos. Puedes
automatizar una carga de prueba durante la noche y una un poco más larga
durante el fin de semana. Del viernes 6.00 PM hasta las 6.00 AM del
siguiente lunes hay 60 horas de tiempo potencial para las pruebas.
- ¿Estás obteniendo tiempo de calidad en tu entorno de pruebas de
rendimiento? He visto altercados entre equipos para tener tiempo en
estos entornos. En la mayoría de los casos ningún equipo obtiene tiempo
de calidad durante el día, mientras que el ambiente está virtualmente
inactivo durante las horas posteriores. Los servidores y la red no está
ocupados durante la noche o los fines de semana. Es el momento ideal
para ejecutar algunas pruebas de rendimiento de calidad.
- ¿Hay demasiadas permutaciones de pruebas manuales? En muchos casos tu
producto está destinado a ser ejecutado en una variedad de plataformas.
Por ejemplo, en 32 y 64 bits, en Linux, Solaris y Windows, o simplemente
en diferentes versiones del mismo sistema operativo. Para empeorar las
cosas, muchas aplicaciones modernas son expuestas a una plétora de
mecanismos de transporte y protocolos (HTTP, AMQP, SOAP, CORBA,
etcétera). Probar manualmente todas estas permutaciones consume mucho
tiempo y comúnmente se realizan cerca de una fecha de liberación debido
a la presión de recursos. Por desgracia, puede ser demasiado tarde en el
ciclo para capturar desagradables errores.

Las pruebas automatizadas que se ejecutan durante la noche o fin de
semana asegurarán que todas estas permutaciones son puestas a prueba con
mayor frecuencia. Con un poco de pensamiento y algo de conocimiento de
secuencias de comandos (_scripting_) puedes programar unos cuantos
trabajos cron para poner en marcha algunas pruebas durante la noche y
los fines de semana. Hay también muchas herramientas de prueba por ahí
que podrían ser útiles. Algunas organizaciones incluso tienen granjas de
servidores que turnan servidores a través de diferentes departamentos y
equipos para asegurar que los recursos son utilizados eficientemente. Si
esto está disponible en tu empresa, puedes enviar las pruebas para que
sean ejecutadas en la noche o durante los fines de semana.

Autor: Rajith Attapattu