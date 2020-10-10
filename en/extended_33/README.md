# Isolate to Eliminate

Whether you're looking at your own code before (or after!) you have shipped it, or you're picking up someone else's code after they have shipped it, tracking down and fixing bugs is a fundamental part of programming. If you know the code well, perhaps you can make an intuitive leap to jump immediately to where the bug is. But how do you go about tracking down a bug when intuition doesn't help?

The nature of all code is that larger systems are built from smaller underlying systems and components. They in turn are also built from smaller systems and components. The bug you are tracking down will have a cause in one of these, and will have symptoms that are visible in other systems. The remaining systems work fine, as far as the bug you're looking for is concerned, so you can use this knowledge to quickly and reliably find where the bug is.

Divide your larger systems down into smaller systems at logical points, such as different server stacks, APIs, major interfaces, classes, methods, and, if necessary, individual lines of code. Test both sides of the divide, with your tests focusing on the data that crosses the divide. If one side works as expected, the bug is not in there. You can eliminate that side from further testing. Continue testing the remaining systems and components, which you have now isolated, by dividing those into smaller systems and components. Keep going until you've reached the smallest testable system, component, unit, or fragment of code that exhibits the bug. Congratulations: You have isolated the fault.

Apart from being a strategy that allows you to work on code you've never seen before, this approach also has the advantage that it is evidence-based. It approach eliminates guesswork and forces developers' assumptions about how their code actually works to be challenged. The data never lies, but be aware that it can be misinterpreted!

The approach is inherently iterative. You'll often go back and forth between your code and your tests, making your code easier to test and your tests clearer, with more targeted test domains and results. Fix the tests that are relevant to the bug you are tracking down, but make a list of any other issues you find along the way so you can come back and address them at a later date. Stay on target, and park potential tangents and distractions for another time.

Being able to debug code is the single most important skill any programmer needs to master. Despite all the headlines you'll read on the Internet of programmers making it big, they are a tiny minority. Most programmers will spend the majority of their careers maintaining code that they have inherited from someone else. That's the reality of being a professional programmer, and strategies for taking code apart and solving problems in it will be the tools that you use the most.

By [Stuart Herbert](http://programmer.97things.oreilly.com/wiki/index.php/Stuart_Herbert)
