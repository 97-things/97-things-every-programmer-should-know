# Interfaces Should Reveal Intention

Kristen Nygaard, father of object-oriented programming and the Simula programming language, focused in his lectures on how to use objects to model the behavior of the real world and on how objects interacted to get a piece of work done. His favorite example was Cafe Objecta, where waiter objects served the appetites of hungry customer objects by allocating seating at table objects, providing menu objects, and receiving order objects.

In this type of model we will find a restaurant object with a public interface offering methods such as `reserveTable(numberOfSeats,customer,timePoint)` and `availableTables(numberOfSeats,timePoint)`, and waiter objects with methods such as `serveTable(table)` and `provideMenu(customer,table)` — object interfaces that reveal each object's intent and responsibility in terms of the domain at hand.

So, where are the _setters_ and _getters_ so often found dominating our object models? They are not here as they do not add value to the behavioral intention and expression of object responsibility.

Some might then argue that we need setters to support _dependency injection_ (a.k.a. _inversion of control_ design principle). Dependency injection has benefits as it reduces coupling and simplifies unit testing so that an object can be tested using a mock-up of a dependency. At the code level this means that for a restaurant object that contains table objects, code such as `Table table = new TableImpl(...);` can be replaced with `Table table;` and then initialized from the outside at runtime by calling `resturant.setTable(new TableImpl());`

The answer to that is that you do not necessarily need _setters_ for that. Either you use the constructor or, even better, create an interface in an appropriate package called something like `ExternalInjections` with methods prefixed with `initializeAttributeName(AttributeType)`. Again the intention of the interface has been made clear by being public and separate. An interface designed to support the use of a specific design principle or the intent of frameworks such as Spring.

So what about the _getters_? I think you are better off just referring to queried attributes by their name, using methods named `price`, `name`, and `timePoint`. Methods that are pure queries returning values are, by definition, functions and read better if they are direct: `item.price()` reads better than `item.getPrice()` because it make the concepts of the domain stand out clearly following the principles found in natural language.

The conclusion on this is that setters and getters are alien constructs that do not reveal the intention and responsibility of a behavior-centric interface. Therefore you should try to avoid using them; there are better alternatives.

By [Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre)
