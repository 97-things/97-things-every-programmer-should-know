# Structure over Function

When learning to program, once you have mastered the syntax of the programming language, the function of a piece of code is the most important thing to get right. It feels great to pass the hurdle of getting a program to actually _run_ and do what you intended. Unfortunately, that initial satisfaction with your programming skills can be misleading. Programs that (seem to) work are necessary but not sufficient for your life as a good programmer.

So what is missing?

You and others will have to read, understand, use, and modify your program code. Changes to code are inevitable. You therefore need to ensure that your code can evolve while its functionality survives.

One of the most significant barriers to evolution is the code's structure. Significant structure exists at many levels: the number and order of statements in a function, loop and conditional blocks; the nesting within control structures; the functions within a module or class; the relationships between one piece of code and others; the partitioning and dependencies between classes, modules and subsystems — its overall design and architecture.

Hindrance to change from poor structure comes in many different species. The simplest taxonomy of code structure is in terms of high cohesion (i.e., the Single Responsibility Principle) and low coupling. Both are easy to measure and understand, and yet very hard to achieve. Violation of these principles is contagious, so without an antidote, code that depends on other, poorly structured code tends to degenerate as well. Take low cohesion and high coupling, or other metrics showing structural disorder, as symptoms to be diagnosed and remedied.

Refactoring is the treatment to improve code structure. Automated refactoring, test automation, and version control provide safety, so that treatment does no harm or can be easily undone.

While the need to refactor is almost inevitable — because we learn about better solutions while we program — there are also preventive measures that make refactoring less expensive and burdensome.

Where poor structure can occur at all levels, good structure builds from the ground up. Keep your program code clean and understandable from the statement level to the coarsest partitioning. Consider your code as _not_ "working" unless it is actually working in a way that you and other programmers can easily understand and evolve. A user might not initially recognize bad structure, so long as functionality is available. However, evolving the system might not happen at the pace the user expects or desires once structural decay in the code sets in.

Keep your code well organized. Program deliberately. Refactor mercilessly towards DRY code. Use patterns and simplicity to guide your efforts to improve the code's structure. Understand and evolve a system's architecture towards doing more with less code. Avoid too much up-front genericity and refactor away from laborious specific solutions repeating code.

As a professional programmer you will know that function is important, but you need to focus on structural improvement when programming, if your system is to grow beyond the scale of "Hello, World!"

By [Peter Sommerlad](http://programmer.97things.oreilly.com/wiki/index.php/Peter_Sommerlad)
