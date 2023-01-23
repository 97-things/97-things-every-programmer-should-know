# Test Precisely and Concretely

It is important to test for the desired, essential behavior of a unit of code, rather than test for the incidental behavior of its particular implementation. But this should not be taken or mistaken as an excuse for vague tests. Tests need to be both accurate *and* precise.

Something of a tried, tested, and testing classic, sorting routines offer an illustrative example. Implementing a sorting algorithm is not necessarily an everyday task for a programmer, but sorting is such a familiar idea that most people believe they know what to expect from it. This casual familiarity, however, can make it harder to see past certain assumptions.

When programmers are asked "What would you test for?" by far and away the most common response is "The result of sorting is a sorted sequence of elements." While this is true, it is not the whole truth. When prompted for a more precise condition, many programmers add that the resulting sequence should be the same length as the original. Although correct, this is still not enough. For example, given the following sequence:

```
3 1 4 1 5 9
```

The following sequence satisfies a postcondition of being sorted in non-descending order and having the same length as the original sequence:

```
3 3 3 3 3 3
```

Although it satisfies the spec, it is also most certainly not what was meant! This example is based on an error taken from real production code (fortunately caught before it was released), where a simple slip of a keystroke or a momentary lapse of reason led to an elaborate mechanism for populating the whole result with the first element of the given array.

The full postcondition is that the result is sorted and that it holds a permutation of the original values. This appropriately constrains the required behavior. That the result length is the same as the input length comes out in the wash and doesn't need restating.

Even stating the postcondition in the way described is not enough to give you a good test. A good test should be readable. It should be comprehensible and simple enough that you can see readily that it is correct (or not). Unless you already have code lying around for checking that a sequence is sorted and that one sequence contains a permutation of values in another, it is quite likely that the test code will be more complex than the code under test. As Tony Hoare observed:

> There are two ways of constructing a software design: One way is to make it so simple that there are *obviously* no deficiencies and the other is to make it so complicated that there are no obvious deficiencies.

Using concrete examples eliminates this accidental complexity and opportunity for accident. For example, given the following sequence:

```
3 1 4 1 5 9
```

The result of sorting is the following:

```
1 1 3 4 5 9
```

No other answer will do. Accept no substitutes.

Concrete examples helps to illustrate general behavior in an accessible and unambiguous way. The result of adding an item to an empty collection is not simply that it is not empty: It is that the collection now has a single item. And that the single item held is the item added. Two or more items would qualify as not empty. And would also be wrong. A single item of a different value would also be wrong. The result of adding a row to a table is not simply that the table is one row bigger. It also entails that the row's key can be used to recover the row added. And so on.

In specifying behavior, tests should not simply be accurate: They must also be precise.

By [Kevlin Henney](http://programmer.97things.oreilly.com/wiki/index.php/Kevlin_Henney)