# Expect the Unexpected

They say that some people see the glass half full, some see it half empty. But most programmers don't see the glass at all; they write code that simply does not consider unusual situations. They are neither optimists nor pessimists. They are not even realists. They're _ignore-ists_.

When writing your code don't consider only the thread of execution you expect to happen. At every step consider all of the _unusual_ things that might occur, no matter how _unlikely_ you think they'll be.

### Errors

Any function you call may not work as you expect.

* If you are lucky, it will return an error code to signal this. If so, you should check that value; never ignore it.

* The function might throw an exception if it cannot honor its contract. Ensure that your code will cope with an exception bubbling up through it. Whether you catch the exception and handle it, or allow it to pass further up the call stack, ensure your code is correct. Correctness includes not leaking resources or leaving the program in an invalid state.

* Or the function might return no indication of failure, but silently not do what you expected. You ask a function to print a message: Will it always print it? Might it sometimes fail and consume the message?

Always consider errors that you can recover from, and write recovery code. Consider also the errors that you cannot recover from. Write your code to do the best thing possible — don't just ignore it.

### Threading

The world has moved from single-threaded applications to more complex, often highly threaded, environments. Unusual interactions between pieces of code are staple here. It's hard to enumerate every possible interweaving of code paths, let alone reproduce one particular problematic interaction more than once.

To tame this level of unpredictability, make sure you understand basic concurrency principles, and how to decouple threads so they cannot interact in dangerous ways. Understand mechanisms to reliably and quickly pass messages between thread contexts without introducing race conditions or blocking the threads unnecessarily.

### Shutdown

We plan how to construct a system: How to create all the objects, how to get all the plates to spin, and how to keep those objects running and those plates spinning. Less attention is given to the other end of the lifecycle: How to bring the code to a graceful halt without leaking resources, locking up, or crashing.

Shutting down your system and destroying all the objects is especially hard in a multi-threaded system. As your application shuts down and destroys its worker objects, make sure you can't leave one object attempting to use another that has already been disposed of. Don't enqueue threaded callbacks that target objects already discarded by other threads.

### The Moral of the Story

The unexpected is not the unusual. You need to write your code in the light of this.

It's important to think about these issues early on in your code development. You can't tack this kind of correctness as an afterthought; the problems are insidious and run deeply into the grain of your code. Such demons are very hard to exorcise after the code has been fleshed out.

Writing good code is not about being an optimist or a pessimist. It's not about how much water is in the glass right now. It's about making a watertight glass so that there will be no spillages, no matter how much water the glass contains.

By [Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe)
