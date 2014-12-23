# The Single Responsibility Principle

One of the most foundational principles of good design is:

> Gather together those things that change for the same reason, and separate those things that change for different reasons.

This principle is often known as the *Single Responsibility Principle* or SRP. In short, it says that a subsystem, module, class, or even a function, should not have more than one reason to change. The classic example is a class that has methods that deal with business rules, reports, and database:

```
public class Employee {
  public Money calculatePay() ...
  public String reportHours() ...
  public void save() ...
}
```

Some programmers might think that putting these three functions together in the same class is perfectly appropriate. After all, classes are supposed to be collections of functions that operate on common variables. However, the problem is that the three functions change for entirely different reasons. The `calculatePay` function will change whenever the business rules for calculating pay change. The `reportHours` function will change whenever someone wants a different format for the report. The save function will change whenever the DBAs change the database schema. These three reasons to change combine to make `Employee` very volatile. It will change for any of those reasons. More importantly, any classes that depend upon `Employee` will be affected by those changes.

Good system design means that we separate the system into components that can be independently deployed. Independent deployment means that if we change one component we do not have to redeploy any of the others. However, if `Employee` is heavily used by many other classes in other components, then every change to Employee is likely to cause the other components to be redeployed; thus negating a major benefit of component design (or SOA if you prefer the more trendy name).

```
public class Employee {
  public Money calculatePay() ...
}

public class EmployeeReporter {
  public String reportHours(Employee e) ...
}

public class EmployeeRepository {
  public void save(Employee e) ...
}
```

The simple partitioning shown above resolves the issues. Each of these classes can be placed in a component of its own. Or rather, all the reporting classes can go into the reporting component. All the database related classes can go into the repository component. And all the business rules can go into the business rule component.

The astute reader will see that there are still dependencies in the above solution. That `Employee` is still depended upon by the other classes. So if `Employee` is modified, the other classes will likely have to be recompiled and redeployed. Thus, `Employee` cannot be modified and then independently deployed. However, the other classes can be modified and independently deployed. No modification of one of them can force any of the others to be recompiled or redeployed. Even `Employee` could be independently deployed through a careful use of the *Dependency Inversion Principle* (DIP), but that's a topic for a [different book](http://www.amazon.com/dp/0135974445/).

Careful application of the SRP, separating things that change for different reasons, is one if the keys to creating designs that have an independently deployable component structure.

by [Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)