# Methods Matter

A large part of today's software is written using object-oriented languages. Object-oriented software is composed of objects communicating via methods. So in a way it can be argued that not objects but methods are the basic building blocks of our code. While there is a lot of literature on design in the large — architecture and components — and on medium granularity — e.g., design patterns — surprisingly little can be found on designing individual methods. Design in the small, however, matters. A lot.

Ideally, any piece of source code should be readable like a good book: it should be interesting; it should convey its intention clearly; and last, but not least, it should be fun to read.

The simplest way to achieve readability is to use expressive names that properly describe the concepts they identify. In most cases this will mean relatively long names for methods and variables. Some argue that short names are easier and thus faster to type. Modern IDEs and editors are capable of simplifying the typing, renaming, and searching of names to make this objection less relevant. Instead of thinking about the typing overhead today, think about the time saved tomorrow when you and others have to reread the code. Be particularly careful when designing your method names because they are the verbs in the story you are trying to tell.

Keeping it simple (KISS) is a general rule of thumb in software design. One source of simplicity is brevity: Most of the time, shorter methods are simpler than long ones. While a low line count is a good starting point, the overall cognitive load can be further reduced by keeping the cyclomatic complexity low — ideally under 3 or 4, definitely under 10. Cyclomatic complexity is a numeric value that can easily be computed by many tools and is roughly equivalent to the number of execution paths through a method. A high cyclomatic complexity complicates unit testing and has been empirically shown to correlate with bugs.

Mixing concerns is often considered harmful. This is normally applied to classes as a whole, but applied at the method level it can further increase the readability of your code. Applied to methods this means that you should strive to map different aspects of your required behavior cleanly to different methods. Such a separation of technical and business concerns facilitates, and benefits from, the use of a well-defined domain vocabulary. Using such a vocabulary helps to reveal intention in your methods. This can ensure that a consistent and ubiquitous vocabulary is used when speaking to domain experts, but it also ensures that methods are focused and consistent, so that developers also benefit.

When you have properly separated concerns try to do the same with levels of abstraction. This is achieved by staying at a single level of abstraction within each method. This way you don't jump back and forth between little technical details and the grander motives of your code narrative. The resulting methods will be easier to grasp and more pleasant to read.

All in all, careful design of short methods with low complexity that focus on a single fine-grained concern and stay at a single level of abstraction combined with proper expressive naming will definitely help to better convey the intention of your code to other developers — and to yourself. This will improve maintainability in the long run and, after all, most software development is maintenance.

Happy method design!

By [Matthias Merdes](http://programmer.97things.oreilly.com/wiki/index.php/Matthias_Merdes)
