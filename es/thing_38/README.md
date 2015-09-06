# Evita errores

Original: Prevent Errors

Los mensajes de error son la interacción más crítica entre el usuario y
el resto del sistema. Suceden cuando la comunicación, entre el usuario y
el sistema, está cerca del punto de quiebre.

Es fácil pensar que un error está siendo causado por una mala entrada de
datos del usuario. Pero la gente comete errores de forma predecible y
sistemática. Así que es posible depurar la comunicación entre el usuario
y el resto del sistema así como lo harías con otros componentes del
sistema.

Por ejemplo, digamos que quieres que el usuario introduzca una fecha en
un rango permitido. En vez de dejar que el usuario introduzca cualquier
fecha es mejor ofrecer un dispositivo, como una lista o calendario,
mostrando sólo las fechas permitidas. Esto elimina cualquier oportunidad
de que el usuario introduzca una fecha fuera del rango.

El formato del error es otro problema común. Por ejemplo, si a un
usuario se le presenta un campo de texto como fecha e introduce una
fecha ambigua como “Julio 29, 2012” es razonable el rechazarlo
simplemente porque no es uno de los formatos preferidos (como
“DD/MM/AAAA”). Es peor aún rechazar “29 / 07 / 2012” sólo porque
contiene espacios extra; este tipo de problema es particularmente
difícil de entender para usuarios porque la fecha parece estar en el
formato deseado.

Este error ocurre porque es más fácil rechazar una fecha que analizar
los tres o cuatro formatos de fecha más comunes. Este tipo de errores
insignificantes llevan al usuarios a la frustración, que a su vez
conduce a errores adicionales conforme el usuario pierde su
concentración. En cambio, respeta las preferencias del usuario al entrar
información, no los datos.

Otra forma de evitar errores de formato es ofrecer señales, por ejemplo,
con una etiqueta dentro del campo mostrar el formato deseado
(“DD/MM/AAAA”). Otra pista podría ser dividir el campo en tres cajas de
texto de dos, dos y cuatro caracteres.

Las señales son diferentes de las instrucciones: las señales tienden a
ser indicios; las instrucciones son detalladas; las señales ocurren en
el punto de interacción; las instrucciones aparecen antes del punto de
interacción. Las señales proveen contexto; las instrucciones dictan el
uso.

En general, las instrucciones son ineficientes para prevenir errores.
Los usuarios tienden a asumir que las interfaces trabajarán en la línea
con su pasada experiencia (“¿seguramente todos saben el significado de
‘Julio 29, 2012’?”). Así que las instrucción no son leídas. Las señales
dan un suave codazo alejando a los usuarios del error.

Otra forma de evitar errores es ofrecer valores predeterminados. Por
ejemplo, los usuarios típicamente introducen valores que corresponden al
hoy, mañana, mi cumpleaños, mi fecha límite o la fecha que introduje la
última vez que usé este formulario. Dependiendo del contexto, es
probable que uno de ellos sea una buena opción de un valor
predeterminado inteligente.

Sin importar la causa, los sistemas deberían ser tolerantes a errores.
Puedes hacer esto proveyendo niveles múltiples de “deshacer” para todas
las acciones y en especial las acciones que tenga el potencial de
destruir o enmendar los datos del usuario.

El registro y análisis de las acciones de “deshacer” puede también ser
un punto a destacar, en el cual la interfaz está atrayendo a los
usuarios a errores inconscientes, tales como hacer clic persistentemente
en un botón “equivocado”. Estos errores son, a menudo, causados por
señales engañosas o secuencias de interacción que puedes rediseñar para
prevenir más errores.

Cualquiera que sea el enfoque que tomes, la mayoría de los errores son
sistemáticos, el resultado de malentendidos entre el usuario y el
software. Entender cómo los usuarios piensan, interpretan información,
toman decisiones e introducen datos, de entrada, te ayudará a depurar
las interacciones entre el software y tus usuarios.

Autor: Giles Colborne