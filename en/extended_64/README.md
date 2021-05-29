# Using Design Patterns to Build Reusable Software

Design patterns are proven solutions to design problems within a given context. They help developers capture meaningful abstractions, add design flexibility, and encapsulate common behavior within their domain. Here are a few design patterns that are helpful in the context of building reusable assets:

* _Strategy_ — Polymorphically bind implementations to execute a particular algorithm. This is useful when encapsulating product variations, i.e., multiple flavors of a feature. For instance, searching a product catalog feature could use exact text matching for product A while using fuzzy matching for product B. This could also be used to support multiple flavors within the same product, choosing a concrete implementation based on runtime criteria, such as type of user or the nature of input parameter or volume of potential results.

* _Adapter_ — Used for translating one interface into another to integrate incompatible interfaces. Introduce an adapter when reusing a legacy asset. It is also useful when there are multiple versions of a reusable asset that you need to support in production. A single implementation can be reused to support both the new and the old version. An adapter can be used for supporting backward compatibility.

* _Content-Based Router_ — Used for routing messages that are being sent via a reliable messaging channel. The router can parse a portion of the message and invoke appropriate message handlers using metadata contained in the original message. Content-based routers can facilitate reuse of message handlers across transports (such as JMS and HTTP). They can also invoke rules depending on message characteristics.

* _Abstract Factory_ — Used to create coherent families of objects. You also don't want your calling code to know the nuances and complexity of constructing domain objects. This pattern is very useful when creating domain objects that require business rules. You want the complex creation in a single place in your codebase. I typically use this pattern when supporting bundling of product features. If you want to reuse a set of product features across bundles you will have several objects that all need to be carefully chosen at runtime for consistent behavior.

* _Decorator_ — Used with a core capability that you want to augment at runtime. Decorators are pluggable components that can be attached or detached at runtime. The upside is that the decorators and the component being decorated are both reusable, but you need to watch out for object proliferation. I use this pattern when the same data needs to be formatted or rendered differently or when I have a generic set of data fields that needs to be filtered based on some criteria.

* _Command_ — Used to encapsulate information that is used to call a piece of code repeatedly. Can also be used to support undo/redo functionality. The commands can be reusable across different product interfaces and act as entry points to invoke backend logic. For instance, I have used this pattern to support invocation of services from a self-service portal and interactive voice response channels.

These are just a few examples of patterns that help with reuse. When you get a problem, pause and reflect to see if a pattern is applicable.

By [Vijay Narayanan](http://programmer.97things.oreilly.com/wiki/index.php/Vijay_Narayanan)
