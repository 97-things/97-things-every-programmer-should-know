# Abstract Data Types

We can view the concept of _type_ in many ways. Perhaps the easiest is that type provides a guarantee of operations on data, so that the expression `42 + "life"` is meaningless. Be warned, though, that the safety net is not always 100% secure. From a compiler's perspective, a type also supplies important optimization clues, so that data can be best aligned in memory to reduce waste, and improve efficiency of machine instructions.

Types offer more than just safety nets and optimization clues. A type is also an abstraction. When you think about the concept of type in terms of abstraction, then think about the operations that are "allowable" for an object, which then constitute its abstract data type. Think about these two types:

```ruby
class Customer
  def totalAmountOwing ...
  def receivePayment ...
end

class Supplier
  def totalAmountOwing ...
  def makePayment ...
end
```

Remember that `class` is just a programming convenience to indicate an abstraction. Now consider when the following is executed.

```ruby
y = x.totalAmountOwing
```

`x` is just a variable that references some data, an object. What is the type of that object? We don't know if it is `Customer` or `Supplier` since both types allow the operation `totalAmountOwing`. Consider when the following is executed.

```ruby
y = x.totalAmountOwing
x.makePayment
```

Now, if successful, `x` definitely references an object of type `Supplier` since only the `Supplier` type supports operations of `totalAmountOwing` and `makePayment`. Viewing types as interoperable behaviors opens the door to polymorphism. If a type is about the valid set of operations for an object, then a program should not break if we substitute one object for another, so long as the substituted object is a subtype of the first object. In other words, honor the semantics of the behaviors and not just syntactical hierarchies. Abstract data types are organized around behaviors, not around the construction of the data.

The manner in which we determine the type influences our code. The interplay of language features and its compiler has led to static typing being misconstrued as a strictly compile-time exercise. Rather, think about static typing as the fixed constraints on the object imposed by the reference. It's an important distinction: The concrete type of the object can change while still conforming to the abstract data type.

We can also determine the type of an object dynamically, based on whether the object allows a particular operation or not. We can invoke the operation directly, so it is rejected at runtime if it is not supported, or the presence of the operation can be checked before with a query.

An abstraction and its set of allowable operations gives us modularity. This modularity gives us an opportunity to design with interfaces. As programmers, we can use these interfaces to reveal our intentions. When we design abstract data types to illustrate our intentions, then type becomes a natural form of documentation, that never goes stale. Understanding types helps us to write better code, so that others can understand our thinking at that point in time.

By [Aslam Khan](http://programmer.97things.oreilly.com/wiki/index.php/Aslam_Khan)
