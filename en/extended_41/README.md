# The Programmer's New Clothes

The conversation goes like this:

> _Mortal Developer_: This design seems complicated. Can we change the whack-a-mole feature? It adds extra steps to every use of the system.
>
> _Expert Domain Programmer_: No, some users might need whack-a-mole to interact with their legacy bug tracking system.

Now our poor mortal developer is stuck. After all, this is the expert we're talking to here. If he says we need whack-a-mole, you better get whacking.

Our expert missed this: Complexity alone can be cause to reject a design. We need to start with an open mind, looking to understand how every aspect of a design pulls its weight. But you're a smart programmer; if a system is difficult for you to understand, it might be too complicated. Now you have to point out and address that complexity. Sadly, there sometimes seems to be an "Emperor's New Clothes" phenomenon in software. No one wants to admit something is hard to understand in an industry where intelligence is considered the greatest virtue.

From the other side, as we develop domain expertise we are prone to a trap. We live and breath the intricacies of the domain, becoming so fluent we can't see the challenges of a novice. It's like being a native speaker of a language: I don't think about the huge number of special rules in English, so a particular rule doesn't seem very onerous to me. But put them together and these rules present a huge obstacle to someone starting to learn it.

Yet there is hope. Unlike natural language, we can control the complexity of our designs. Imagine the biggest, most complicated specification you've seen. Imagine if the design team included a smart, experienced person without domain knowledge, but with veto power. Could we cut out much of the accidental complexity?

Some humble advice for anyone struggling with this right now:

* Remember Alan Kay's insight: "Simple things should be simple, complex things should be possible." If something complicated must be in the system, it still should not affect the simple things.

* View the project as a constant battle against complexity. A single complex module may seem unimportant, but it quickly compounds.

* Understand a project end-to-end. The project should be easily broken down into problems that are known to be solvable.

* A strong-willed engineer or executive can will a group down the wrong path. It's an engineer's duty to object and prevent spiraling complexity.

* Brian Kernighan said it well: "Everyone knows that debugging is twice as hard as writing a program in the first place. So if you're as clever as you can be when you write it, how will you ever debug it?"

All of this boils down to _Keep It Simple, Stupid_. It turns out keeping things simple can be pretty hard.

By [Ryan Brush](http://programmer.97things.oreilly.com/wiki/index.php/Ryan_Brush)
