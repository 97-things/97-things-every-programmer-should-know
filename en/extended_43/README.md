# Programmers Who Write Tests Get More Time to Program

I became a programmer so that I could spend time creating software by programming. I don't want to waste my time managing low-quality code.

Does your code work the first time you test it out? Mine certainly never does. So if I hand the code over to someone else, I'm sure to get a bug report back that will take up my valuable programming time. This much is obvious to most developers. However, it also means that I don't want to have to go thought a long manual test myself to verify my code.

The first thing I do when I'm starting on a programming task is ask myself: "How am I going to test that this actually works?" I know it has to be done, I know it will take up a lot of my time if I do a poor job of it, so I want to get it right.

A good way to start is by writing tests before you write the code. The tests will specify the required behavior of the code. If you write the tests with the question "How will I know when my task is complete?" the chances are that not only will your tests will be better for it, your design will also have improved.

I've come to codebases that were otherwise good, but that required me to write a lot of code to support my tests. In other words: The code was overly complex to use.

For example, a system that is built with an asynchronous chain of services connected via a message bus might require you to deploy your code before you can test it. I've redesigned such code in a couple of steps that progressively reduced the coupling, improved the cohesion, and simplified the testing of the code:

1. Allow the code to be run synchronously and in-process by a configuration change. The messaging infrastructure is no longer coupled to the business logic. The resulting design is both easier to follow and more flexible, in addition to being easier to test. However, testing still requires setting up a long chain of services.
2. Refactoring my services to calculate the result they send to the next service by using a transformation function makes the responsibilities of different parts of the code clearer. And I can test almost all the logic by just calling this transformation function and checking the return value.

When encountering a programming task, ask yourself: "How can I test this?" If the answer is "Not very easily" try to write a test anyway. The test will probably require a lot of setup and it may be hard to verify the results. These are design problems, not test problems. Use the information from the testing process to refactor your system to a better design.

May you achieve fewer bugs and spend all your days programming happily in a well-designed system!

By [Johannes Brodwall](http://programmer.97things.oreilly.com/wiki/index.php/Johannes_Brodwall)
