# Oportunidades perdidas del Polimorfismo

Original: Missing Opportunities for Polymorphism

El polimorfismo es una de las grandes ideas fundamentales de la
Orientación a Objetos (OO). La palabra, tomada del griego, significa
muchas (poli) formas (morfos). En el contexto de programación el
polimorfismo se refiere a las muchas formas de una clase particular de
objetos o métodos. Pero el polimorfismo no es simplemente sobre
implementaciones alternativas. Usado con cuidado, crea diminutos
contextos de ejecución que nos dejan trabajar sin la necesidad de
detallados bloques if-then-else. Estar en un contexto nos permite hacer
lo correcto directamente, mientras que estar fuera del contexto nos
obliga a reconstruirlo para entonces poder hacer lo correcto. Con el uso
cuidadoso de implementaciones alternadas podemos capturar el contexto
que nos ayude a producir menos código que sea más leíble. Esto se
demuestra mejor con algo de código, como el siguiente (e irreal) carrito
de compras:


    public class ShoppingCart {
        private ArrayList<Item> cart = new ArrayList<Item>();
        public void add(Item item) { cart.add(item); }
        public Item takeNext() { return cart.remove(0);  }
        public boolean isEmpty() { return cart.isEmpty(); }
    }

Digamos que nuestra compra en línea ofrece elementos que pueden ser
descargados y elementos que necesitan ser enviados. Vamos a construir
otro objeto que soporte estas operaciones:

    public class Shipping {
        public boolean ship(Item item, SurfaceAddress address) { ... }
        public boolean ship(Item item, EMailAddress address { ... }
    }

Cuando un cliente ha completado la compra, necesitamos enviar los bienes:

    while (!cart.isEmpty()) {
        shipping.ship(cart.takeNext(), ???);
    }

El parámetro `???` no es algún nuevo operador _Elvis_, está preguntado
si debería enviar correo electrónico o correo normal. El contexto
necesario para responder la pregunta ya no existe. Pudimos haber
capturado el método de envío en un boleano o en un enum y entonces usar
un `if-then- else` para llenar el parámetro faltante. Otra solución
sería crear dos clases, en las cuales ambas extiendan `Item`. Llamémosle
`DownloableItem` y `SurfaceItem`.Ahora vamos a escribir algo de código.
Promoveré `Item` para que sea una interfaz que soporte un único método:
`ship`. Para enviar el contenido del carrito haremos una llamada a
`item.ship(shipper)`. Ambas clases `DownloadbleItem` y `SurfaceItem`
implementarán `ship`.

    public class DownloadableItem implements Item {
        public boolean ship(Shipping shipper) {
            shipper.ship(this, customer.getEmailAddress());
        }
    }

    public class SurfaceItem implements Item {
        public boolean ship(Shipping shipper) {
            shipper.ship(this, customer.getSurfaceAddress());
        }
    }

En este ejemplo hemos delegado la responsabilidad de trabajar con
`Shipping` en cada `Item`. Debido a que cada item sabe cómo es mejor que
sea enviado, este arreglo nos permite estar con él sin la necesidad de
un `if-then-else`. El código también demuestra un uso de dos patrones
que frecuentemente actúan juntos: [_Command_][1] y [_Double
Dispatch_][2]. El uso efectivo de estos patrones reside en un uso
cuidadoso del polimorfismo. Cuando esto suceda habrá una reducción del
número de bloques if-then-else en nuestro código.

Si bien hay casos en los que es mucho más práctico utilizar `if-then-
else` en vez del polimorfismo, es más frecuente el caso en el cual un
estilo de código más polimórfico dará lugar a un código base más
pequeño, más fácil de leer y menos frágil. El número de oportunidades
perdidas es un simple conteo de declaraciones `if-then-else` en nuestro
código.


[1]: https://en.wikipedia.org/wiki/Command_pattern
[2]: https://en.wikipedia.org/wiki/Double_dispatch

Autor: Kirk Pepperdine