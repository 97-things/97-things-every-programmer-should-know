# The Three Laws of Test-Driven Development

The jury is in. The controversy is over. The debate has ended. The conclusion is: _TDD works_. Sorry.

Test-Driven Development (TDD) is a programming discipline whereby programmers drive the design and implementation of their code by using unit tests. There are three simple laws:

1. You can't write any production code until you have first written a failing unit test.
2. You can't write more of a unit test than is sufficient to fail, and not compiling is failing.
3. You can't write more production code than is sufficient to pass the currently failing unit test.

If you follow these three laws you will be locked into a cycle that is, perhaps, 30 seconds long.

Experienced programmers' first impression of these laws is that they are just _stupid_. But if we follow these laws, we soon discover that there are a number of benefits:

* **Debugging.** What would programming be like if you were never more than a few minutes away from running everything and seeing it work? Imagine working on a project where you _never_ have several modules torn to shreds hoping you can get them all put back together next Tuesday. Imagine your debug time shrinking to the extent that you lose the muscle memory for your debugging hot keys.

* **Courage.** Have you ever seen code in a module that was so ugly that your first reaction was "Wow, I should clean this." Of course your next reaction was: "I'm not touching it!" Why? Because you were _afraid_ you'd break it. How much code could be cleaned if we could conquer our fear of breaking it? If you have a suite of tests that you trust, then you are not afraid to make changes. _You are not afraid to make changes!_ You see a messy function, you clean it. All the tests pass! The tests give you the courage to clean the code! Nothing makes a system more flexible than a suite of tests — nothing. If you have a beautiful design and architecture, but have no tests, you are still afraid to change the code. But if you have a suite of high-coverage tests then, even if your design and architecture are terrible, you are not afraid to clean up the design and architecture.

* **Documentation.** Have you ever integrated a third party package? They send you a nice manual written by a tech writer. At the back of that manual is an ugly section where all the code examples are shown. Where's the first place you go? You go to the code examples. You go to the code examples because that's where the _truth_ is. Unit tests are just like those code examples. If you want to know how to call a method, there are tests that call that method every way it can be called. These tests are small, focused _documents_ that describe how to use the production code. They are _design documents_ that are written in a language that the programmers understand; are unambiguous; are so formal that they _execute_; and cannot get out of sync with the production code.

* **Design.** If you follow the three laws every module will be _testable_ by definition. And another word for _testable_ is _decoupled_. In order to write your tests first, you have to decouple the units you are testing from the rest of the system. There's simply no other way to do it. This means your designs are more flexible, more maintainable, and just cleaner.

* **Professionalism.** Given that these benefits are real, the bottom line is that it would be _unprofessional_ not to adopt the practice that yields them.

By [Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)
