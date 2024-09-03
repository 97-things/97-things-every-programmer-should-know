# Scoping Methods

It has long been recommended that we should scope our variables as narrowly as possible. Why is that so?

* Readability is greatly improved if the scope of a named variable is so small that you can see its declaration only a few lines above its usage.
* Variables leaving scope are quickly reclaimed from the stack or collected by the garbage collector.
* Invalid reuse of locally scoped variables is impossible.
* Singular assignment on declaration encourages a functional style and reduces the mental overhead of keeping track of multiple assignments in different contexts
* Local variables are not shared state and are therefore automatically thread safe.

But what about scoping our methods?

We try to decompose methods into smaller units of computation, each of which is easily understandable. This goes hand in hand with the principle that a method should deal only with a _single level of abstraction_. If the result, however, is that your class then houses too many small methods to be easily understandable, it's time to rescope its methods. Although similar in some ways, that's not quite the same as decomposing classes with low cohesion into different smaller classes. The class may be quite cohesive, it's just that is spans too many levels of abstraction.

Although there are layout rules that make locality and access more significant (like putting a private method just below the first method that uses it), scoping is a cleaner way of separating cohesive parts of a class.

How do you scope methods?

Create objects that correspond to the public methods, and move the related private methods over to the method objects. If you had parameter lists for the private methods — especially long ones — you can promote these some of these parameters to instance variables of the method object.

You then have your original class declare its dependencies on these fragments and orchestrate their invocation. This keeps your original class in a coordinating role, freed from the detail of private methods. The lifetime of your method objects depends on their intended use. Mostly I create them within the scope just before being called and let them die immediately after. You may also choose to give them more significant status and have them passed in from outside the object or created by a factory.

These method objects give the newly created method scope a name and a location. They stay very narrowly focused and at a consistent level of abstraction. Often they become home for more functionality working on the state they took with them, e.g., the promoted parameters or the instance variables used by just these methods.

If you have private methods that are often reused within different other methods it's perhaps time to accept their importance and promote them to public methods in a separate method object.

By [Michael Hunger](http://programmer.97things.oreilly.com/wiki/index.php/Michael_Hunger)
