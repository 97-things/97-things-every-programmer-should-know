# Codifica en el lenguaje del dominio

Original: Code in the Language of the Domain

Imagínate dos códigos bases. En uno te encuentras esto:

    if (portfolioIdsByTraderId.get(trader.getId())
      .containsKey(portfolio.getId())) {...}

Te rascas la cabeza imaginándote para que podría servir este código.
Parece que está obteniendo un ID desde un objeto comerciante (“trader”),
usándolo para obtener aparentemente un mapa de mapas y, entonces, está
viendo si otro ID desde un objeto portafolio (“portfolio”) existe en el
mapa interior. Te rascas la cabeza un poco más. Ves la declaración del
método `portfolioIdsByTraderId` y descubres esto:

    Map<int, Map<int, int>> portfolioIdsByTraderId;

Poco a poco te das cuenta que podría tener algo que ver con que un
comerciante tenga acceso a un portafolio en particular. Y, por supuesto,
encontrarás el mismo fragmento de búsqueda –o un similar-pero-
ligeramente-diferente fragmento de código– en el momento en que a
alguien le importa si un comerciante tiene acceso a un portafolio en
particular.

En el otro código base te encuentras con esto:

    if (trader.canView(portfolio)) {...}

No hay rascado de cabeza. No necesitas saber cómo lo sabe un
comerciante. Quizás es uno de esos mapas de mapas escondidos dentro.
Pero es un asunto del comerciante, no tuyo.

Ahora, ¿en cuál de estos códigos te gustaría estar trabajando?

Hubo un tiempo en que sólo teníamos unas muy básicas estructuras de
datos: bit, bytes y caracteres (realmente sólo bytes que pretendíamos
que fueran letras y puntuaciones). Tener decimales eran un poco
truculento porque nuestros números de base 10 no trabajan muy bien en
binario, así que teníamos varios tamaños de tipos de punto flotante.
Entonces vinieron las matrices y las cadenas (realmente sólo matrices
distintas). Teníamos pilas, colas, hashes, listas ligadas y listas
salteadas y muchas otras excitantes estructuras de datos que no existían
en el mundo real. La “Ciencia Computacional” se trataba de gastar mucho
esfuerzo mapeando el mundo real en nuestras estructuras de datos
restrictivas. Los verdaderos gurús podrían incluso recordar cómo lo
habían logrado.

¡Entonces tuvimos los tipos definidos por el usuario! Está bien, esto no
es noticia, pero fue un cambio en el juego, de alguna manera. Si tu
dominio contiene conceptos como negociantes y portafolios, podías
modelarlos con tipos llamados, digamos, Comerciantes y Portafolio. Pero,
más importante que esto, también puedes modelar relaciones entre ellos
usando términos de dominio.

Si no codificas usando términos del dominio estás creando un
entendimiento tácito (léase: secreto) de que este valor de tipo entero
que está por ahí significa la manera de identificar a un comerciante,
donde ese valor de tipo entero por allá es la manera de identificar un
portafolio. (¡Mejor no confundirlos!) Y si representas un concepto de
negocio (“a algunos comerciantes no les está permitido ver algunos
portafolios –es ilegal–”) con un algoritmo, digamos la existencia de
relaciones en un mapa de claves, no le estás haciendo ningún favor a los
chicos de auditoría y quejas.

El programador de junto quizás no sepa el secreto, así que ¿porqué no
hacerlo explícito? Usar una llave como el término de búsqueda de otra
llave que realiza la revisión de una llave existente no es terriblemente
obvio. ¿Cómo se supone que alguien intuya que ahí están implementadas
las reglas de negocio que previenen conflictos de interés?

Realizar conceptos explícitos del dominio en tu código significa que
otros programadores pueden adquirir la intención del código mucho más
fácilmente que intentar meter un algoritmo en lo que entienden sobre el
dominio. Esto también significa que cuando el modelo del dominio
evoluciona –es decir, que tu entendimiento se incrementa– estés en una
buena posición para evolucionar el código. En conjunto con una buena
encapsulación, aumenta la oportunidad de que la regla exista sólo en un
lugar y que puedes cambiarla sin que el código dependiente se dé cuenta.

El programador que venga unos cuantos meses después a trabajar con el
código te lo agradecerá y quizás ese programador seas tú.

Autor: Dan North