# Use Aggregate Objects to Reduce Coupling

Despite that fact that architects and developers know that tight coupling leads to increased complexity, we experience large object models growing out of control on an almost daily basis. In practice, this leads to performance problems and lack of transactional integrity. There are many reasons why this happens: the inherent complexity of the real world, which has few clear boundaries; insufficient programming language support for dynamic multi-object grouping; and weak design practices.

To illustrate the problem, consider a simple order management system built from three object classes: `Order`, `OrderLine`, and `Item`. The object model can be traversed as `order.orderLine.item`. Assume now that the item price must be updated. What should happen to confirmed and delivered orders? Should their price also be changed? In most cases, certainly not. To secure that rule, the item price at the time of purchase can be copied into `orderLine` together with the quantity. Another example is to think about what happens when an order is canceled, and its corresponding object deleted. Should attached `orderLines` be deleted? Most likely, yes. Should the referenced items be deleted as part of an order? Most likely not.

Dealing with this type of problem at large leads us to a set of design heuristics first published by Eric Evans in his book [Domain-Driven Design](http://domaindrivendesign.org/books/index.html) under the heading _aggregates_. An aggregate is a set of objects defined to belong together and, therefore, should be handled as one unit when it comes to updates. The pattern also defines how an object model is allowed to be connected, with the following three rules considered to be the most important:

1. External objects are only allowed to hold references to the _aggregate root_.
2. Aggregate members are only allowed to be accessed through the _root_.
3. Member objects exist only in context of the _root_.

Applying these rules on our simple order management system the following can be stated: `Order` is the _root_ entity of the order aggregate while `orderLine` is a member. `Item` is the _root_ of another aggregate. Deleting an order implies that all of its `orderLine`s are deleted within the same transaction. Items are not affected by changes to orders. Orders are not affected by changes to items.

Identifying aggregates can be a difficult design task, with refactoring and domain expertise a must. On the other hand, the aggregate pattern is a powerful tool to reduce coupling, taking out enemy number one in our struggle for good design.

By [Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre)
