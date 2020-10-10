# Code Is Hard to Read

Each programmer has an idea in their head regarding _hard to read_ and _easy to read_. Readability depends on many factors:

* **Implementation language**. Some syntax just _is_ easier to read than others. XSLT anyone?
* **Code layout and formatting**. Personal preferences and pet hates, like "Where do I place the curly brace?" and indentation.
* **Naming conventions**. `userStatus` versus `_userstatus` versus `x`.
* **Viewer**. Choice of IDE, editor, or other tool used will contribute to readability.

The short message is that code is hard to read! The amount of math and abstract thinking required to read through even the most elegant of programs is taken for granted by many programmers. This is why there are reams of good advice and tools available to help us produce readable code. The points above should be very easy for any professional programmer to handle, but I left out the fifth point, which is:

* **Solution design**. The most common problem — "I see what's happening here... but it could be done better."

This addresses the "art" in programming. The mind thinks a certain way and some solutions will just sit better than others. Not because of any technical or optimization reason, it will just "read better." As a programmer you should strive to produce a solution that addresses all five of these points.

A good piece of advice is to have someone else glance at your solution, or to come back to it a day later and see if you "get it" first time. This advice is common but very powerful. If you find yourself wondering "What does that method/variable do again?", refactor! Another good litmus test is to have a developer working in a different language read your code. It's a great test of quality to read some code implemented in a different language to the one you're currently using and see if you "get it" straight away. Most scripting languages excel at this. If you are working on Java you can glance at well-written Ruby/bash/DSL and pick it up immediately.

As a rule of thumb, programmers must consider these five factors when coding. _Implementation language_ and _Solution design_ are the most challenging. You have to find the right language for the job — no one language is the golden hammer. Sometimes creating your own Domain-Specific Language (DSL) can vastly improve a solution. There are many factors for _Solution design_, but many good concepts and principles have been around for many years in computer science, regardless of language.

All code is hard to read. You must be professional and take the time to ensure your solution has flow and reads as well as you can make it. So do the research and find evidence to back up your assumptions, unit test by method, and question dependencies — a simple, readable implementation is head and shoulders above a clever-but-confusing, look-at-me implementation.

By [Dave Anderson](http://programmer.97things.oreilly.com/wiki/index.php/Dave_Anderson)
