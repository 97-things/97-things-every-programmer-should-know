# La conveniencia no es una -bilidad

Original: Convenience Is not an -ility

Mucho se ha dicho acerca de la importancia y desafíos al diseñar una
buena API. Es difícil hacerlo bien la primera vez y es incluso más
difícil cambiarlo después. Algo así como la crianza de niños. La mayoría
de los programadores experimentados han aprendido que una buena API
sigue un nivel consistente de abstracción, exhibe consistencia y
simetría, y forma el vocabulario para un lenguaje expresivo. Por lo
tanto, estar consciente de los principios guía no se traduce
automáticamente en un comportamiento adecuado. Comer dulces es malo para
ti.

En vez de predicar desde las alturas, quiero tomar una “estrategia”
específica de diseño de API, una que me encuentro una y otra vez: el
argumento de conveniencia. Comienza típicamente con los siguientes
“puntos de vista”:

- No quiero que otras clases tengan que hacer dos llamadas separadas
para hacer una cosa.
- ¿Por qué debería hacer otro método si es casi igual que éste? Sólo
agregaré un switch sencillo.
- Mira, es muy fácil: si el segundo parámetro de cadena termina con
“.txt”, el método automáticamente asume que el primer parámetro es el
nombre de archivo, por lo que no necesito realmente dos métodos.

Aunque sea bien intencionado, tales argumentos son propensos a disminuir
la legibilidad del código al usar el API. Una invocación de método como
esta:


    parser.processNodes(text, false);

no tiene virtualmente algún significado si no sabemos la implementación,
o al menos consultar la documentación. Este método fue probablemente
diseñado para la comodidad del implementador como un opuesto de la
conveniencia de quien llama. “No quiero que quien hace la llamada tenga
que hacer dos llamadas separadas” se traduce en: “no quería codificar
dos métodos separados”. No hay nada fundamentalmente malo con la
conveniencia si tiene intención de ser el antídoto del tedio, falta de
idea o incomodidad. Sin embargo, si pensamos más cuidadosamente en ello,
el antídoto para esos síntomas es la eficiencia, consistencia y
elegancia, no necesariamente la conveniencia. Se supone que el API
oculta la complejidad subyacente, podemos esperar de manera realista que
un buen diseño de API requiere algo de esfuerzo. Un solo método largo
podría ser ciertamente más conveniente de escribir que un bien pensado
conjunto de operaciones, pero ¿sería fácil de usar?

La metáfora del API como un lenguaje puede guiarnos hacia mejores
decisiones de diseño en estas situaciones. Un API debe proporcionar un
lenguaje expresivo, lo cual nos da en el siguiente nivel suficiente de
vocabulario para preguntar y responder preguntas útiles. Esto no implica
que debería proveer exactamente un método o verbo por cada pregunta que
valga la pena. Un vocabulario diverso nos permite expresar matices de
significado. Por ejemplo, preferimos decir `correr` en vez de
`caminar(true)`, a pesar de que podría ser visto como esencialmente la
misma operación, sólo ejecutada en una velocidad distinta. Un
vocabulario API consistente y bien pensado hace expresivo y fácil de
entender el código del siguiente nivel. Más importante aún, un
vocabulario que pueda ser mejorado permite a otros programadores usar el
API de formas que quizás no habías anticipado –¡de hecho, una gran
conveniencia para los usuarios del API!–. La próxima vez que estés
tentado a agrupar unas cuantas cosas en un método API, recuerda que el
idioma inglés no tiene una palabra para
MakeUpYourRoomBeQuietAndDoYourHomeWork
(LimpiaTuCuartoSeCalladoyHazTuTarea), a pesar de que parece muy
conveniente para una operación tan frecuentemente solicitada.

Autor: Gregor Hohpe