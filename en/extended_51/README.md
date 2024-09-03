# Simple Is not Simplistic

> "Very often, people confuse simple with simplistic. The nuance is lost on most." - Clement Mok

From the _New Oxford Dictionary Of English_:

* **simple** easily understood or done; presenting no difficulty
* **simplistic** treating complex issues and problems as if they were much simpler than they really are

In principle we all appreciate that simple software is more maintainable, has fewer bugs, has a longer lifetime, etc. We like to think that we always try to implement the most appropriate solutions, aspiring to this condition of simplicity. In practice, however, we also know that many developers often end up with unmaintainable code very quickly.

In my experience, the most common reason for that is due to lack of understanding of what the real problem than needs to be solved is. In fact, before implementing a new piece of functionality, there are several equally important things to do:

1. Understand the requirements: Is what the users are asking for what they _really_ need?
2. Think about how to fit the functionality into the system _cleanly_: What parts of the current system, if any, need to change to best accommodate it?
3. Think about what and how to test: How can I demonstrate that the functionality is implemented correctly? How can I make it so that the tests are simple to write and simple to run?
4. Given all the above, think about the time necessary to implement it: Time is always a major concern in software projects.

Unfortunately, when working on a "simple" solution, many developers do the following: gloss over point (1), assuming that the users actually know what they need; consider point (2), but forgetting the part about _cleanly_; skip point (3) altogether; finally, reduce the time at point (4) as much as possible by cutting corners. Far from being simple, that is actually a simplistic solution.

The net result is an increase in a system's internal complexity when this short-cut approach is used repeatedly to implement and add to the system's functionality. The maintainability and extensibility are affected negatively. Defects, however, are affected positively. And users will most likely be unhappy because the functionality is unlikely to match their expectations or their needs.

Doing the right thing - i.e., attending to all the above points considerately - in the short term requires more immediate work, and feels harder and more time consuming. In the medium to long term, however, the system will be easier and less expensive to maintain and evolve. The users (and the developers) will also be much happier.

Of course, there may be times when a solution is required very quickly and a clean implementation in a short time is impossible. However, hacking a solution should be a deliberate choice. The costs — the impact of the accumulated technical debt — have to be weighed carefully against any gains.

As Edward De Bono wrote, "simplicity before understanding is simplistic; simplicity after understanding is simple."

By [Giovanni Asproni](http://programmer.97things.oreilly.com/wiki/index.php/Giovanni_Asproni)
