# Missing Opportunities for Polymorphism

Polymorphism is one of the grand ideas that is fundamental to OO. The word, taken from Greek, means many (*poly*) forms (*morph*). In the context of programming polymorphism refers to many forms of a particular class of objects or method. But polymorphism isn't simply about alternate implementations. Used carefully, polymorphism creates tiny localized execution contexts that let us work without the need for verbose *if-then-else* blocks. Being in a context allows us to do the right thing directly, whereas being outside of that context forces us to reconstruct it so that we can then do the right thing. With careful use of alternate implementations, we can capture context that can help us produce less code that is more readable. This is best demonstrated with some code, such as the following (unrealistically) simple shopping cart:

```
public class ShoppingCart {
    private ArrayList<Item> cart = new ArrayList<Item>();
    public void add(Item item) { cart.add(item); }
    public Item takeNext() { return cart.remove(0);  }
    public boolean isEmpty() { return cart.isEmpty(); }
}
```

Let's say our webshop offers items that can be downloaded and items that need to be shipped. Let's build another object that supports these operations:

```
public class Shipping {
    public boolean ship(Item item, SurfaceAddress address) { ... }
    public boolean ship(Item item, EMailAddress address { ... }
}
```

When a client has completed checkout we need to ship the goods:

```
while (!cart.isEmpty()) {
    shipping.ship(cart.takeNext(), ???);
}
```

The *???* parameter isn't some new fancy elvis operator, it's asking should I email or snail-mail the item? The context needed to answer this question no longer exists. We have could captured the method of shipment in a boolean or enum and then use an *if-then-else* to fill in the missing parameter. Another solution would be create two classes that both extend Item. Let's call these DownloadableItem and SurfaceItem. Now let's write some code. I'll promote Item to be an interface that supports a single method, ship. To ship the contents of the cart, we will call `item.ship(shipper)`. Classes `DownloadableItem` and `SurfaceItem` will both implement ship.

```
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
```

In this example we've delegated the responsibility of working with `Shipping` to each Item. Since each item knows hows it's best shipped, this arrangement allows us to get on with it without the need for an *if-then-else*. The code also demonstrates a use of two patterns that often play well together: Command and Double Dispatch. Effective use of these patterns relies on careful use of polymorphism. When that happens there will be a reduction in the number of *if-then-else* blocks in our code.

While there are cases where it's much more practical to use *if-then-else* instead of polymorphism, it is more often the case that a more polymorphic coding style will yield a smaller, more readable and less fragile code base. The number of missed opportunities is a simple count of the *if-then-else* statements in our code.

By [Kirk Pepperdine](http://programmer.97things.oreilly.com/wiki/index.php/Kirk_Pepperdine)