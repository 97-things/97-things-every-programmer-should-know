# Don't Use too Much Magic

In recent years _convention over configuration_ has been an emerging software design paradigm. By taking advantage of it, developers only need specify the non-common part of their application, because the tools that follow this approach provide meaningful behavior for all the aspects covered by the tool itself. These default behaviors often fit the most typical needs. The defaults can be replaced by custom implementations where something more specific is needed. Many modern frameworks, such as Ruby on Rails and Spring, Hibernate, and Maven in the Java world, use this approach in order to simplify developers' lives by decreasing both the number of decisions they need to take and the amount of configuration they need to set up.

Most of the tools that take this approach generally do so by simplifying the most common and frequent tasks in the fastest and easiest way possible, yet without losing too much flexibility. It seems almost like magic that you can do so much by writing so little. Under the hood these frameworks do lots of useful things, like populate your objects from an underlying database, bind their property values to your favorite presentation layer, or wire them together via dependency injection. Moreover, smart programmers tend to add their own magic to the that of those frameworks, increasing the number of conventions that need to be respected in order to keep things working.

In a nutshell, convention over configuration is easy to use and can allow savings of time and effort by letting you focus on the real problems of your business domain without being distracted by the technical details. But when you abuse it — or, even worse, when you don't have a clear idea of what happens under the hood — there is a chance that you lose control of your application because it becomes hard to find out at which point the tools you are using don't behave as expected, or even to say which configuration you are running since you didn't declare it anywhere. Then small changes in the code cause big effects in apparently unrelated parts of the application. Transactions get opened or closed unexpectedly. And so on.

This is the point where things start going wrong and programmers must call on their problem-solving skills. Using the fantastic features made available by a framework is straightforward for any average developer so long as the magic works, in the same way that a pilot can easily fly a large airplane in fine weather with the automatic pilot doing its job. But can the pilot handle that airplane in middle of a thunderstorm or when the wheels don't come out during the landing phase?

A good programmer is used to relying on the libraries he uses as much as a good pilot is used to rely on his automatic counterpart. But both of them know when it is time to give up their automatic tools and dirty their hands. An experienced developer is able to use the frameworks properly, but also to debug them when they don't behave as expected, to work around their defects, and to understand how they work and what their limits are. An even better developer knows when it is not the case to use them at all because they don't fit a particular need or they introduce an unaffordable inflexibility or loss of performance.

By [Mario Fusco](http://programmer.97things.oreilly.com/wiki/index.php/Mario_Fusco)