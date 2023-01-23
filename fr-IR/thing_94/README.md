# Write Small Functions Using Examples

We would like to write code that is correct, and have evidence on hand that it is correct. It can help with both issues to think about the "size" of a function. Not in the sense of the amount of code that implements a function — although that is interesting — but rather the size of the mathematical function that our code manifests.

For example, in the game of Go there is a condition called *atari* in which a player's stones may be captured by their opponent: A stone with two or more free spaces adjacent to it (called *liberties*) is not in atari. It can be tricky to count how many liberties a stone has, but determining atari is easy if that is known. We might begin by writing a function like this:

```
boolean atari(int libertyCount)
    libertyCount < 2
```

This is larger than it looks. A mathematical function can be understood as a set, some subset of the Cartesian product of the sets that are its domain (here, `int`) and range (here, `boolean`). If those sets of values were the same size as in Java then there would be `2L*(Integer.MAX_VALUE+(-1L*Integer.MIN_VALUE)+1L)` or 8,589,934,592 members in the set `int×boolean`. Half of these are members of the subset that is our function, so to provide complete evidence that our function is correct we would need to check around 4.3×10<sup>9</sup> examples.

This is the essence of the claim that tests cannot prove the absence of bugs. Tests can demonstrate the presence of features, though. But still we have this issue of size.

The problem domain helps us out. The nature of Go means that number of liberties of a stone is not any int, but exactly one of {1,2,3,4}. So we could alternatively write:

```
LibertyCount = {1,2,3,4} 
boolean atari(LibertyCount libertyCount)
    libertyCount == 1
```

This is much more tractable: The function computed is now a set with at most eight members. In fact, four checked examples would constitute evidence of complete certainty that the function is correct. This is one reason why it's a good idea to use types closely related to the problem domain to write programs, rather than native types. Using domain–inspired types can often make our functions much smaller. One way to find out what those types should be is to find the examples to check in problem domain terms, before writing the function.

by [Keith Braithwaite](http://programmer.97things.oreilly.com/wiki/index.php/Keith_Braithwaite)