# Encapsula Comportamiento, no sólo Estado

Original: Encapsulate Behavior, not Just State

En la teoría de sistemas, el contenimiento es uno de los más útiles
constructos cuando se está tratando con sistemas de estructuras muy
grandes y complejas. En la industria de software el valor del
contenimiento o encapsulación es bien entendido.

Los módulos y paquetes resuelven las necesidades a gran escala de la
encapsulación, mientras que las clases, subrutinas y funciones resuelven
los aspectos más granulares en la materia. A través de los años he
descubierto que las clases parecen ser uno de los constructos de
encapsulación más difíciles que los desarrolladores entiendan. Es común
encontrar una clase con sólo un método principal con 3 mil líneas de
código, o una clase con sólo método `set` y `get` para sus atributos
primitivos. Estos ejemplos demuestran que el desarrollador involucrado
no ha entendido por completo el pensamiento orientado a objetos,
fallando en tomar ventaja del poder de los objetos como constructos de
modelaje. Para los desarrolladores familiarizados con los términos POJO
(*Plain Old Java Object*) y POCO (*Plain Old C# Object* o *Plain Old CLR
Object*), éste fue el intento para regresar a lo más básico de OO como
el paradigma modelo, los objetos son planos y sencillos, pero no tontos.

Un objeto encapsula ambos; estado y comportamiento, donde el
comportamiento es definido por el estado actual. Considera un objeto
puerta. Éste tiene 4 estados: cerrado, abierto, cerrando, abriendo.
Ofrece dos operaciones: abrir y cerrar. Dependiendo del estado, las
operaciones de abrir y cerrar se comportarán de forma diferente. Esta
propiedad inherente de un objeto hace que el proceso de diseño
conceptualmente simple. Esto se resume en dos tareas sencillas:
localización y delegación de responsabilidad a los diferentes objetos,
incluyendo los protocolos de la interacción entre objetos.

Cómo funciona en la práctica se ilustra mejor con un ejemplo. Digamos
que tienes tres clases: *Customer* (Cliente), *Order* (Orden) e *Item*.
El objeto *Customer* es marcador de posición natural para el límite de
crédito y las reglas de validación. Un objeto *Order* sabe sobre su
Customer asociado, y su operación `addItem` delega la validación del
crédito actual llamando al método
`Customer.validaCredito(item.precio())`. Si la poscondición del método
falla, una excepción puede ser enviada y la compra cancelada.

Los desarrolladores menos experimentados en orientación a objetos
podrían decidirse a envolver todas las reglas de negocio en un objeto
frecuentemente referido como *orderManager* u *OrderService*. En este
diseño, *Order*, *Customer* e *Item* son tratados como algo más que
tipos de registros. Toda la lógica es factorizada desde las clases y
unidas en un método largo y procedural con un montón de constructos
internos `if-the-else`. Estos métodos se rompen con facilidad y son casi
imposibles de mantener. ¿La razón? La encapsulación está rota.

Así que, al final, no rompas la encapsulación y usa el poder de tu
lenguaje de programación para mantenerla.

Autor: Einar Landre