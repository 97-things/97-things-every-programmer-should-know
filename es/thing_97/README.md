# El WET dispersa los cuellos de botella en el rendimiento

Original: WET Dilutes Performance Bottlenecks

La importancia del principio DRY ([No te repitas][1]) es que codifica la
idea de que cada pieza del conocimiento en un sistema debería tener una
representación única. En otras palabras, el conocimiento debería estar
contenido en una implementación única. La antítesis de DRY es WET (Write
Every Time, escríbelo todas las veces). Nuestro código es WET cuando el
conocimiento es codificado en varias distintas implementaciones. Las
implicaciones de rendimiento de DRY versus WET quedan claras cuando
consideras los numerosos efectos en un perfil de rendimiento.

Comenzamos considerando una característica en nuestro sistema, digamos
X, que es un cuello de botella de CPU. Digamos que la característica X
consume el 30% del CPU. Ahora digamos que la característica X tiene diez
diferentes implementaciones. En promedio, cada implementación consume 3%
del CPU. En este nivel de uso de CPU no es útil preocuparse si estamos
buscando una victoria rápida, es común que olvidemos que esta
característica es nuestro cuello de botella. Sin embargo, digamos que,
de alguna manera, reconocimos la característica X como un cuello de
botella. Ahora estamos con el problema de encontrar un arreglo en cada
implementación. Con WET tenemos diez diferentes implementaciones que
necesitamos buscar y reparar. Con DRY veríamos claramente el 30% de uso
de CPU y tendríamos una décima parte de código que arreglar. ¿Mencioné
que no tenemos tiempo que perder buscando cada implementación?

Hay un caso de uso en el cual frecuentemente nos sentimos culpables de
violar el principio DRY: nuestro uso de colecciones. Una técnica común
de implementar una consulta sería el iterar sobre una colección y
entonces aplicar la consulta para cada elemento:

    public class UsageExample {
        private ArrayList<Customer> allCustomers = new ArrayList<Customer>();
        // ...
        public ArrayList<Customer> findCustomersThatSpendAtLeast(Money amount) {
            ArrayList<Customer> customersOfInterest = new ArrayList<Customer>();
            for (Customer customer: allCustomers) {
                if (customer.spendsAtLeast(amount))
                   customersOfInterest.add(customer);
            }
            return customersOfInterest;
        }
    }

Al exponer esta colección en bruto a los clientes, hemos violado la
encapsulación. Esto no sólo limita nuestra habilidad para refactorizar,
obliga a los usuarios de nuestro código a violar el principio DRY al
tener cada uno de ellos que reimplementar potencialmente la misma
consulta. Esta situación se puede evitar fácilmente al quitar la
colección en bruto del API. En este ejemplo podemos introducir un nuevo
tipo de colección de dominio específico llamado `CustomerList`. Esta
nueva clase es más semántica en la línea de nuestro dominio. Actuará
como una casa natural para todas nuestras consultas.

Tener esta nueva colección nos permitirá ver de forma sencilla si esta
consulta es un cuello de botella en el rendimiento. Al incorporar las
consultas en la clase eliminamos la necesidad de exponer las elecciones
de representación, tales como `Arraylist`, a nuestros clientes. Esto nos
da la libertad de alterar esta implementación sin el miedo de violar los
contratos de los clientes:

    public class CustomerList {
        private ArrayList<Customer> customers = new ArrayList<Customer>();
        private SortedList<Customer> customersSortedBySpendingLevel = new SortedList<Customer>();
        // ...
        public CustomerList findCustomersThatSpendAtLeast(Money amount) {
            return new CustomerList(customersSortedBySpendingLevel.elementsLargerThan(amount));
        }
    }

    public class UsageExample {
        public static void main(String[] args) {
            CustomerList customers = new CustomerList();
            // ...
            CustomerList customersOfInterest = customers.findCustomersThatSpendAtLeast(someMinimalAmount);
            // ...
        }
    }

En este ejemplo, la adherencia a DRY nos permite introducir un esquema
de índice alterno con `SortedList` usando una llave en el nivel de gasto
de nuestros clientes. Más importante que los detalles específicos de
este ejemplo, en particular, seguir el principio DRY nos ayuda a
encontrar y reparar cuellos de botella en el rendimiento que habrían
sido más difíciles de encontrar si el código fuera WET.


[1]: no-te-repitas.html

Autor: Kirk Pepperdine