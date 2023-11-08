# Consider the Hardware

It's a common opinion that slow software just needs faster hardware. This line of thinking is not necessarily wrong but, like misusing antibiotics, it can become a big problem over time. Most developers don't have any idea what is really going on "under the hood." There is often a direct conflict of interest between best programming practices and writing code that screams on the given hardware.

First, let's look at your CPU's prefetch cache as an example. Most prefetch caches work by constantly evaluating code that hasn't even executed yet. They help performance by "guessing" where your code will branch to before it even has happened. When the cache "guesses" correctly, it's amazingly fast. If it "guesses" wrong, on the other hand, all the preprocessing on this "wrong branch" is useless and a time-consuming cache invalidation occurs. Fortunately, it's easy to start making the prefetch cache work harder for you. If you code your branch logic so that the _most frequent result_ is the condition that is tested for, you will help your CPU's prefetch cache be "correct" more often, leading to fewer CPU-expensive cache invalidations. This sometimes may read a little awkwardly, but systematically applying this technique over time will decrease your code's execution time.

Now, let's look at some of the conflicts between writing code for hardware and writing software using mainstream best practices.

Folks prefer to write many small functions in favor of larger ones to ease maintainability, but all those function calls come at a price! If you use this paradigm, your software may spend more time preparing and recovering from work than actually doing it! The much loathed `goto` or `jmp` command is the fastest method to get around followed closely by machine language indirect addressing jump tables. Functions are great for humans but from the CPU's point of view they're expensive.

What about inline functions? Don't inline functions trade program size for efficiency by copying function code inline versus jumping around? Yes they do! But even when you specify a function is to be inlined, can you be sure it was? Did you know some compilers turn regular functions into inline ones when they feel like it and vice versa? Understanding the machine code created by your compiler from your source code is extremely important if you wish to write code that will perform optimally for the platform at hand.

Many developers think abstracting code to the nth degree, and using inheritance, is just the pinnacle of great software design. Sometimes constructs that look great conceptually are terribly inefficient in practice. Take for example inherited virtual functions: They are pretty slick but, depending on the actual implementation, they can be very costly in CPU clock cycles.

What hardware are you developing for? What does your compiler do to your code as it turns it to machine code? Are you using a virtual machine? You'll rarely find a single programming methodology that will work perfectly on all hardware platforms, real or virtual.

Computer systems are getting faster, smaller and cheaper all the time, but this does not warrant writing software without regards to performance and storage. Efforts to save clock CPU cycles and storage can pay off as dividends in performance and efficiency.

Here's something else to ponder: New technologies are coming out all the time to make computers more _green_ and ecosystem friendly. Efficient software may soon be measured in power consumption and may actually affect the environment!

Video game and embedded system developers know the hardware ramifications of their compiled code. Do you?

By [Jason P Sage](http://programmer.97things.oreilly.com/wiki/index.php/Jason_P_Sage)
