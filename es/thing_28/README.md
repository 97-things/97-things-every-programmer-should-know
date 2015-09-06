# El diseño del código sí importa

Original: Code Layout Matters

Hace muchos años trabajaba en un sistema en Cobol, en el cual no se le
permitía al personal cambiar la sangría a menos que tuvieran una razón
para cambiar el código, debido a que alguien, alguna vez, descompuso
algo al dejar un trozo de línea en una de las columnas especiales al
inicio de una línea. Esto aplicaba incluso si el diseño estaba
equivocado, lo cual sucedía algunas veces, así que teníamos que leer el
código muy cuidadosamente porque no podíamos confiar en él. La política
debió costar una fortuna en fricción de programador.

Hay una investigación que muestra que todos pasamos más de nuestro
tiempo de programación navegando y leyendo código –encontrando dónde
hacer el cambio– que escribiendo, así que esto es lo que queremos
optimizar.

- Fácil de escanear. La gente es buena en la comparación de patrones
visuales (una reminiscencia de la época en la que teníamos que observar
leones en la sabana), así que puedo ayudarme al hacer todo lo que no es
directamente relevante al dominio, toda la “complejidad accidental” que
viene con muchos lenguajes comerciales, ocultarlo en el fondo de
pantalla para estandarizarlo. Si el código que se comporta igual luce
igual, entonces mi sistema perceptual me ayudará a escoger las
diferencias. Es por eso que también observo las convenciones sobre cómo
diseñar las partes de una clase dentro de una unidad de compilación:
constantes, campos, métodos públicos, métodos privados.
- Diseño expresivo. Todos hemos aprendido que toma su tiempo encontrar los
nombres adecuados para que nuestro código exprese, tan claramente como
es posible, lo que hace; en lugar de sólo listar los pasos, ¿está bien?
El diseño de código también es parte de esta expresividad. Un primer
corte es tener el acuerdo del equipo en un formateo automático para lo
básico, entonces podemos hacer ajustes manuales mientras estamos
codificando. A menos que haya un disensión activa, el equipo convergerá
rápidamente en un estilo de “acabado manual” común. Un formateador no
puede entender mis intenciones (debería saberlo, una vez codifiqué uno),
y es más importante para mí que los saltos de línea y los agrupadores
reflejen la intención de mi código, no sólo la sintaxis del lenguaje
(Ken McGuire me liberó de mi esclavitud a los formateadores automáticos
de código).
- Formato compacto. Mientras más puedo conseguir en una pantalla, más
puedo ver si se rompe el contexto al desplazarme o al cambiar de
archivo, lo que significa que puedo dejar menos estados en mi cabeza.
Los comentarios del procedimiento largos y los espacios en blanco tienen
sentido para nombres de 8 caracteres e impresoras, pero ahora vivo en un
IDE que hace el coloreo de sintaxis y el enlace cruzado. Los pixeles son
mi factor limitante, así que quiero que cada uno contribuya hacia mi
entendimiento del código. Quiero que el diseño me ayude a entender el
código, pero no más que eso.

Un amigo no programador comentó alguna vez que el código se parece a la
poesía. Tengo esa sensación en el código bueno, que todo en el texto
tiene un propósito y está ahí para ayudarme a entender la idea.
Desafortunadamente, escribir código no tiene la misma imagen romántica
que escribir poesía.

Autor: Steve Freeman