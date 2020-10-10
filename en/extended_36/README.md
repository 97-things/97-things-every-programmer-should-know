# Know Your Language

Syntax and semantics are important, but they're just a starting point. There is much more to know if you want to use a language effectively: How to write short, understandable code that works and is likely to continue working and be able to read, understand, and incorporate third-party code.

Know the idioms that are specific to the language you're working in. For example, in C++ you can make an object uncopyable by making the copy constructor and assignment operator private. Also know the common ways of implementing cross-language idioms — the patterns in _Design Patterns_ are a good start.

Know the history of the language. If your language was based on another language look at what changed. If your language has gone through multiple revisions look at what has changed (and why) between the revisions.

Know the future of the language. How is the language likely to change (or not)? Know which features are headed for deprecation and which features are likely to be added. Know how the language handles moving to a new, possibly incompatible version (e.g., Python 3.0). Know what the process is for changing the language (e.g., Python PEPs).

Know which features of the language have counterparts in other languages and which are unique to this language. Know which of the unique features are useful enough that they might make it into future languages.

Know what's wrong with the language. Read other people's critiques of the language; write your own critiques of the language. Understand why some of the flaws exist. Sometimes the reasons are historical. Sometimes the flaws are genuinely unavoidable or are the lesser of two evils. Sometimes the flaws are just mistakes. One interesting exercise is to take a flaw and work out how it could be corrected, and whether the knock-on effects would be worse than the flaw itself.

Know how you work around features that aren't in the language. For example, if the language does not have garbage collection, know what techniques are used to keep memory under control. Conversely, if the language does have garbage collection, learn the details of exactly how it works so that you're not surprised by odd performance and behavior.

Know the libraries that come with the language, and the common third-party libraries that are available (e.g., Boost and wxPython).

Know what happens when something goes wrong. Know what errors the compiler gives for common mistakes. Know what happens when there's an error at runtime, and what you can do about it.

Know what mistakes are particularly prevalent in the language. Try and avoid them yourself and be aware that they might crop up in code from other programmers.

Know what the definitive guides to your language are. Some authors are more reliable than others. Some compilers stick more closely to the language specification than others do. If there is an official standard for your language, make sure you have a copy of it and use it. The standard may appear to be written in a foreign tongue, but with practice it's quite possible to understand it.

Finally, although knowledge is important, it is a means, not the end. As Goethe said "Knowing is not enough; we must apply." Take that knowledge, and use it to produce great software.

By [Bob Archer](http://programmer.97things.oreilly.com/wiki/index.php/Bob_Archer)
